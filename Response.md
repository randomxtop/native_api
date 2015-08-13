Two returned text format: json and xml, developers can obtain the appropriate format based on the needs of their own programs, developers need to pass parameters restype, json is default format returned.    
Returned content includes following parameters:    
<table>
<tbody>
<tr><td><em><b>Field</b></em></td><td><em><b>Description</b></em></td><td><em><b>Example</b></em></td>
<tr><td>status</td><td>Status code</td><td>1</td>
<tr><td>describe</td><td>The description of the status</td><td>success</td>
<tr><td>data</td><td>The ads data, it is an array</td><td> </td>
</tbody>
</table>

A node of the <b>data</b> 
<table>
<tbody>
<tr><td><em><b>Field</b></em></td><td><em><b>Description</b></em></td>
<tr><td>id</td><td>unique id of data</td>
<tr><td>title</td><td>title of the app</td>
<tr><td>desc</td><td>desccription of the app</td>
<tr><td>package_name</td><td>package name of the app</td>
<tr><td>icon_url</td><td>icon of the app</td>
<tr><td>image_url</td><td>image of the app</td>
<tr><td>click_url</td><td> URL that have to be requested when the ad is clicked(Normally, it returns 302). <br>Note: The expiration time for click_url is 1 hour.</td>
<tr><td>impression_url</td><td>URL that have to be requested when the ad is displayed. <br>Note: The expiration time for click_url is 1 hour.</td></td>
<tr><td>notice_url</td><td>URL that have to be requested to notice us the ad is clicked. Note: The server needs to receive notification http code of 2xx or 3xx, which is considered successful, otherwise retry until successful notified.</td>
<tr><td>pre_click</td><td>whether allow pre click</td>
</tbody>
</table>


***

JSON Response Example    
```java
{
  "status": 1,
  "msg": "success",
  "data": [
  {
    "id":1,
    "title": "APUS Launcher-Small,Fast,Boost",
    "desc": "5-stars rated over 1 million, and installed on over 90 million devices in over 235 countries.",
    "package_name": "com.apusapps.launcher",
    "icon_url": "http://d11kdtiohse1a9.cloudfront.net/common/2015/01/23/142199355187006.png",
    "image_url": "",
    "impression_url": "http://127.0.0.1/adn_net/impression?token=54f6a22273a9f6580a000971&sign=tXWo8YoZf7306714&timestamp=1425449503",
    "click_url": "http://127.0.0.1/adn_net/click?token=54f6a22273a9f6580a000981&sign=aAavDASV4a06225f&timestamp=1425449503&cid=2138&aid=1",
    "notice_url": "",
    "pre_click": true
  },
  {
    "id":2,
    "title": "Mico",
    "desc": "Mico provides you the most SIMPLE and RELIABLE way to chat with strangers and meet new friends.",
    "package_name": "com.mico",
    "icon_url": "http://d11kdtiohse1a9.cloudfront.net/common/2015/02/12/142373089166901.png",
    "image_url": "",
    "impression_url": "http://127.0.0.1/adn_net/impression?token=54f6a22273a9f6580a000991&sign=9KVU5YSJ087a605c&timestamp=1425449503",
    "click_url": "http://127.0.0.1/adn_net/click?token=54f6a22273a9f6580a0009b1&sign=uuhFH57Rd215c8a0&timestamp=1425449503&cid=2604&aid=1",
    "notice_url": ""
    "pre_click": false
  }
  ]
}
```