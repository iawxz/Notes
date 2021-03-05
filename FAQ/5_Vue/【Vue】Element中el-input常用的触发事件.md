# 【Vue】Element中el-input常用的触发事件

![img](https://user-gold-cdn.xitu.io/2020/6/18/172c5182c3c23cdb?imageView2/0/w/1280/h/960/format/webp/ignore-error/1)

## @change

一个input标签，想要键入时触发事件，自然而然最先想到常用的change事件。

```html
<el-input placeholder="搜索名称/订单编号" v-model="searchInfo" clearable @change="search">
    <i slot="prefix" class="el-input__icon el-icon-search"></i>
</el-input>
```

```js
// 获取搜索内容
search(){
    console.log(this.searchInfo)
},
```

键入后发现，控制台并没有打印出数据：

![img](https://user-gold-cdn.xitu.io/2020/6/18/172c524a8112f940?imageView2/0/w/1280/h/960/format/webp/ignore-error/1)

查过资料后才发现**element中el-input的change事件是移除焦点才触发的**，那想要实现每键入一个字符都触发一次事件怎么办呢？

## @input

暂时的解决方案是input事件，js内容不变继续输出和el-input绑定的值。

```html
<el-input placeholder="搜索名称/订单编号" v-model="searchInfo" clearable @input="search">
    <i slot="prefix" class="el-input__icon el-icon-search"></i>
</el-input>
```

![img](https://user-gold-cdn.xitu.io/2020/6/18/172c535fd716cbdd?imageView2/0/w/1280/h/960/format/webp/ignore-error/1)

![img](https://user-gold-cdn.xitu.io/2020/6/18/172c5363a11bcafd?imageView2/0/w/1280/h/960/format/webp/ignore-error/1)

