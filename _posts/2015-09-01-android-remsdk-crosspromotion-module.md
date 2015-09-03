---
ID: 343
post_title: '[ANDROID] CrossPromotion Module'
author: nan.den
post_date: 2015-09-01 22:03:22
post_excerpt: ""
layout: post
permalink: >
  http://rem-dev-jeast.azurewebsites.net/2015/09/01/android-remsdk-crosspromotion-module/
published: true
---
Notes: 
- This tutorial is based on the <a href="https://rmsdk.blob.core.windows.net/rmsdkcontainer/rmsdk-android-v1.3.0.zip?st=2015-09-02T02%3A09%3A25Z&se=2015-09-02T02%3A29%3A25Z&sp=r&sv=2014-02-14&sr=b&sig=lFXg3GzyTekz%2Bn3bfS59rC%2FryDaRcxUrIzDtD6RNjvY%3D">"release-v1.3"</a>. 
*For more information about this release version please visit <a href="https://rmsdk.apps.global.rakuten.com/docs/android#notes"target="_blank">here</a>.  
– This module requires Android version 2.3 or more.(Gingerbread ~) 

This tutorial is about… 
Add cross promotion function into applications. 

<strong>Step #1: Add dependencies</strong> 
There are two options to add dependencies in your application. 
Visit <a href="https://rakuten.atlassian.net/wiki/pages/viewpage.action?pageId=225183560" target="_blank">this website</a> to set up either "First Option" or "Second Option". Then, add following dependencies in your application build.gradle based on the options.

 
<pre class="lang:java decode:true " title="@build.gradel#dependencies" >// First Option 
compile 'com.android.support:support-v4:22.1.0' 
compile 'com.android.support:support-annotations:22.1.0' 

// add aar and jar files into libs folder 
compile files('libs/volley-1.0.0-SNAPSHOT.jar') 
compile files('libs/api-1.0-SNAPSHOT.jar') 
compile (name: 'versiontracker-1.4.1', ext: 'aar') 
compile (name: 'crosspromotion-1.1', ext: 'aar')</pre> 

 
<pre class="lang:java decode:true " title="@build.gradle#dependencies" >// Second Option  
compile 'jp.co.rakuten.sdtd.crosspromotion:crosspromotion:1.1'</pre> 

<strong>Step #2: Add following permission in AndroidManifest.xml</strong>

 
<pre class="lang:java decode:true " title="AndroidManifest.xml" >&lt;manifest ……&gt; 

&lt;!-- Internet access --&gt; 
&lt;uses-permission android:name="android.permission.INTERNET"/&gt; 

&lt;application ……&gt;</pre> 

<strong>Step #3: Create a class to handle image cache</strong> 
In following code snippet, we create a class called LruBitmaoCache. This class is subclass of LruCache and implementing ImageCach.
 
<pre class="lang:java decode:true " title="@LruBitmapCache" >public class LruBitmapCache extends LruCache&lt;String, Bitmap&gt; implements ImageCache {

    // constructor  
    public LruBitmapCache(int maxSize) { 
        super(maxSize); 
    }

    // For calculating the maxSize 
    public static int getCacheSize(Context context) { 
        final DisplayMetrics displayMetrics = context
                                             .getResources()
                                             .getDisplayMetrics(); 
        final int screenWidth = displayMetrics.widthPixels; 
        final int screenHeight = displayMetrics.heightPixels; 
        final int screenBytes = screenWidth * screenHeight * 4; 
        // Returns a cache size equal to approximately three screens worth of images. 
        return screenBytes * 3; 
    }

    // Override sizeOf method 
    @Override 
    protected int sizeOf(String key, Bitmap value) { 
        return value.getRowBytes() * value.getHeight(); 
    }

.....

}
</pre> 

<strong>Step #4: Set up to initialize objects in Application startup routine</strong> 
In the following code snippet we create a subclass of Application, and the subclass will be called on app launch to initialize objects.

<pre class="lang:java decode:true " title="#AppSubclass" >public class AppSubClass extends Application {
....

    @Override 
    public void onCreate() { 
        super.onCreate(); 

    // Volley initialization 
    RequestQueue requestQueue = Volley.newRequestQueue(this); 
    requestQueue .start();

    // define ImageLoader  
    ImageLoader imageLoader = new ImageLoader(requestQueue, new LruBitmapCache(LruBitmapCache.getCacheSize(this)));

    // CrossPromotionManager initialization 
    CrossPromotionManager.INSTANCE.initialize( 
                          this,    
                          applicationName, 
                          applicationRevision, 
                          applicationServiceId, 
                          requestQueue, 
                          imageLoader);

    // Set API Subscription key 
    CrossPromotionManager.INSTANCE.setApiSubscriptionKey(API_SUBSCRIPTION_KEY); 
 
    // For set to staging environment 
    CrossPromotionManager.INSTANCE.setStaging(true); 
 
    // Set debug mode *optional 
    CrossPromotionManager.INSTANCE.setDebug(true);

}</pre> 

<strong>Step #5: Add cross promotion UI</strong>
Set up an intent and launch the cross promotion UI. 
<pre class="lang:java decode:true " title="@MainActivity" >Intent intent = CrossPromotionManager.INSTANCE.getCrossPromotionIntent(CrossPromotionVisibilityOption.ALL); 
startActivity(intent);</pre> 

<strong>More:</strong>

- You can choose application visibility option as follow:
 
<pre class="lang:java decode:true " >// Options for filter apps
CrossPromotionVisibilityOption.INSTALLED_ONLY 
CrossPromotionVisibilityOption.NON_INSTALLED_ONLY 
CrossPromotionVisibilityOption.ALL</pre> 
