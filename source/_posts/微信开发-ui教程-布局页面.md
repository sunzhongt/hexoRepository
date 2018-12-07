---
title: 微信开发-ui教程-布局页面
date: 2018-12-02
cover: http://img4.imgtn.bdimg.com/it/u=1119919285,3827027875&fm=26&gp=0.jpg
categories: 微信开发
tags: 微信开发
---

#### ui教程-布局页面

flex布局

flex容器的属性
- flex-direction决定元素的排列方向
- flex-wrap决定元素如何换行
- flex-flow是 flex-wrap 和 flex-direction 的简写
- justify-contenty 元素在主轴上的对齐方式
- align-items元素在交叉轴的对齐方式


**flex-direction**  决定元素的排列方向--`容器`
- row (横线排列 横为主轴 竖为交叉轴) ==默认==
- column(纵线排列 横为交叉轴 竖为主轴)


**flex-wrap** 决定元素如何换行--`容器`
- nowrap (不换行 挤在一行 会变形 ) ==默认==
- wrap (多出换行 ) 
- wrap-reverse (将第一行放在下边 多出往上换行 )


 **flex-flow** 是 flex-wrap 和 flex-direction 的简写--`容器`
- row (横线排列 横为主轴 竖为交叉轴) ==默认==
- column(纵线排列 横为交叉轴 竖为主轴)
- nowrap (不换行 挤在一行 会变形 ) ==默认==
- wrap (多出换行 ) 
- wrap-reverse (将第一行放在下边 多出往上换行 )

```
.box{
    flex-flow:row wrap;
}
```


**justify-contenty** 元素在主轴上的对齐方式--`容器`

- center (元素在主轴上居中对齐) 
- flex-start(元素在主轴上居中对左)==默认== 
- flex-end (元素在主轴上居中对右) 
- space-around (元素在主轴上 两边多余的空间相等)【牙缝一样齐】 
- space-between (元素在主轴上 最左最右贴边  中间的两边多余的空间相等)【左中右很绝】 


**align-items** 元素在交叉轴上的对齐方式--`容器`

- center (元素在交叉轴上居中对齐) 
- flex-start(元素在交叉轴上从上往下)==默认== 
- flex-end (元素在交叉轴上从下往上) 
- stretch (在元素不设高的情况下  让元素的高与容器一样) 
- beasline (使元素的对齐方式与元素中文字的基线对齐) 
- space-around (元素在主轴上 两边多余的空间相等)【牙缝一样齐】 
- space-between (元素在主轴上 最左最右贴边  中间的两边多余的空间相等)【左中右很绝】 
---

flex==元素==的属性
- flex-grow当有多余空间的放大比例
- flex-shrink当空间不足时，元素的缩小比例
- flex-basis元素在主轴上的占据空间
- flex是grow shrink basis 的简写
- order定义元素的排列顺序
- align-self定义元素自身的对齐方式


**flex-grow** 当有多余空间的放大比例--`元素`
- 数字 (占总的几份) ==默认为0==

**flex-shrink** 当空间不足时(在一行上多个元素拥挤时，所有元素等比缩小)，元素的缩小比例，--`元素`
- 数字 ( 压缩的几份) ==默认为0 不变==

**flex** grow shrink basis 的简写，--`元素`
```css
item{
  flex:1 1 250px; 
}
```

**order** 定义元素的排列顺序--`元素`
- 数字 (写几就是第几个) 

**align-self** 定义元素自身的对齐方式--`元素`

- align-items一样