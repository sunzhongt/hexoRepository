---
title: 微信开发-App的生命周期及App对象的使用
date: 2018-12-01
cover: http://img4.imgtn.bdimg.com/it/u=1119919285,3827027875&fm=26&gp=0.jpg
categories: 微信开发
tags: 微信开发 
---


#### 微信开发-App的生命周期及App对象的使用

- [App的生命周期]()
- [App对象的使用]()

App的生命周期

 序号  |  名称     |   周期
 ---   |  ---      |   ---
   1   |  onLaunch |   初始化
   2   |  onShow   |   页面显示（前台）
   3   |  onload   |   页面加载完成
   4   |  onHide   |   页面消失（后台）
```js
App({
    //初始化
    onLaunch:function(){
        
    },
    //页面显示（前台）
     onShow:function(){
        
    },
    //页面加载完成
     onload:function(){
        
    },
    //页面消失（后台）
     onHide:function(){
        
    },
})
```
App对象的使用
 ```
 //获取应用实例
const app = getApp()

app.xxxx.xxx 
//or
app.xxx('xxx');

 ```

 页面的生命周期

![image](https://github.com/sunzhongt/imgData/blob/master/mdImg/WX%E9%A1%B5%E9%9D%A2%E7%94%9F%E5%91%BD%E5%91%A8%E6%9C%9F.png?raw=true)



