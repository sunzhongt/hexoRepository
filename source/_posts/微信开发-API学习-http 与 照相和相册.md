---
title: 微信开发-API学习
date: 2018-10-11
cover: https://img02.sogoucdn.com/app/a/100520093/b692ca88cf40622d-c4c351c548f54192-9b31be1c6e33db79adc5f293470100b2.jpg
categories: categories
tags: 微信开发-API学习
---

#### 微信开发-API学习

- [wx.request(object)](https://developers.weixin.qq.com/miniprogram/dev/api/network/request/wx.request.html)发起 HTTPS 网络请求

```js
wx.request({
  url: 'test.php', //仅为示例，并非真实的接口地址
  data: {
    x: '',
    y: ''
  },
  header: {
    'content-type': 'application/json' // 默认值
  },
  success (res) {
    console.log(res.data)
  }
})
```

属性|	类型|	默认值|	是否必填|	说明|	支持版本|
--|--|--|--|--|--|--
url|string|	|	是	|开发者服务器接口地址	
data|string/object/ArrayBuffer|	|	否	|请求的参数	
header|	Object	||	否|	设置请求的 header，header 中不能设置 Referer。 `content-type 默认为 application/json`	
method|	string|	GET|	否	|HTTP 请求方法	
dataType|	string|	json|	否|	返回的数据格式	
responseType|	string	|text|	否|	响应的数据类型	|>= 1.7.0
success|	function	||	否|	接口调用成功的回调函数	
fail|	function	||	否|	接口调用失败的回调函数	
complete|	function|	|	否|	接口调用结束的回调函数（调用成功、失败都会执行）


object.method 的合法值

值|	说明|
--|--
OPTIONS|	HTTP 请求 OPTIONS
GET	HTTP |请求 GET
HEAD|	HTTP 请求 HEAD
POST|	HTTP 请求 POST
PUT	|HTTP 请求 PUT
DELETE|	HTTP 请求 DELETE
TRACE|	HTTP 请求 TRACE
CONNECT|	HTTP 请求 CONNECT

object.dataType 的合法值

值|	说明
--|--
json|	返回的数据为 JSON，返回后会对返回的数据进行一次 JSON.parse
其他|	不对返回的内容进行 JSON.parse

object.responseType 的合法值

值|	说明
--|--
text|	响应的数据为文本
arraybuffer	|响应的数据为 ArrayBuffer

Object res

属性|	类型|说明|支持版本|
--|--|--|--
data|	string/Object/Arraybuffer|	开发者服务器返回的数据
statusCode|	number|	开发者服务器返回的 HTTP 状态码	
header	|Object	|开发者服务器返回的 HTTP Response Header|	>= 1.2.0


- [wx.chooseImage(Object)](https://developers.weixin.qq.com/miniprogram/dev/api/media/image/wx.chooseImage.html)从本地相册选择图片或使用相机拍照

参数 Object 

属性|	类型|	默认值	|是否必填	|说明|	支持版本
--|--|--|--|--|--
count|	number|	9|	否|	最多可以选择的图片张数	
sizeType|	Array.<string>|	['original', 'compressed']|	否|	所选的图片的尺寸	
sourceType|	Array.<string>	|['album', 'camera']|	否|	选择图片的来源	
success	|function	||	否|	接口调用成功的回调函数	
fail|	function	||	否	|接口调用失败的回调函数	
complete|	function	||	否|	接口调用结束的回调函数（调用成功、失败都会执行）

object.sizeType 的合法值

值|	说明
--|--
original|	原图
compressed|	压缩图

object.sourceType 的合法值

值|	说明
--|--
album|	从相册选图
camera|	使用相机

object.success 回调函数
参数

Object res

属性|	类型|	说明|	支持版本
--|--|--|--
tempFilePaths|	Array.<string>	|图片的本地临时文件路径列表	
tempFiles|	Array.<Object>	|图片的本地临时文件列表|	>= 1.2.0

res.tempFiles 的结构

属性|	类型|	说明|	支持版本
--|--|--|--
path|	string|	本地临时文件路径	
size|	number	|本地临时文件大小，单位 B

示例代码
```js
wx.chooseImage({
  count: 1,
  sizeType: ['original', 'compressed'],
  sourceType: ['album', 'camera'],
  success (res) {
    // tempFilePath可以作为img标签的src属性显示图片
    const tempFilePaths = res.tempFilePaths
  }
})
```