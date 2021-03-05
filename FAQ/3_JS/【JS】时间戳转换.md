# 【JS】时间戳转换

## 时间转换成时间戳
##### 获取当前时间的时间戳
```JavaScript
var now_timestamp = Date.parse(new Date());
```

##### 各单位时间的时间戳
官方对时间戳的定义是，一种时间表示方式，从格林威治时间1970年01月01日00时00分00秒起至现在的总秒数。我用js获取时间戳，打印输出来看是保留了末尾000的毫秒数，为了方便一些计算，我用毫秒数来存各单位时间戳的值；
```JavaScript
var minute_timestamp = 60 * 1000; 			//1分钟
var day_timestamp = 24 * 60 * 60 * 1000; 		//1天
var week_timestamp = day_timestamp * 7; 		//7天
```
##### 已有时间转时间戳

```JavaScript
var get_timestamp = (new Date("2020/12/24 11:59:59")).getTime()
```
getTime()返回数值的单位是毫秒；

## 时间戳转换成时间
##### 对当前时间的时间戳time进行转换；

```JavaScript
//now_timestamp是整数，否则需要parseInt转换
var time = new Date(now_timestamp);
```
##### 年月日的转换(格式xxxx年xx月xx日)
几个api，getFullYear()、getMonth()、getDate()；
```JavaScript
//年
var year = time.getFullYear().toString();
//月，小于10的默认在前面加一个0
var month = (time.getMonth() + 1).toString();
if (month.length < 2) {month = "0" + month;}
//日，小于10的默认在前面加一个0
var day = time.getDate().toString();
if (day.length < 2) {day = "0" + day;}
```
##### 星期几的转换
通过getDay()可以获取到数据，星期天-星期六(0-6)；
```JavaScript
var weekdays = ["星期天","星期一","星期二","星期三","星期四","星期五","星期六",];
var weekday = time.getDay().toString();
```

