<table style="table-layout:fixed">
<tbody>
<tr><td><em><b>Parameter</b></em></td><td><em><b>Type</b></em></td><td><em><b>Required?</b></em></td><td><em><b>Description</b></em></td></tr>

<tr><td>sign</td><td>string</td><td>Yes</td><td style="word-break:break-all"><b>Mandatory.</b> Uniquely identifies the publisher, which is a 32-bit encryption string. 
md5(appId+apiKey)<br><b>Example: </b>sign=8b74bgdf992e13e1ef0f70d72a35c6d2</td></tr>

<tr><td>app_id</td><td>int</td><td>Yes</td><td style="word-break:break-all"><b>Mandatory.</b> Uniquely identifies which app/site is integrated.
ID generated after publisher add an app or site.<br><b>Example: </b>appId=123</td></tr>

<tr><td>unit_id</td><td>int</td><td>Yes</td><td style="word-break:break-all"><b>Mandatory.</b> Ad unit id, unique identifier of ad placement. <br><b>Example: </b>unit_id=12345</td></tr>

<tr><td>client_ip</td><td>string</td><td>Yes</td><td style="word-break:break-all">The IP address of the device requesting the ad. 
The parameter is not necessary, but if you pass on it, it must be the public IP, and not a LAN IP. 
If your execution context is a server, you Should use X_FORWARD_FOR (if present) or REMOTE_ADDR header values you got from the client request.<br>
<b>Example: </b>clientIp=69.41.253.50</td></tr>
<tr><td>platform</td><td>Int</td><td>Yes</td><td>1-Android, 2-Ios</td></tr>
<tr><td>os_version</td><td>String</td><td>Yes</td><td>System version, Example: 4.4.2</td></tr>
<tr><td>package_name</td><td>String</td><td>Yes</td><td>package name</td></tr>
<tr><td>app_version_code</td><td>Int</td><td>Yes</td><td>app version code</td></tr>
<tr><td>android_id</td><td>String</td><td>Yes</td><td>android id</td></tr>
<tr><td>model</td><td>String</td><td>Yes</td><td>device model, Example: GT-9505</td></tr>
<tr><td>screen_size</td><td>String</td><td>Yes</td><td>screen size , Example: 1920x1080</td></tr>
<tr><td>orientation</td><td>Int</td><td>Yes</td><td>1-Vertical，2-Horizontal</td></tr>
<tr><td>mnc</td><td>String</td><td>Yes</td><td>Mobile Network Code, Example: 00</td></tr>
<tr><td>mcc</td><td>String</td><td>Yes</td><td>Mobile Country Code, Example: 460</td></tr>
<tr><td>network_type</td><td>Int</td><td>Yes</td><td>network_type：2 = 2G;3 = 3G;4 = 4G;9 = WIFI & lan</td></tr>
<tr><td>language</td><td>String</td><td>Yes</td><td>system language, Example: zh-TW</td></tr>
<tr><td>timezone</td><td>String</td><td>Yes</td><td>timezone</td></tr>
<tr><td>image_size</td><td>Int</td><td>No</td><td>image size list, which is limited to the following values:<br>
2: 320x50(banner)<br>
3: 300x250<br>
4: 480x320(horizontal  cover)<br>
5: 320x480(vertical  cover)<br>
6: 300x300(big Icon)<br>
<b>Example: </b>image_size=4</td></tr>

<tr><td>useragent</td><td>string</td><td>No</td style="word-break:break-all"><td>The browser's user agent of the device, valid URL-encoded String, highly recommended.<br><b>Example: </b>ua=Mozilla/5.0%20(Linux;%20U;%20Android%204.2.2;%20zh-tw;%20Nexus%207%20Build/JDQ39)%20AppleWebKit/534.30%20(KHTML,%20like%20Gecko)%20Version/4.0%20Safari/534.30</td></tr>

<tr><td>category</td><td>int</td><td>No</td><td>Category of the ads:<br>
1: Game app<br>
2: Utility app<br>
If null, then ads can be game app or utility app<br>
<b>Example: </b>category=1</td>

<tr><td>ad_num</td><td>int</td><td>No</td><td>Number of ads:<br>
Max: 15<br>
Min: 1<br>
<b>Example: </b>ad_num=1</td></tr>

<tr><td>ping_mode</td><td>int</td><td>No</td>
<td style= " WORD-WRAP:   break-word">If ping_mode == 1, two urls will be returned.<br>
1) Click_url: return to us when the user clicks on the ad<br>
2) notice_url: notify us when the user clicks on the ad, but which can accelerate the redirect speed by reducing one jump.<br></td></tr>

<tr><td>imei</td><td>String</td><td>No</td><td>imei</td></tr>
<tr><td>mac</td><td>String</td><td>No</td><td>mac</td></tr>
<tr><td>gaid</td><td>String</td><td>No</td><td>Google Advertising ID</td></tr>
</tbody>
</table>

> **IMPORTANT:** All our API parameters are case sensitive. Wrong use of upper or lower case characters in any of the parameters name will cause our ad-server to ignore that parameter completely.

> **ping_mode Explanation:** 
Request: Client request->Your server->Native server (realtime-API)
Return: realtime API->clickURL(provided by upstream, maybe the download
URL of the app)&noticeURL(for tracking)-> Your server directly redirect to
clickURL, at the same time, Your server call the noticeURL in the background
process for tracking.