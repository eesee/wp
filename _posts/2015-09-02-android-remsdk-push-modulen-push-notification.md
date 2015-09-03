---
ID: 359
post_title: '[ANDROID] Push Module ~ Push Notification ~'
author: nan.den
post_date: 2015-09-02 00:59:40
post_excerpt: ""
layout: post
permalink: >
  http://rem-dev-jeast.azurewebsites.net/2015/09/02/android-remsdk-push-modulen-push-notification/
published: true
---
Notes: 
- Please go through <a href="http://rem-dev-jeast.azurewebsites.net/2015/08/28/android-remsdk-user-module-login/">tutorial for login</a> before starting this tutorial.
- This tutorial is based on the <a href="https://rmsdk.blob.core.windows.net/rmsdkcontainer/rmsdk-android-v1.3.0.zip?st=2015-09-02T02%3A09%3A25Z&se=2015-09-02T02%3A29%3A25Z&sp=r&sv=2014-02-14&sr=b&sig=lFXg3GzyTekz%2Bn3bfS59rC%2FryDaRcxUrIzDtD6RNjvY%3D">"release-v1.3"</a>. 
*For more information about this release version please visit <a href="https://rmsdk.apps.global.rakuten.com/docs/android#notes"target="_blank">here</a>.  
– This module requires Android version 2.3 or more.(Gingerbread ~) 

This tutorial is about…
How to integrating push notifications into Rakuten applications.

<strong>Step #1: Add dependencies</strong>
There are two options to add dependencies in your application.
Visit <a href="https://rakuten.atlassian.net/wiki/pages/viewpage.action?pageId=225183560" target="_blank">this website</a> to set up either "First Option" or "Second Option". Then, add following dependencies in your application build.gradle based on the options.
 
<pre class="lang:java decode:true " title="@build.gradle#dependencies " >// First Option
compile 'org.jsoup:jsoup:1.7.3'
compile 'com.intellij:annotations:12.0'
compile 'com.google.android.gms:play-services-gcm:7.0.0'
compile 'com.google.android.gms:play-services-base:7.0.0'
compile files('libs/ SaxRassReader-0.0.1-SNAPSHOT.jar')
compile (name: ' push-2.6', ext: 'aar')
</pre> 

 
<pre class="lang:java decode:true " title="@build.gradle#dependencies " >// Second Option
compile 'jp.co.rakuten.sdtd.push:push:2.6'
</pre> 

* You need dependencies for <a href="http://rem-dev-jeast.azurewebsites.net/2015/08/28/android-remsdk-user-module-login/">User Module</a> as well.

<strong>Step #2: Add scopes for token </strong>
 
<pre class="lang:java decode:true " title="@AppSubclass#memberVariable " >String PUSH_SCOPES =	"pnp_android_register,
                         pnp_android_unregister,
                         pnp_android_denytype_check,
                         pnp_android_denytype_update,
                         pnp_com mon_pushedhistory,
                         pnp_common_getunreadcount,
                         pnp_common_sethistorystatus,
                         pnp_common_trackingopen";
</pre> 
* Visit <a href="http://rem-dev-jeast.azurewebsites.net/2015/08/31/android-remsdk-user-module-obtain-token/">here</a> for how to set up scopes to obtain token.

<strong>Step #3: Add following permission in AndroidManifest.xml</strong>
 
<pre class="lang:java decode:true " title="@AndroidManifest.xml" >&lt;manifest ……&gt;

&lt;uses-permission android:name="com.google.android.c2dm.permission.RECEIVE" /&gt;   
&lt;uses-permission android:name="android.permission.WAKE_LOCK" /&gt;

&lt;uses-permission android:name="&lt;application package name&gt;.permission.C2D_MESSAGE" /&gt;
&lt;permission   
android:name="&lt;application package name&gt;.permission.C2D_MESSAGE"
android:protectionLevel="signature" /&gt;

&lt;application ……&gt;
</pre> 
* You need permissions for <a href="http://rem-dev-jeast.azurewebsites.net/2015/08/28/android-remsdk-user-module-login/">User Module</a> as well.

<strong>Step #4: Create a subclass of AbstractPushService</strong>
In the following code snippet, we create a subclass of AbstractPushService to receive the push notification from Google Cloud Messaging and you can perform further action here.

 
<pre class="lang:java decode:true " title="@MyPushService " >public class MyPushService extends AbstractPushService {
    ....
    @Override
    protected void onMessage(Context context, Intent intent) {
        GoogleCloudMessaging gcm = GoogleCloudMessaging.getInstance(context);
        String messageType = gcm.getMessageType(intent);

        if(GoogleCloudMessaging.MESSAGE_TYPE_MESSAGE.equals(messageType)) {
            // perform further action here
        }
    }
    ....
}
</pre> 
<strong>Step #5: Add Push Notification Receiver and Service in AndroidManifest.xml</strong>
 
<pre class="lang:java decode:true " title="@AndroidManifest.xml" >&lt;application ....&gt;

&lt;!--Push Notification Receiver--&gt;
&lt;receiver 
    android:name="jp.co.rakuten.sdtd.push.GcmBroadcastReceiver"  
    android:permission="com.google.android.c2dm.permission.SEND"&gt;   
    &lt;intent-filter&gt;       
        &lt;action android:name="com.google.android.c2dm.intent.RECEIVE" /&gt;
        &lt;action android:name="com.google.android.c2dm.intent.REGISTRATION" /&gt;       
        &lt;category android:name="&lt;application package name&gt;" /&gt;   
    &lt;/intent-filter&gt;
&lt;/receiver&gt;

&lt;!-- Intent Service receiving push notifications (MyPushService extends to jp.co.rakuten.sdtd.push.AbstractPushService) --&gt;
&lt;service android:name="&lt;application package name&gt;.MyPushService" /&gt;

&lt;activity ..../&gt;

&lt;/application&gt;
</pre> 

<strong>Step #6: Set up to initialize objects in Application startup routine</strong>
In the following code snippet we create a subclass of Application, and the subclass will be called on app launch to initialize objects.
 
<pre class="lang:java decode:true " title="@AppSubclass" >public class AppSubClass extends Application {
    .....
    @Override
    public void onCreate() {
        super.onCreate();
        // need Volley and LoginManager initialization from User Module as well
        .....
    // PushManager initialization
    PushManager.INSTANCE.initialize(
                         this, 
                         PNP_SENDER_ID, 
                         requestQueue, 
                         MyPushService.class);
    PushManager.INSTANCE.setPNPClient(PNP_CLIENT_ID, PNP_CLIENT_SECRET);

    // set debug mode *optional 
    PushManager.INSTANCE.setDebug(true);

    // set environment, default is production
    PushManager.INSTANCE.setStaging(false);
    PushManager.INSTANCE.useLux(false);
    }

    ....
}
</pre> 
<strong>Step #7: Push notification registration</strong>
User can receive push notification from PNP, after the registration.
 
<pre class="lang:java decode:true " title="@MainActivity" >if(!PushManager.INSTANCE.isDeviceRegistered()) {

    Future runningFuture = PushManager.INSTANCE.register(token,
                new PushManager.PushRegistrationListener() {
                    @Override
                    public void onPushRegistration() {
                        // successfully registered 
                    }
                }, new PushManager.PushErrorListener() {
                     @Override
                     public void onPushError(Exception e) {
                         // registration error
                     }
                   }
    );
}
</pre> 
<strong>Step #8: Unregister push notification</strong>
User will not receive the push notification after unregister the device.

 
<pre class="lang:java decode:true " title="@MainActivity" >if(PushManager.INSTANCE.isDeviceRegistered()) {
    Future runningFuture = PushManager.INSTANCE.unregister(token,
                    new PushManager.PushUnregistrationListener() {
                        @Override
                        public void onPushUnregistration() {
                            // unregister success
                        }
                    }, new PushManager.PushErrorListener() {
                        @Override
                        public void onPushError(Exception e) {
                            // unregister error
                        }
                    }
    );
}
</pre> 


