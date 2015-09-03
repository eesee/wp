---
ID: 301
post_title: '[Android] User Module ~ Obtain token ~'
author: nan.den
post_date: 2015-08-31 00:53:01
post_excerpt: ""
layout: post
permalink: >
  http://rem-dev-jeast.azurewebsites.net/2015/08/31/android-remsdk-user-module-obtain-token/
published: true
---
Notes:
Please go through <a href="http://rem-dev-jeast.azurewebsites.net/2015/08/28/android-remsdk-user-module-login/">tutorial for login</a> before starting this tutorial.
– This tutorial is based on the <a href="https://rmsdk.blob.core.windows.net/rmsdkcontainer/rmsdk-android-v1.3.0.zip?st=2015-09-02T02%3A09%3A25Z&se=2015-09-02T02%3A29%3A25Z&sp=r&sv=2014-02-14&sr=b&sig=lFXg3GzyTekz%2Bn3bfS59rC%2FryDaRcxUrIzDtD6RNjvY%3D">“release-v1.3”</a>.
*For more information about this release version please visit <a href="https://rmsdk.apps.global.rakuten.com/docs/android#notes">here</a>.

This tutorial is about…
Obtain an access token for RAE APIs. 

<strong>Step #1: Configure RAE token provider in Application startup routine</strong>
 
<pre class="lang:java decode:true " title="@AppSubClass#onCreate" >// create an AuthProvider 
AuthProviderGID authProvider = new AuthProviderGID.Builder() 
                                                  .client(CLIENT_ID, CLIENT_CLIENT_SECRET) 
                                                  .scope(SCOPE) 
                                                  .mallId("es") 
                                                  .build(); 
 
LoginService loginService = LoginManager.INSTANCE.getLoginService(); 
 
// register AuthProvider to the LoginService 
loginService.registerAuthProvider(AUTHENTICATION_TYPE, authProvider);</pre> 

<strong>Step #2: Obtain an access token</strong>
 
<pre class="lang:java decode:true " title="@MainActivity" >LoginHelper.authRequest(AUTHENTICATION_TYPE, 
    new LoginHelper.AuthCallback&lt;AuthResponse&gt;(){ 
 
        @Override 
        public void onAuthSuccess(AuthResponse authResponse) { 
        // obtain token 
        token = authResponse.getToken(); 
        } 
 
        @Override 
        public void onAuthError(Exception e) { 
        // handle error here 
        } 
    });</pre> 
 
 