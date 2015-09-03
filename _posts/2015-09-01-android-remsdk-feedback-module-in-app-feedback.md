---
ID: 325
post_title: '[ANDROID] Feedback Module ~ In-App Feedback ~'
author: nan.den
post_date: 2015-09-01 02:30:30
post_excerpt: ""
layout: post
permalink: >
  http://rem-dev-jeast.azurewebsites.net/2015/09/01/android-remsdk-feedback-module-in-app-feedback/
published: true
---
Notes:
- In order to use the Feedback module in your application, you need to register your application. More information coming soon….
- This tutorial is based on the <a href="https://rmsdk.blob.core.windows.net/rmsdkcontainer/rmsdk-android-v1.3.0.zip?st=2015-09-02T02%3A09%3A25Z&se=2015-09-02T02%3A29%3A25Z&sp=r&sv=2014-02-14&sr=b&sig=lFXg3GzyTekz%2Bn3bfS59rC%2FryDaRcxUrIzDtD6RNjvY%3D">"release-v1.3"</a>
 *For more information about this release version please visit <a href="https://rmsdk.apps.global.rakuten.com/docs/android#notes" target="_blank">here</a>.

This tutorial is about…
Add User Feedback built-in UI to your application. 

<strong>Step #1: Add dependencies</strong>
There are two options to add dependencies in your application.
Visit <a href="https://rakuten.atlassian.net/wiki/pages/viewpage.action?pageId=225183560" target="_blank">this website</a> to set up either "First Option" or "Second Option". Then, add following dependencies in your application build.gradle based on the options.

 
<pre class="lang:java decode:true " title="@build.gradle#dependencies" >
// First Option
compile (name: 'feedback-1.2', ext: 'aar')
compile (name: 'deviceinformation-1.1', ext: 'aar')
compile (name: 'versiontracker-1.4.1', ext: 'aar')
compile files('libs/volley-1.0.0-SNAPSHOT.jar')
</pre> 

 
<pre class="lang:java decode:true " title="@build.gradle#dependencies" >
// Second Option
compile 'jp.co.rakuten.sdtd.feedback:feedback:1.2'
</pre> 

<strong>Step #2: Set up to initialize objects in Application startup routine</strong>
In the following code snippet we create a subclass of Application, and the subclass will be called on app launch to initialize objects.
 
<pre class="lang:java decode:true " title="@AppSubClass#onCreate" >public class AppSubClass extends Application {
    .....
    @Override
    public void onCreate() {
        super.onCreate();

        // Volley initialization
        RequestQueue requestQueue = Volley.newRequestQueue(this);

        // FeedbackManager initialization
        FeedbackManager.INSTANCE.initialize(this, requestQueue);
        FeedbackManager.INSTANCE.useDebug(true); // optional
    }
}
</pre> 

<strong>Step #3: Add Feedback built-in UI</strong>
Add the following code snippet in the class where you want to launch the UI.

 
<pre class="lang:java decode:true " title="@MainActivity#onOptionsItemSelected" >// add the code to show feedback UI
FeedbackManager.INSTANCE.showFeedback(MainActivity.this);</pre> 
