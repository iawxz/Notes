# 【MP】button控件的边框隐藏

原生微信小程序开发过程中，遇到一个button边框不能隐藏的问题。

button控件有一条淡灰色的边框，在控件上了添加了隐藏边框的样式依然无法使button边框隐藏。

![img](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/9cdd7d448f60422b9f4678c9a15a35be~tplv-k3u1fbpfcp-zoom-1.image)

```css
/* 客服中心button样式 */
.item-text-CSC{
	background:transparent;
    padding:0;
    margin:0;
    /* 下面三条隐藏边框的样式都无效 */
    /* boder:0; */
    /* boder:none; */
    /* border:transparent; */
}
```

找了点资料，原来微信小程序中button的边框是加在::after上的，在button这个伪元素中默认有一条这样的样式：

```css
border:1px solid rgba(0,0,0,0.2);
```

**找到原因那就好办了**

```css
/* 客服中心button样式 */
.item-text-CSC{
	background:transparent;
    padding:0;
    margin:0;
}

.item-text-CSC::after{
	/* 下面三条隐藏边框的样式都能生效 */
    /* boder:0; */
    /* boder:none; */
    border:transparent;
}
```

![img](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/949ddb15a1d1474d91af7839454e1c1f~tplv-k3u1fbpfcp-zoom-1.image)

实现了button控件的边框隐藏。