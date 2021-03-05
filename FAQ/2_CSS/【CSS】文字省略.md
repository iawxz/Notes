# 【CSS】文字省略

做网页的时候，为了不让文字溢出影响页面结构，经常会遇到要文字省略的情况。如下：

![](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/4e67dd97bdae481cb6a0a32a8e6d941b~tplv-k3u1fbpfcp-watermark.image)

简单地用CSS即可实现。

#### 单行文字省略(如上图中标题显示)：
```css
text-overflow: ellipsis;
overflow: hidden;
white-space: nowrap;
```

#### 多行文字省略(如上图中文章显示)：
```css
overflow: hidden;
-webkit-line-clamp: 3; 
-webkit-box-orient: vertical;
display: -webkit-box;
```