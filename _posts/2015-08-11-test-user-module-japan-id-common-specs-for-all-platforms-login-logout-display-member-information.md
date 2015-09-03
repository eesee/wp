---
ID: 41
post_title: 'TEST: User Module &#8211; Japan ID &#8211; common specs for all platforms (Login, Logout &#038; Display Member Information)'
author: sdtd
post_date: 2015-08-11 09:09:54
post_excerpt: ""
layout: post
permalink: >
  http://rem-dev-jeast.azurewebsites.net/2015/08/11/test-user-module-japan-id-common-specs-for-all-platforms-login-logout-display-member-information/
published: true
---
<div class="page-metadata">
<ul>
	<li><a class="toc-link" href="https://confluence.rakuten-it.com/confluence/pages/viewpage.action?pageId=626037574#UserModule-JapanID-commonspecsforallplatforms(Login,Logout&amp;DisplayMemberInformation)-Definitions">Definitions</a></li>
	<li><span class="toc-item-body" data-outline="2"><a class="toc-link" href="https://confluence.rakuten-it.com/confluence/pages/viewpage.action?pageId=626037574#UserModule-JapanID-commonspecsforallplatforms(Login,Logout&amp;DisplayMemberInformation)-Features">Features</a></span></li>
	<li><span class="toc-item-body" data-outline="3"><a class="toc-link" href="https://confluence.rakuten-it.com/confluence/pages/viewpage.action?pageId=626037574#UserModule-JapanID-commonspecsforallplatforms(Login,Logout&amp;DisplayMemberInformation)-ExampleusageofUserLibraryinQAApp">Example usage of User Library in QA App</a></span></li>
</ul>
</div>
<div id="main-content" class="wiki-content">
<div class="toc-macro client-side-toc-macro  hidden-outline" data-headerelements="H1,H2"></div>
<h2 id="UserModule-JapanID-commonspecsforallplatforms(Login,Logout&amp;DisplayMemberInformation)-Definitions">Definitions</h2>
<div class="table-wrap">
<table class="confluenceTable">
<thead>
<tr>
<th class="confluenceTh">WHO</th>
<td class="confluenceTd">App developers using Rakuten Mobile SDK</td>
</tr>
</thead>
<tbody>
<tr>
<th class="confluenceTh">WHAT</th>
<td class="confluenceTd">Able to Login/Logout &amp; access account information natively for Rakuten Members, using JAPAN ID</td>
</tr>
<tr>
<th class="confluenceTh">WHY</th>
<td class="confluenceTd">The developers (users of Rakuten Mobile SDK) are able to use the Rakuten's member information in their apps</td>
</tr>
</tbody>
</table>
</div>
<h2 id="UserModule-JapanID-commonspecsforallplatforms(Login,Logout&amp;DisplayMemberInformation)-Features">Features</h2>
<div class="table-wrap">
<table class="confluenceTable tablesorter tablesorter-default stickyTableHeaders">
<thead class="tableFloatingHeaderOriginal">
<tr class="tablesorter-headerRow">
<th class="confluenceTh sortableHeader" tabindex="0" data-column="0">
<div class="tablesorter-header-inner">
<h3 id="UserModule-JapanID-commonspecsforallplatforms(Login,Logout&amp;DisplayMemberInformation)-Features.1">Features</h3>
</div></th>
<th class="confluenceTh sortableHeader" tabindex="0" data-column="1">
<div class="tablesorter-header-inner">Function</div></th>
<th class="confluenceTh sortableHeader" tabindex="0" data-column="2">
<div class="tablesorter-header-inner">Android</div></th>
<th class="confluenceTh sortableHeader" tabindex="0" colspan="1" data-column="3">
<div class="tablesorter-header-inner">iOS</div></th>
<th class="confluenceTh sortableHeader" tabindex="0" colspan="1" data-column="4">
<div class="tablesorter-header-inner">Windows</div></th>
</tr>
</thead>
<tbody>
<tr>
<td class="confluenceTd">
<h4 id="UserModule-JapanID-commonspecsforallplatforms(Login,Logout&amp;DisplayMemberInformation)-StandardizedUI">Standardized UI</h4>
</td>
<td class="confluenceTd">SDK ships a ready to use User Interface (screens for mobile application) that App developers can use to make their own app</td>
<td class="confluenceTd"><span class="status-macro aui-lozenge aui-lozenge-success">LIVE</span></td>
<td class="confluenceTd" colspan="1"><span class="status-macro aui-lozenge aui-lozenge-success">LIVE</span></td>
<td class="confluenceTd" colspan="1"><span class="status-macro aui-lozenge aui-lozenge-success">LIVE</span></td>
</tr>
<tr>
<td class="confluenceTd">
<h4 id="UserModule-JapanID-commonspecsforallplatforms(Login,Logout&amp;DisplayMemberInformation)-Login/Logout">Login / Logout</h4>
</td>
<td class="confluenceTd">Login &amp; Logout using Rakuten's Japan ID</td>
<td class="confluenceTd"><span class="status-macro aui-lozenge aui-lozenge-success">LIVE</span></td>
<td class="confluenceTd" colspan="1"><span class="status-macro aui-lozenge aui-lozenge-success aui-lozenge-subtle">IN DEV</span></td>
<td class="confluenceTd" colspan="1"><span class="status-macro aui-lozenge aui-lozenge-success">LIVE</span></td>
</tr>
<tr>
<td class="confluenceTd" colspan="1">
<h4 id="UserModule-JapanID-commonspecsforallplatforms(Login,Logout&amp;DisplayMemberInformation)-AccessUserinformation">Access User information</h4>
</td>
<td class="confluenceTd" colspan="1">Access basic user information like nickname, birthday, prefecture, gender, name in katakana</td>
<td class="confluenceTd" colspan="1"><span class="status-macro aui-lozenge aui-lozenge-success">LIVE</span></td>
<td class="confluenceTd" colspan="1"><span class="status-macro aui-lozenge aui-lozenge-success aui-lozenge-subtle">IN DEV</span></td>
<td class="confluenceTd" colspan="1"><span class="status-macro aui-lozenge aui-lozenge-success">LIVE</span></td>
</tr>
<tr>
<td class="confluenceTd" colspan="1">
<h4 id="UserModule-JapanID-commonspecsforallplatforms(Login,Logout&amp;DisplayMemberInformation)-RememberMe">Remember Me</h4>
</td>
<td class="confluenceTd" colspan="1">Remembers your credentials if you want to login again</td>
<td class="confluenceTd" colspan="1"><span class="status-macro aui-lozenge aui-lozenge-success">LIVE</span></td>
<td class="confluenceTd" colspan="1"><span class="status-macro aui-lozenge aui-lozenge-success aui-lozenge-subtle">IN DEV</span></td>
<td class="confluenceTd" colspan="1"><span class="status-macro aui-lozenge aui-lozenge-success">LIVE</span></td>
</tr>
<tr>
<td class="confluenceTd" colspan="1">
<h4 id="UserModule-JapanID-commonspecsforallplatforms(Login,Logout&amp;DisplayMemberInformation)-ForgotPassword">Forgot Password</h4>
</td>
<td class="confluenceTd" colspan="1">The process (UI &amp; libraries) to help users recover their password</td>
<td class="confluenceTd" colspan="1"><span class="status-macro aui-lozenge aui-lozenge-subtle">SOMEDAY</span></td>
<td class="confluenceTd" colspan="1"><span class="status-macro aui-lozenge aui-lozenge-subtle">SOMEDAY</span></td>
<td class="confluenceTd" colspan="1"><span class="status-macro aui-lozenge aui-lozenge-subtle">SOMEDAY</span></td>
</tr>
</tbody>
</table>
</div>
<h3 id="UserModule-JapanID-commonspecsforallplatforms(Login,Logout&amp;DisplayMemberInformation)-1.CreatingUserInterface(mobileappscreen)forLoginfunctionality">1. Creating User Interface (mobile app screen) for Login functionality</h3>
The Rakuten Mobile SDK ships a ready to use native User Interface (mobile application screens) for User Module.

The UI is part of the User Library in the SDK. It is available as native UI for all three platforms.
<h3 id="UserModule-JapanID-commonspecsforallplatforms(Login,Logout&amp;DisplayMemberInformation)-"><span class="confluence-embedded-file-wrapper image-left-wrapper confluence-embedded-manual-size"><img class="confluence-embedded-image confluence-external-resource confluence-content-image-border image-left" src="https://rakuten.atlassian.net/wiki/download/attachments/215374040/IMG_0204.PNG?version=1&amp;modificationDate=1422860394146&amp;api=v2" alt="" width="225" height="400" data-image-src="https://rakuten.atlassian.net/wiki/download/attachments/215374040/IMG_0204.PNG?version=1&amp;modificationDate=1422860394146&amp;api=v2" /></span></h3>
Application Developers can choose to:

- use this UI natively in their apps

- over ride some of the elements &amp; keep rest of the screen as-is
- create their own UI
<h4 id="UserModule-JapanID-commonspecsforallplatforms(Login,Logout&amp;DisplayMemberInformation)-Availability:">Availability:</h4>
<div class="table-wrap">
<table class="confluenceTable tablesorter tablesorter-default stickyTableHeaders">
<thead class="tableFloatingHeaderOriginal">
<tr class="tablesorter-headerRow">
<th class="confluenceTh sortableHeader" tabindex="0" data-column="0"></th>
<th class="confluenceTh sortableHeader" tabindex="0" data-column="1">
<div class="tablesorter-header-inner">
<p class="tablesorter-header-inner">Android</p>

</div></th>
<th class="confluenceTh sortableHeader" tabindex="0" colspan="1" data-column="2">
<div class="tablesorter-header-inner">
<p class="tablesorter-header-inner">iOS</p>

</div></th>
<th class="confluenceTh sortableHeader" tabindex="0" colspan="1" data-column="3">
<div class="tablesorter-header-inner">
<p class="tablesorter-header-inner">Windows</p>

</div></th>
</tr>
</thead>
<tbody>
<tr>
<td class="confluenceTd">Standardized native UI</td>
<td class="confluenceTd"><span class="status-macro aui-lozenge aui-lozenge-success">AVAILABLE</span></td>
<td class="confluenceTd" colspan="1"><span class="status-macro aui-lozenge aui-lozenge-success">AVAILABLE</span></td>
<td class="confluenceTd" colspan="1"><span class="status-macro aui-lozenge aui-lozenge-success">AVAILABLE</span></td>
</tr>
</tbody>
</table>
</div>
<h3 id="UserModule-JapanID-commonspecsforallplatforms(Login,Logout&amp;DisplayMemberInformation)-2.Login&amp;LogoutusingRakuten'sJapanID">2. Login &amp; Logout using Rakuten's Japan ID</h3>
By utilizing the User Library in the SDK, developers can perform the proper authentication of users, using Japan ID.
<div>
<div class="table-wrap">
<table class="confluenceTable">
<tbody>
<tr>
<td class="confluenceTd">Given</td>
<td class="confluenceTd">The app uses Japan ID for login</td>
</tr>
<tr>
<td class="confluenceTd">When</td>
<td class="confluenceTd">the developers use the Rakuten Mobile SDK's User Library</td>
</tr>
<tr>
<td class="confluenceTd">Then</td>
<td class="confluenceTd">they can provide a mechanism for their users to Login using Rakuten username &amp; password</td>
</tr>
</tbody>
</table>
</div>
</div>
On successful provision of correct username &amp; password by the user, the app will be returned a token.

This token can be used to access this user's data later on.
<h4 id="UserModule-JapanID-commonspecsforallplatforms(Login,Logout&amp;DisplayMemberInformation)-Availability:.1">Availability:</h4>
<div class="table-wrap">
<table class="confluenceTable tablesorter tablesorter-default stickyTableHeaders">
<thead class="tableFloatingHeaderOriginal">
<tr class="tablesorter-headerRow">
<th class="confluenceTh sortableHeader" tabindex="0" data-column="0"></th>
<th class="confluenceTh sortableHeader" tabindex="0" data-column="1">
<div class="tablesorter-header-inner">
<p class="tablesorter-header-inner">Android</p>

</div></th>
<th class="confluenceTh sortableHeader" tabindex="0" colspan="1" data-column="2">
<div class="tablesorter-header-inner">
<p class="tablesorter-header-inner">iOS</p>

</div></th>
<th class="confluenceTh sortableHeader" tabindex="0" colspan="1" data-column="3">
<div class="tablesorter-header-inner">
<p class="tablesorter-header-inner">Windows</p>

</div></th>
</tr>
</thead>
<tbody>
<tr>
<td class="confluenceTd">Login &amp; Logout using Rakuten's Japan ID</td>
<td class="confluenceTd"><span class="status-macro aui-lozenge aui-lozenge-success">AVAILABLE</span></td>
<td class="confluenceTd" colspan="1"><span class="status-macro aui-lozenge aui-lozenge-success">AVAILABLE</span></td>
<td class="confluenceTd" colspan="1"><span class="status-macro aui-lozenge aui-lozenge-success">AVAILABLE</span></td>
</tr>
</tbody>
</table>
</div>
<h3 id="UserModule-JapanID-commonspecsforallplatforms(Login,Logout&amp;DisplayMemberInformation)-.8"></h3>
<h3 id="UserModule-JapanID-commonspecsforallplatforms(Login,Logout&amp;DisplayMemberInformation)-3.Accessbasicuserinformationlikenickname,birthday,prefecture,gender,nameinkatakana">3. Access basic user information like nickname, birthday, prefecture, gender, name in katakana</h3>
Once the Login has been made, a request for user's basic information can be made.

The basic information for user includes:
<ul>
	<li>Nickname</li>
	<li>First name</li>
	<li>Last name</li>
	<li>First name in Katakana</li>
	<li>Last name in Katakana</li>
	<li>Birthday</li>
	<li>Prefecture</li>
	<li>Gender</li>
</ul>
<h4 id="UserModule-JapanID-commonspecsforallplatforms(Login,Logout&amp;DisplayMemberInformation)-Availability:.2">Availability:</h4>
<div class="table-wrap">
<table class="confluenceTable tablesorter tablesorter-default stickyTableHeaders">
<thead class="tableFloatingHeaderOriginal">
<tr class="tablesorter-headerRow">
<th class="confluenceTh sortableHeader" tabindex="0" data-column="0"></th>
<th class="confluenceTh sortableHeader" tabindex="0" data-column="1">
<div class="tablesorter-header-inner">
<p class="tablesorter-header-inner">Android</p>

</div></th>
<th class="confluenceTh sortableHeader" tabindex="0" colspan="1" data-column="2">
<div class="tablesorter-header-inner">
<p class="tablesorter-header-inner">iOS</p>

</div></th>
<th class="confluenceTh sortableHeader" tabindex="0" colspan="1" data-column="3">
<div class="tablesorter-header-inner">
<p class="tablesorter-header-inner">Windows</p>

</div></th>
</tr>
</thead>
<tbody>
<tr>
<td class="confluenceTd">Access basic information</td>
<td class="confluenceTd"><span class="status-macro aui-lozenge aui-lozenge-success">LIVE</span></td>
<td class="confluenceTd" colspan="1"><span class="status-macro aui-lozenge aui-lozenge-success">LIVE</span></td>
<td class="confluenceTd" colspan="1"><span class="status-macro aui-lozenge aui-lozenge-success">LIVE</span></td>
</tr>
</tbody>
</table>
</div>
<strong>Example:</strong>

The QA App, whose code is bundled in the download package of the SDK provides an example implementation of this feature.
<ul>
	<li>User is asked for credentials</li>
	<li>User provides valid Japan ID username &amp; password</li>
	<li>Basic information of user is displayed on the next screen</li>
</ul>
<strong>Screenshots of QA App (bundled in SDK)</strong>
<div class="table-wrap">
<table class="confluenceTable">
<tbody>
<tr>
<td class="confluenceTd">
<h3 id="UserModule-JapanID-commonspecsforallplatforms(Login,Logout&amp;DisplayMemberInformation)-.9"><span class="confluence-embedded-file-wrapper image-left-wrapper confluence-embedded-manual-size"><img class="confluence-embedded-image confluence-external-resource image-left" src="https://rakuten.atlassian.net/wiki/download/attachments/215374040/IMG_0204.PNG?version=1&amp;modificationDate=1422860394146&amp;api=v2" alt="" width="365" height="649" data-image-src="https://rakuten.atlassian.net/wiki/download/attachments/215374040/IMG_0204.PNG?version=1&amp;modificationDate=1422860394146&amp;api=v2" /></span></h3>
</td>
<td class="confluenceTd" colspan="1"></td>
<td class="confluenceTd"><strong><span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img class="confluence-embedded-image confluence-external-resource" src="https://rakuten.atlassian.net/wiki/download/attachments/215374040/IMG_0181.PNG?version=2&amp;modificationDate=1422860481506&amp;api=v2" alt="" width="367" height="653" data-image-src="https://rakuten.atlassian.net/wiki/download/attachments/215374040/IMG_0181.PNG?version=2&amp;modificationDate=1422860481506&amp;api=v2" /></span></strong></td>
</tr>
</tbody>
</table>
</div>
<h3 id="UserModule-JapanID-commonspecsforallplatforms(Login,Logout&amp;DisplayMemberInformation)-4.Remembersyourcredentialsifyouwanttologinagain">4. Remembers your credentials if you want to login again</h3>
If a user has logged in once in the app, the app acquires a authentication token.

When user returns to the App, the it can be re-used by the app to login the user.

This can prove to be convenient for the users as they do not have to provide the login details once again.
<h4 id="UserModule-JapanID-commonspecsforallplatforms(Login,Logout&amp;DisplayMemberInformation)-Availability:.3">Availability:</h4>
<div class="table-wrap">
<table class="confluenceTable tablesorter tablesorter-default stickyTableHeaders">
<thead class="tableFloatingHeaderOriginal">
<tr class="tablesorter-headerRow">
<th class="confluenceTh sortableHeader" tabindex="0" data-column="0"></th>
<th class="confluenceTh sortableHeader" tabindex="0" data-column="1">
<div class="tablesorter-header-inner">
<p class="tablesorter-header-inner">Android</p>

</div></th>
<th class="confluenceTh sortableHeader" tabindex="0" colspan="1" data-column="2">
<div class="tablesorter-header-inner">
<p class="tablesorter-header-inner">iOS</p>

</div></th>
<th class="confluenceTh sortableHeader" tabindex="0" colspan="1" data-column="3">
<div class="tablesorter-header-inner">
<p class="tablesorter-header-inner">Windows</p>

</div></th>
</tr>
</thead>
<tbody>
<tr>
<td class="confluenceTd">Remembers your username &amp; password if you want to login again</td>
<td class="confluenceTd"><span class="status-macro aui-lozenge aui-lozenge-success">LIVE</span></td>
<td class="confluenceTd" colspan="1"><span class="status-macro aui-lozenge aui-lozenge-success">LIVE</span></td>
<td class="confluenceTd" colspan="1"><span class="status-macro aui-lozenge aui-lozenge-success">LIVE</span></td>
</tr>
</tbody>
</table>
</div>
<strong>Example:</strong>

An example of such functionality exists in the QA App, which is bundled as part of the SDK download package.

<strong><strong>Screenshot</strong>
</strong>

<span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img class="confluence-embedded-image confluence-external-resource" src="https://rakuten.atlassian.net/wiki/download/attachments/206605361/IMG_0215.PNG?version=1&amp;modificationDate=1422866678533&amp;api=v2" alt="" width="265" height="471" data-image-src="https://rakuten.atlassian.net/wiki/download/attachments/206605361/IMG_0215.PNG?version=1&amp;modificationDate=1422866678533&amp;api=v2" /></span>
<h3 id="UserModule-JapanID-commonspecsforallplatforms(Login,Logout&amp;DisplayMemberInformation)-5.SignupforanewRakutenAccount">5. Signup for a new Rakuten Account</h3>
<h3 id="UserModule-JapanID-commonspecsforallplatforms(Login,Logout&amp;DisplayMemberInformation)-6.Theprocesstohelpusersrecovertheirpassword">6. The process to help users recover their password</h3>
For both of the above features, SDK does not provides a native UI or code library.

One of the ways to circumvent this issue is that when Forgot password or new account Signup is required to be part of the app, make a switch over to mobile web pages.
<div class="table-wrap">
<table class="confluenceTable tablesorter tablesorter-default stickyTableHeaders">
<thead class="tableFloatingHeaderOriginal">
<tr class="tablesorter-headerRow">
<th class="confluenceTh sortableHeader" tabindex="0" data-column="0"></th>
<th class="confluenceTh sortableHeader" tabindex="0" data-column="1">
<div class="tablesorter-header-inner">
<div class="tablesorter-header-inner">Android</div>
</div></th>
<th class="confluenceTh sortableHeader" tabindex="0" colspan="1" data-column="2">
<div class="tablesorter-header-inner">
<div class="tablesorter-header-inner">iOS</div>
</div></th>
<th class="confluenceTh sortableHeader" tabindex="0" colspan="1" data-column="3">
<div class="tablesorter-header-inner">
<div class="tablesorter-header-inner">Windows</div>
</div></th>
</tr>
</thead>
<tbody>
<tr>
<td class="confluenceTd" colspan="1">
<h4 id="UserModule-JapanID-commonspecsforallplatforms(Login,Logout&amp;DisplayMemberInformation)-ForgotPassword.1">Forgot Password</h4>
</td>
<td class="confluenceTd" colspan="1"><span class="status-macro aui-lozenge aui-lozenge-complete">MOBILE WEB</span></td>
<td class="confluenceTd" colspan="1"><span class="status-macro aui-lozenge aui-lozenge-complete">MOBILE WEB</span></td>
<td class="confluenceTd" colspan="1"><span class="status-macro aui-lozenge aui-lozenge-complete">MOBILE WEB</span></td>
</tr>
<tr>
<td class="confluenceTd" colspan="1"><strong>Signup for new account</strong></td>
<td class="confluenceTd" colspan="1"><span class="status-macro aui-lozenge aui-lozenge-complete">MOBILE WEB</span></td>
<td class="confluenceTd" colspan="1"><span class="status-macro aui-lozenge aui-lozenge-complete">MOBILE WEB</span></td>
<td class="confluenceTd" colspan="1"><span class="status-macro aui-lozenge aui-lozenge-complete">MOBILE WEB</span></td>
</tr>
</tbody>
</table>
</div>
<h3 id="UserModule-JapanID-commonspecsforallplatforms(Login,Logout&amp;DisplayMemberInformation)-BundledUI">Bundled UI</h3>
As mentioned earlier the Rakuten Mobile SDK provides a bundled UI within the SDK itself.
<ul>
	<li>User's can use this on as-is basis</li>
	<li>They can customize it for their need</li>
	<li>or ignore it altogether &amp; build their UI from scratch</li>
</ul>
<div class="table-wrap">
<table class="confluenceTable">
<tbody>
<tr>
<td class="confluenceTd"><span class="confluence-embedded-file-wrapper image-center-wrapper confluence-embedded-manual-size"><img class="confluence-embedded-image confluence-external-resource image-center" src="https://rakuten.atlassian.net/wiki/download/attachments/215374040/IMG_0204.PNG?version=1&amp;modificationDate=1422860394146&amp;api=v2" alt="" width="397" height="706" data-image-src="https://rakuten.atlassian.net/wiki/download/attachments/215374040/IMG_0204.PNG?version=1&amp;modificationDate=1422860394146&amp;api=v2" /></span></td>
<td class="confluenceTd"><span class="confluence-embedded-file-wrapper image-center-wrapper confluence-embedded-manual-size"><img class="confluence-embedded-image confluence-external-resource image-center" src="https://rakuten.atlassian.net/wiki/download/attachments/206605361/IMG_0215.PNG?version=1&amp;modificationDate=1422866678533&amp;api=v2" alt="" width="397" height="706" data-image-src="https://rakuten.atlassian.net/wiki/download/attachments/206605361/IMG_0215.PNG?version=1&amp;modificationDate=1422866678533&amp;api=v2" /></span></td>
</tr>
<tr>
<td class="confluenceTd">Login Screen</td>
<td class="confluenceTd">Remember Me Screen</td>
</tr>
<tr>
<td class="confluenceTd">Builtin UI that developers can use in their mobile app,
for login</td>
<td class="confluenceTd">Builtin UI that developers can use when there is a previously
signed in user reutrns to the app.</td>
</tr>
</tbody>
</table>
</div>
<h3 id="UserModule-JapanID-commonspecsforallplatforms(Login,Logout&amp;DisplayMemberInformation)-Fields&amp;Descriptions">Fields &amp; Descriptions</h3>
The UI contains following Fields, and their descriptions are listed here:
<div class="table-wrap">
<table class="confluenceTable tablesorter tablesorter-default stickyTableHeaders" style="height: 816px;" width="869">
<thead class="tableFloatingHeaderOriginal">
<tr class="tablesorter-headerRow">
<th class="confluenceTh sortableHeader" tabindex="0" colspan="1" data-column="0"></th>
<th class="confluenceTh sortableHeader" tabindex="0" data-column="1">
<div class="tablesorter-header-inner">
<div class="tablesorter-header-inner">

Field

</div>
</div></th>
<th class="confluenceTh sortableHeader" tabindex="0" data-column="2">
<div class="tablesorter-header-inner">
<div class="tablesorter-header-inner">

Description

</div>
</div></th>
<th class="confluenceTh sortableHeader" tabindex="0" data-column="3">
<div class="tablesorter-header-inner">
<div class="tablesorter-header-inner">

Required (Yes/No)

</div>
</div></th>
<th class="confluenceTh sortableHeader" tabindex="0" data-column="4">
<div class="tablesorter-header-inner">
<div class="tablesorter-header-inner">

Input Type

</div>
</div></th>
<th class="confluenceTh sortableHeader" tabindex="0" data-column="5">
<div class="tablesorter-header-inner">
<div class="tablesorter-header-inner">

Validation<br class="atl-forced-newline" />Business Rules

</div>
</div></th>
<th class="confluenceTh sortableHeader" tabindex="0" data-column="6">
<div class="tablesorter-header-inner">
<div class="tablesorter-header-inner">

Comments

</div>
</div></th>
</tr>
</thead>
<tbody>
<tr>
<td class="confluenceTd" colspan="1"></td>
<td class="confluenceTd">Username</td>
<td class="confluenceTd">Rakuten ID of the user</td>
<td class="confluenceTd">Yes</td>
<td class="confluenceTd">Textbox</td>
<td class="confluenceTd">Rakuten ID Format
<ul>
	<li>valid email address</li>
</ul>
</td>
<td class="confluenceTd"></td>
</tr>
<tr>
<td class="confluenceTd" colspan="1"></td>
<td class="confluenceTd" colspan="1">Password</td>
<td class="confluenceTd" colspan="1">Password assosciated with Rakuten ID</td>
<td class="confluenceTd" colspan="1">Yes</td>
<td class="confluenceTd" colspan="1">Password Text Box</td>
<td class="confluenceTd" colspan="1">Rakuten Password validation rules
<ul>
	<li>alphanumeric</li>
</ul>
</td>
<td class="confluenceTd" colspan="1"></td>
</tr>
<tr>
<td class="confluenceTd"></td>
<td class="confluenceTd" colspan="1">Remember me</td>
<td class="confluenceTd" colspan="1">Whether user should be kept login or not</td>
<td class="confluenceTd" colspan="1">No</td>
<td class="confluenceTd" colspan="1">Toggle Button</td>
<td class="confluenceTd" colspan="1">Either ON or OFF</td>
<td class="confluenceTd" colspan="1">
<ul>
	<li>Currently its "Do not remember me"</li>
</ul>
- We will correct the symantics in future</td>
</tr>
</tbody>
</table>
</div>
<h3 id="UserModule-JapanID-commonspecsforallplatforms(Login,Logout&amp;DisplayMemberInformation)-Messages">Messages</h3>
<div class="table-wrap">
<table class="confluenceTable tablesorter tablesorter-default stickyTableHeaders">
<thead class="tableFloatingHeaderOriginal">
<tr class="tablesorter-headerRow">
<th class="confluenceTh sortableHeader" tabindex="0" colspan="1" data-column="0">
<div class="tablesorter-header-inner">
<div class="tablesorter-header-inner">ID</div>
</div></th>
<th class="confluenceTh sortableHeader" tabindex="0" data-column="1">
<div class="tablesorter-header-inner">
<div class="tablesorter-header-inner">
<div class="tablesorter-header-inner">Message</div>
</div>
</div></th>
<th class="confluenceTh sortableHeader" tabindex="0" data-column="2">
<div class="tablesorter-header-inner">
<div class="tablesorter-header-inner">When to display</div>
</div></th>
<th class="confluenceTh sortableHeader" tabindex="0" data-column="3">
<div class="tablesorter-header-inner">
<div class="tablesorter-header-inner">
<div class="tablesorter-header-inner">Type</div>
</div>
</div></th>
<th class="confluenceTh sortableHeader" tabindex="0" data-column="4">
<div class="tablesorter-header-inner">
<div class="tablesorter-header-inner">
<div class="tablesorter-header-inner">Comments</div>
</div>
</div></th>
</tr>
</thead>
<tbody>
<tr>
<td class="confluenceTd" colspan="1">1</td>
<td class="confluenceTd">Invalid status code: bad request (400)</td>
<td class="confluenceTd">
<ul>
	<li>When username is incorrect</li>
	<li>When password is incorrect</li>
	<li>When either username OR password is incorrect</li>
</ul>
</td>
<td class="confluenceTd">pop-up error</td>
<td class="confluenceTd">
<ul>
	<li>Currently the SDK returns the default error message received from the server.</li>
	<li>We can be customized later on.</li>
	<li>We are currently showing it as a pop-up, users can over ride that functionality to their own specification</li>
</ul>
</td>
</tr>
</tbody>
</table>
</div>
<h2 id="UserModule-JapanID-commonspecsforallplatforms(Login,Logout&amp;DisplayMemberInformation)-ExampleusageofUserLibraryinQAApp">Example usage of User Library in QA App</h2>
As a reference implementation of User Library, the Rakuten Mobile SDK team has provided an example implementation of it.

The reference implementation is called the QA App.
<h4 id="UserModule-JapanID-commonspecsforallplatforms(Login,Logout&amp;DisplayMemberInformation)-UserFlow1:Buildasampleinterface,whichallowsusertologinusingGMSORRogin">User Flow 1: Build a sample interface, which allows user to login using GMS OR Rogin</h4>
<div class="table-wrap">
<table class="confluenceTable tablesorter tablesorter-default stickyTableHeaders">
<thead class="tableFloatingHeaderOriginal">
<tr class="tablesorter-headerRow">
<th class="confluenceTh sortableHeader" tabindex="0" data-column="0">
<div class="tablesorter-header-inner"> User Action</div></th>
<th class="confluenceTh sortableHeader" tabindex="0" data-column="1">
<div class="tablesorter-header-inner">Screen Shot</div></th>
</tr>
</thead>
<tbody>
<tr>
<td class="confluenceTd">Step 1: User Launches th QA App</td>
<td class="confluenceTd"></td>
</tr>
<tr>
<td class="confluenceTd" colspan="1">Step 2: User chooses the QA Settings from menu</td>
<td class="confluenceTd" colspan="1"></td>
</tr>
<tr>
<td class="confluenceTd">Step 2: User chooses GMS / Rogin as login type</td>
<td class="confluenceTd"><span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img class="confluence-embedded-image confluence-external-resource" src="https://rakuten.atlassian.net/wiki/download/attachments/215374040/IMG_0180.PNG?version=1&amp;modificationDate=1422860338134&amp;api=v2" alt="" width="303" height="539" data-image-src="https://rakuten.atlassian.net/wiki/download/attachments/215374040/IMG_0180.PNG?version=1&amp;modificationDate=1422860338134&amp;api=v2" /></span></td>
</tr>
<tr>
<td class="confluenceTd">Step 3: User is asked to provide Rakuten ID &amp; Password (in interface shipped by Rakuten Mobile SDK)</td>
<td class="confluenceTd"><span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img class="confluence-embedded-image confluence-external-resource" src="https://rakuten.atlassian.net/wiki/download/attachments/215374040/IMG_0204.PNG?version=1&amp;modificationDate=1422860394146&amp;api=v2" alt="" width="278" height="495" data-image-src="https://rakuten.atlassian.net/wiki/download/attachments/215374040/IMG_0204.PNG?version=1&amp;modificationDate=1422860394146&amp;api=v2" /></span></td>
</tr>
<tr>
<td class="confluenceTd">Step 4: On successful login, the user is taken to next page
<ul>
	<li>It shows them User Information, which is similar in look &amp; feel as QA app</li>
</ul>
</td>
<td class="confluenceTd"></td>
</tr>
</tbody>
</table>
</div>
<h4 id="UserModule-JapanID-commonspecsforallplatforms(Login,Logout&amp;DisplayMemberInformation)-UserFlow2:UserProvidesInvalidUsernameORpassword">User Flow 2: User Provides Invalid Username OR password</h4>
<div class="table-wrap">
<table class="confluenceTable tablesorter tablesorter-default stickyTableHeaders">
<thead class="tableFloatingHeaderOriginal">
<tr class="tablesorter-headerRow">
<th class="confluenceTh sortableHeader" tabindex="0" data-column="0">
<div class="tablesorter-header-inner">User Action</div></th>
<th class="confluenceTh sortableHeader" tabindex="0" data-column="1">
<div class="tablesorter-header-inner">Screen Shot</div></th>
</tr>
</thead>
<tbody>
<tr>
<td class="confluenceTd">Step 1: On un-succesful Login
<ul>
	<li> An error message is shown.</li>
</ul>
</td>
<td class="confluenceTd"><span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img class="confluence-embedded-image confluence-external-resource" src="https://rakuten.atlassian.net/wiki/download/attachments/215374040/IMG_0214.PNG?version=1&amp;modificationDate=1422860589424&amp;api=v2" alt="" width="284" height="505" data-image-src="https://rakuten.atlassian.net/wiki/download/attachments/215374040/IMG_0214.PNG?version=1&amp;modificationDate=1422860589424&amp;api=v2" /></span></td>
</tr>
</tbody>
</table>
</div>
User Flow 3: User re-opens app &amp; had "Do not remember me" as OFF"
<div class="table-wrap">
<table class="confluenceTable tablesorter tablesorter-default stickyTableHeaders">
<thead class="tableFloatingHeaderOriginal">
<tr class="tablesorter-headerRow">
<th class="confluenceTh sortableHeader" tabindex="0" data-column="0">
<div class="tablesorter-header-inner">User Action</div></th>
<th class="confluenceTh sortableHeader" tabindex="0" data-column="1">
<div class="tablesorter-header-inner">Screen Shot</div></th>
</tr>
</thead>
<thead class="tableFloatingHeader">
<tr class="tablesorter-headerRow">
<th class="confluenceTh sortableHeader" tabindex="0" data-column="0">
<div class="tablesorter-header-inner">User Action</div></th>
<th class="confluenceTh sortableHeader" tabindex="0" data-column="1">
<div class="tablesorter-header-inner">Screen Shot</div></th>
</tr>
</thead>
<tbody>
<tr>
<td class="confluenceTd"> Step 1: Show the screen where user can:1: Login by clicking Red Button labeleed "Login as &lt;user's name&gt;"

2: Logout &amp; re-login by tapping button "Login with another account"</td>
<td class="confluenceTd"><span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img class="confluence-embedded-image confluence-external-resource" src="https://rakuten.atlassian.net/wiki/download/attachments/206605361/IMG_0215.PNG?version=1&amp;modificationDate=1422866678533&amp;api=v2" alt="" width="345" height="614" data-image-src="https://rakuten.atlassian.net/wiki/download/attachments/206605361/IMG_0215.PNG?version=1&amp;modificationDate=1422866678533&amp;api=v2" /></span></td>
</tr>
<tr>
<td class="confluenceTd" colspan="1">Step 2: If user chooses to login
<ul>
	<li>Show user information (like before)</li>
</ul>
&nbsp;</td>
<td class="confluenceTd" colspan="1"><span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img class="confluence-embedded-image confluence-external-resource" src="https://rakuten.atlassian.net/wiki/download/attachments/215374040/IMG_0181.PNG?version=2&amp;modificationDate=1422860481506&amp;api=v2" alt="" width="304" height="541" data-image-src="https://rakuten.atlassian.net/wiki/download/attachments/215374040/IMG_0181.PNG?version=2&amp;modificationDate=1422860481506&amp;api=v2" /></span></td>
</tr>
<tr>
<td class="confluenceTd" colspan="1">Step 3: If user chooses to logout
<ul>
	<li>Log them out of current account</li>
	<li>Take them to login page</li>
</ul>
</td>
<td class="confluenceTd" colspan="1"><span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img class="confluence-embedded-image confluence-external-resource" src="https://rakuten.atlassian.net/wiki/download/attachments/215374040/IMG_0204.PNG?version=1&amp;modificationDate=1422860394146&amp;api=v2" alt="" width="307" height="546" data-image-src="https://rakuten.atlassian.net/wiki/download/attachments/215374040/IMG_0204.PNG?version=1&amp;modificationDate=1422860394146&amp;api=v2" /></span></td>
</tr>
</tbody>
</table>
</div>
</div>