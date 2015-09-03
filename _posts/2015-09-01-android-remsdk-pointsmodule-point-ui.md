---
ID: 312
post_title: '[ANDROID] Points Module'
author: nan.den
post_date: 2015-09-01 00:35:36
post_excerpt: ""
layout: post
permalink: >
  http://rem-dev-jeast.azurewebsites.net/2015/09/01/android-remsdk-pointsmodule-point-ui/
published: true
---
Notes:
- Please go through <a href="http://rem-dev-jeast.azurewebsites.net/2015/08/28/android-remsdk-user-module-login/">tutorial for login</a> before starting this tutorial.
– This tutorial is based on the <a href="https://rmsdk.blob.core.windows.net/rmsdkcontainer/rmsdk-android-v1.3.0.zip?st=2015-09-02T02%3A09%3A25Z&se=2015-09-02T02%3A29%3A25Z&sp=r&sv=2014-02-14&sr=b&sig=lFXg3GzyTekz%2Bn3bfS59rC%2FryDaRcxUrIzDtD6RNjvY%3D">“release-v1.3”</a>.
*For more information about this release version please visit <a href="https://rmsdk.apps.global.rakuten.com/docs/android#notes">here</a>.
- This module requires Android version 2.3 or more.(Gingerbread ~)

This tutorial is about…
How to provide UI for querying point and member status information for users logged in with Rakuten ID. 

<strong>Step #1: Add dependencies</strong>
There are two options to add dependencies in your application.
Visit <a href="https://rakuten.atlassian.net/wiki/pages/viewpage.action?pageId=225183560" target="_blank">this website</a> to set up either "First Option" or "Second Option". Then, add following dependencies in your application build.gradle based on the options.

<pre class="lang:java decode:true " title="@build.gradle#dependencies" >

// First Option
compile 'com.nineoldandroids:library:2.4.0'
compile (name: 'points-1.7.2', ext: 'aar')
</pre> 

 
<pre class="lang:java decode:true " title="@build.gradle#dependencies" >
// Second Option
compile 'jp.co.rakuten.sdtd.points:points:1.7.2'</pre> 

* You need dependencies for <a href="http://rem-dev-jeast.azurewebsites.net/2015/08/28/android-remsdk-user-module-login/">User Module</a> as well.

<strong>Step #2: Add scopes for token </strong>

~ Japan Ichiba points ~
 
<pre class="lang:java decode:true " title="@AppSubClass#memberVariable" >String ICHIBA_POINT_SCOPES =    "memberinfo_read_name," +
                                "memberinfo_read_point," +
                                "memberinfo_read_rank";

</pre> 

~ Global points ~
 
<pre class="lang:java decode:true " title="@AppSubClass#memberVariable" >String GLOBAL_POINT_SCOPES =    "memberinfo_read_name," +
                                "memberinfo_read_point," +
                                "memberinfo_read_rank," +
                                "gecp_point_read";
</pre> 
* Visit <a href="http://rem-dev-jeast.azurewebsites.net/2015/08/31/android-remsdk-user-module-obtain-token/">here</a> for how to set up scopes to obtain token. 

<strong>Step #3: Set up to initialize objects in Application startup routine</strong> 
In the following code snippet we create a subclass of Application, and the subclass will be called on app launch to initialize objects.
 
<pre class="lang:java decode:true " title="@AppSubclass#onCreate" >public class AppSubClass extends Application {
    .....
    @Override
    public void onCreate() {
        super.onCreate();
        // need Volley and LoginManager initialization as well 
        .....
        // PointsManager initialization
        PointsManager.INSTANCE.initialize(this, requestQueue);
    }
}</pre> 


<strong>Step #4: Create a layout for holding Ichiba/Global point fragment class  </strong>

 
<pre class="lang:java decode:true " >&lt;FrameLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:id="@+id/fragment_holder_rae"
    android:layout_width="match_parent"
    android:layout_height="match_parent"&gt;
&lt;/FrameLayout&gt;
</pre> 

<strong>Step #5: Add Ichiba/Global point built-in UI</strong>

~ Japan Ichiba points ~
For following code snippet, we obtain token at MainActivity and pass the token to an Activity called IchibaPointActivity. IchibaPointActivity calls PointFragment. 
<pre class="lang:java decode:true " title="@IchibaPointActivity#onCreate" >// receive token from MainActivity
Intent intent = getIntent(); 
String token = intent.getStringExtra("token");

FragmentManager fragmentManager = getSupportFragmentManager();
if(fragmentManager.findFragmentByTag("points") == null) { 
    // Call PointsFragment
    Fragment fragment = PointsFragment.newInstance(token);       
    fragmentManager.beginTransaction()            
                   .add(R.id.fragment_holder_rae, fragment, "points")    
                   .commit(); 
}

 </pre> 
~ Global points ~
For following code snippet, we obtain token at MainActivity and pass the token to an Activity called GlobalPointsActivity. GlobalPointsActivity calls GMPointsFragment. 
 
<pre class="lang:java decode:true " title="@GlobalPointsActivity#onCreate" >
// receive token from MainActivity
Intent intent = getIntent(); 
String token = intent.getStringExtra("token");

FragmentManager fragmentManager = getSupportFragmentManager(); 
if(fragmentManager.findFragmentByTag("points") == null) { 
    // Call GMPointsFragment
    Fragment fragment = GMPointsFragment.newInstance(token, Mall.getMallI(“es”));
    fragmentManager.beginTransaction()            
    .add(R.id.fragment_holder_rae, fragment, "points")            
    .commit(); 
}
</pre> 