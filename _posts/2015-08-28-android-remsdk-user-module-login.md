---
ID: 276
post_title: '[Android] User Module ~ Login ~'
author: nan.den
post_date: 2015-08-28 03:24:42
post_excerpt: ""
layout: post
permalink: >
  http://rem-dev-jeast.azurewebsites.net/2015/08/28/android-remsdk-user-module-login/
published: true
---
Notes:
- Your application needs to be whitelisted in order to integrate this User Module. More information coming soon....
- This tutorial is based on the <a href="https://rmsdk.blob.core.windows.net/rmsdkcontainer/rmsdk-android-v1.3.0.zip?st=2015-08-27T23%3A04%3A52Z&se=2015-08-27T23%3A24%3A52Z&sp=r&sv=2014-02-14&sr=b&sig=wBVYQ%2FywJZVIIH5R%2FPF5Rl2qNWYMt5u9oM8MZa9ugD8%3D">"release-v1.3"</a>
 *For more information about this release version please visit <a href="https://rmsdk.apps.global.rakuten.com/docs/android#notes" target="_blank">here</a>.

This tutorial is about...
- Integration of Rakuten <a href="https://rmsdk.apps.global.rakuten.com/blog/single-sign-on" target="_blank">Single Sign-On</a> login

<strong>Step #1: Add dependencies</strong>
There are two options to add dependencies in your application.
Visit <a href="https://rakuten.atlassian.net/wiki/pages/viewpage.action?pageId=225183560" target="_blank">this website</a> to set up either "First Option" or "Second Option". Then, add following dependencies in your application build.gradle based on the options.
 
<pre class="lang:java decode:true " title="@build.gradle#dependencies" >// First Option
compile 'com.android.support:support-v4:22.1.0'
compile 'com.android.support:support-annotations:22.1.0'
compile 'com.google.code.gson:gson:2.2.4'
// add aar and jar files into libs folder
compile files('libs/volley-1.0.0-SNAPSHOT.jar')
compile files('libs/api-1.0-SNAPSHOT.jar')
compile (name: 'versiontracker-1.4.1', ext: 'aar')
compile (name: 'user-authenticator-3.4.2', ext: 'aar')
compile (name: 'user-3.4.2', ext: 'aar')
</pre> 
 
<pre class="lang:java decode:true " title="@build.gradle#dependencies" >// Second Option
compile 'jp.co.rakuten.sdtd.user:user:3.4'</pre> 

<strong>Step #2: Add following permission in AndroidManifest.xml</strong>
 
<pre class="lang:java decode:true " >&lt;manifest ……&gt;

    &lt;uses-permission android:name="android.permission.INTERNET" /&gt;
    &lt;uses-permission android:name="android.permission.USE_CREDENTIALS" /&gt;
    &lt;uses-permission android:name="android.permission.GET_ACCOUNTS" /&gt;
    &lt;uses-permission android:name="android.permission.MANAGE_ACCOUNTS" /&gt;
    &lt;uses-permission android:name="android.permission.AUTHENTICATE_ACCOUNTS" /&gt;

&lt;application ……&gt;
</pre> 

<strong>Step #3: Set up to initialize objects in Application startup routine</strong>
In the following code snippet we create a subclass of Application, and the subclass will be called on app launch to initialize objects.
 
<pre class="lang:java decode:true " title="@AppSubClass#onCreate" >public class AppSubClass extends Application {
    .....
    @Override
    public void onCreate() {
        super.onCreate();
        // Volley initialization
        RequestQueue requestQueue = Volley.newRequestQueue(this);
        // LoginManager initialization
        LoginManager.INSTANCE.initialize(this, requestQueue);
    }
}</pre> 
Add the subclass in AndroidManifest.xml
 
<pre class="lang:java decode:true " title="@AndroidManifest#application ~ add subclass of Application in ~" >android:name=".AppSubClass"</pre> 

<strong>Step #4: Add Login and Logout</strong>

~ Login ~ 
In order to show login UI, use SsoLoginActivity.
In following code snippet, we intent to SsoLoginActivity from current class and the REQUESTCODE_LOGIN will be passed to onActivityResult to perform further action.
 
<pre class="lang:java decode:true " title="@MainActivity#onCreate" >startActivityForResult(SsoLoginActivity.newIntent(MainActivity.this).build(), REQUEST_LOGIN);</pre> 

~ Logout ~
In order to show logout UI, use LogoutActivity.
In following code snippet, we intent to LogoutActivity from current class and the REQUEST_LOGOUT will be passed to onActivityResult to perform further action.
 
<pre class="lang:java decode:true " title="@MainActivity#onCreate" >startActivityForResult(LogoutActivity.newIntent(MainActivity.this).build(), REQUEST_LOGOUT);</pre> 

<strong>Step 5: Perform further action after login and logout
</strong>
 
<pre class="lang:java decode:true " title="@MainActivity#onActivityResult" >...
    @Override
    protected void onActivityResult(int requestCode, int resultCode, Intent data) {
        super.onActivityResult(requestCode, resultCode, data);
        switch (requestCode) {
            case REQUEST_LOGIN: {
                if(resultCode == RESULT_OK) {
                    // perform further action after login successfully
                }
                break;
            }
            case REQUEST_LOGOUT: {
                if(resultCode == RESULT_OK) {
                    // perform further action after logout successfully
                }
                break;
            }
        }
    }</pre> 



<strong>More:</strong>
 
- Check login status
<pre class="lang:java decode:true " >// return boolean
LoginManager.INSTANCE.getLoginService().isLoggedIn();</pre> 

- React to logout event. 
In some scenarios, logout event can be triggered. Below is two recommendations for handling the logout event.
  
<pre class="lang:java decode:true " title="@MainActivity#onStart" >// 1st Recommendation 
@Override
protected void onStart() {
     super.onStart();
     if (!LoginManager.INSTANCE.getLoginService().isLoggedIn()) {          
         // handle the logout event here. i.e.launch login UI or finish activity
     }
}</pre> 

 
<pre class="lang:java decode:true " >// 2nd Recommendation
public class MyLogoutReceiver extends BroadcastReceiver {
    @Overridepublic void onReceive(Context context, Intent intent) {
        // React to logout broadcast events to clear any data...etc
    }
}

....
@AndroidManifest.xml
&lt;application
    ....

    &lt;receiver android:name=".MyLogoutReceiver"           
        android:exported="false"&gt;     
        &lt;intent-filter&gt;         
            &lt;action android:name="jp.co.rakuten.sdtd.user.APP_LOGOUT" /&gt;         
            &lt;data android:scheme="package" android:host="&lt;your-application-id&gt;" /&gt;     
        &lt;/intent-filter&gt;
    &lt;/receiver&gt;
....
&lt;/application&gt;</pre> 

  

 


