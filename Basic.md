<!-- ## Basic -->

## Random.boolean( min, max, current )

* Random.boolean()
* Random.boolean( min, max, current )

返回一个随机的布尔值。

<!-- **参数的含义和默认值**如下所示： -->

### min

可选。

指示参数 current 出现的概率。概率计算公式为 `min / (min + max)`。该参数的默认值为 1，即有 50% 的概率返回参数 current。

### max

可选。

指示参数 current 的相反值 !current 出现的概率。概率计算公式为 `max / (min + max)`。该参数的默认值为 1，即有 50% 的概率返回参数 !current。

### current

可选。

可选值为布尔值 true 或 false。如果未传入任何参数，则返回 true 和 false 的概率各为 50%。该参数没有默认值。在该方法的内部，依据原生方法 Math.random() 返回的（浮点）数来计算和返回布尔值，例如在最简单的情况下，返回值是表达式 `Math.random() >= 0.5` 的执行结果。

<!-- **使用示例**如下所示： -->

```js
Random.boolean()
// => true
Random.boolean(1, 9, true)
// => false
Random.bool()
// => false
Random.bool(1, 9, false)
// => true
```

<!-- 事实上，原生方法 Math.random() 返回的随机（浮点）数的分布并不均匀，是货真价实的伪随机数，将来会替换为基于 ？？ 来生成随机数。?? 对 Math.random() 的实现机制进行了分析和统计，并提供了随机数的参考实现，可以访问[这里](http://??)。
TODO 统计 -->

## Random.natural( min, max )

* Random.natural()
* Random.natural( min )
* Random.natural( min, max )

返回一个随机的自然数（大于等于 0 的整数）。

<!-- **参数的含义和默认值**如下所示： -->

### min

可选。

指示随机自然数的最小值。默认值为 0。

### max

可选。

指示随机自然数的最大值。默认值为 9007199254740992。

<!-- **使用示例**如下所示： -->

```js
Random.natural()
// => 1002794054057984
Random.natural(10000)
// => 71529071126209
Random.natural(60, 100)
// => 77
```

## Random.integer( min, max )

* Random.integer()
* Random.integer( min )
* Random.integer( min, max )

返回一个随机的整数。

<!-- **参数的含义和默认值**如下所示： -->

### min

可选。

指示随机整数的最小值。默认值为 -9007199254740992。

### max

可选。

指示随机整数的最大值。默认值为 9007199254740992。

<!-- **使用示例**如下所示： -->

```js
Random.integer()
// => -3815311811805184
Random.integer(10000)
// => 4303764511003750
Random.integer(60,100)
// => 96
```

## Random.float( min, max, dmin, dmax )

* Random.float()
* Random.float( min )
* Random.float( min, max )
* Random.float( min, max, dmin )
* Random.float( min, max, dmin, dmax )

返回一个随机的浮点数。

<!-- **参数的含义和默认值**如下所示： -->

### min

可选。

整数部分的最小值。默认值为 -9007199254740992。

### max

可选。

整数部分的最大值。默认值为 9007199254740992。

### dmin

可选。

小数部分位数的最小值。默认值为 0。

### dmin

可选。

小数部分位数的最大值。默认值为 17。


<!-- **使用示例**如下所示： -->

```js
Random.float()
// => -1766114241544192.8
Random.float(0)
// => 556530504040448.25
Random.float(60, 100)
// => 82.56779679549358
Random.float(60, 100, 3)
// => 61.718533677927894
Random.float(60, 100, 3, 5)
// => 70.6849
```

## Random.character( pool )

* Random.character()
* Random.character( 'lower/upper/number/symbol' )
* Random.character( pool )

返回一个随机字符。

<!-- **参数的含义和默认值**如下所示： -->

### pool

可选。

字符串。表示字符池，将从中选择一个字符返回。

如果传入了 `'lower'` 或 `'upper'`、`'number'`、`'symbol'`，表示从内置的字符池从选取：

```js
{
    lower: "abcdefghijklmnopqrstuvwxyz",
    upper: "ABCDEFGHIJKLMNOPQRSTUVWXYZ",
    number: "0123456789",
    symbol: "!@#$%^&*()[]"
}
```

如果未传入该参数，则从 `lower + upper + number + symbol` 中随机选取一个字符返回。

<!-- **使用示例**如下所示： -->

```js
Random.character()
// => "P"
Random.character('lower')
// => "y"
Random.character('upper')
// => "X"
Random.character('number')
// => "1"
Random.character('symbol')
// => "&"
Random.character('aeiou')
// => "u"
```

## Random.string( pool, min, max )

* Random.string()
* Random.string( length )
* Random.string( pool, length )
* Random.string( min, max )
* Random.string( pool, min, max )

返回一个随机字符串。

<!-- **参数的含义和默认值**如下所示： -->

### pool

可选。

字符串。表示字符池，将从中选择一个字符返回。

如果传入 `'lower'` 或 `'upper'`、`'number'`、`'symbol'`，表示从内置的字符池从选取：
  
```js  
{
    lower: "abcdefghijklmnopqrstuvwxyz",
    upper: "ABCDEFGHIJKLMNOPQRSTUVWXYZ",
    number: "0123456789",
    symbol: "!@#$%^&*()[]"
}
```

如果未传入该参数，则从 `lower + upper + number + symbol` 中随机选取一个字符返回。

### min

可选。

随机字符串的最小长度。默认值为 3。

### max

可选。

随机字符串的最大长度。默认值为 7。

<!-- **使用示例**如下所示： -->

```js
Random.string()
// => "pJjDUe"
Random.string( 5 )
// => "GaadY"
Random.string( 'lower', 5 )
// => "jseqj"
Random.string( 7, 10 )
// => "UuGQgSYk"
Random.string( 'aeiou', 1, 3 )
// => "ea"
Random.string( '壹贰叁肆伍陆柒捌玖拾', 3, 5 )
// => "肆捌伍叁"
```

## Random.range( start, stop, step )

* Random.range( stop )
* Random.range( start, stop )
* Random.range( start, stop, step )

返回一个整型数组。

<!-- **参数的含义和默认值**如下所示： -->

### start

必选。

数组中整数的起始值。

### stop

可选。

数组中整数的结束值（不包含在返回值中）。

### step

可选。

数组中整数之间的步长。默认值为 1。

<!-- **使用示例**如下所示： -->

```js
Random.range(10)
// => [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
Random.range(3, 7)
// => [3, 4, 5, 6]
Random.range(1, 10, 2)
// => [1, 3, 5, 7, 9]
Random.range(1, 10, 3)
// => [1, 4, 7]
```

<!-- ## Datetime -->

## Random.date( format )

* Random.date()
* Random.date(format)

返回一个随机的日期字符串。

<!-- **参数的含义和默认值**如下所示： -->

### format

可选。

指示生成的日期字符串的格式。默认值为 `yyyy-MM-dd`。

可选的占位符参考自 [Ext.Date](http://docs.sencha.com/ext-js/4-1/#!/api/Ext.Date)，如下所示：

| Format  | Description                                                 | Example
| ------- | ----------------------------------------------------------- | --------------
| yyyy    | A full numeric representation of a year, 4 digits           | 1999 or 2003
| yy      | A two digit representation of a year                        | 99 or 03
| y       | A two digit representation of a year                        | 99 or 03
| MM      | Numeric representation of a month, with leading zeros       | 01 to 12
| M       | Numeric representation of a month, without leading zeros    | 1 to 12
| dd      | Day of the month, 2 digits with leading zeros               | 01 to 31
| d       | Day of the month without leading zeros                      | 1 to 31
| HH      | 24-hour format of an hour with leading zeros                | 00 to 23
| H       | 24-hour format of an hour without leading zeros             | 0 to 23
| hh      | 12-hour format of an hour without leading zeros             | 1 to 12
| h       | 12-hour format of an hour with leading zeros                | 01 to 12
| mm      | Minutes, with leading zeros                                 | 00 to 59
| m       | Minutes, without leading zeros                              | 0 to 59
| ss      | Seconds, with leading zeros                                 | 00 to 59
| s       | Seconds, without leading zeros                              | 0 to 59
| SS      | Milliseconds, with leading zeros                            | 000 to 999
| S       | Milliseconds, without leading zeros                         | 0 to 999
| A       | Uppercase Ante meridiem and Post meridiem                   | AM or PM
| a       | Lowercase Ante meridiem and Post meridiem                   | am or pm
| T       | Milliseconds, since 1970-1-1 00:00:00 UTC                   | 759883437303

<!-- **使用示例**如下所示： -->

```js
Random.date()
// => "2002-10-23"
Random.date('yyyy-MM-dd')
// => "1983-01-29"
Random.date('yy-MM-dd')
// => "79-02-14"
Random.date('y-MM-dd')
// => "81-05-17"
Random.date('y-M-d')
// => "84-6-5"
```

## Random.time( format )

* Random.time()
* Random.time( format )

返回一个随机的时间字符串。

<!-- **参数的含义和默认值**如下所示： -->

### format

可选。

指示生成的时间字符串的格式。默认值为 `HH:mm:ss`。可选的占位符参考自 [Ext.Date](http://docs.sencha.com/ext-js/4-1/#!/api/Ext.Date)，请参见 [Random.date(format)](#date)。

<!-- **使用示例**如下所示： -->
    
```js
Random.time()
// => "00:14:47"
Random.time('A HH:mm:ss')
// => "PM 20:47:37"
Random.time('a HH:mm:ss')
// => "pm 17:40:00"
Random.time('HH:mm:ss')
// => "03:57:53"
Random.time('H:m:s')
// => "3:5:13"
```

## Random.datetime( format )

* Random.datetime()
* Random.datetime( format )

返回一个随机的日期和时间字符串。

<!-- **参数的含义和默认值**如下所示： -->

### format

可选。

指示生成的日期和时间字符串的格式。默认值为 `yyyy-MM-dd HH:mm:ss`。可选的占位符参考自 [Ext.Date](http://docs.sencha.com/ext-js/4-1/#!/api/Ext.Date)，请参见 [Random.date( format )](#date)。

<!-- **使用示例**如下所示： -->

```js
Random.datetime()
// => "1977-11-17 03:50:15"
Random.datetime('yyyy-MM-dd A HH:mm:ss')
// => "1976-04-24 AM 03:48:25"
Random.datetime('yy-MM-dd a HH:mm:ss')
// => "73-01-18 pm 22:12:32"
Random.datetime('y-MM-dd HH:mm:ss')
// => "79-06-24 04:45:16"
Random.datetime('y-M-d H:m:s')
// => "02-4-23 2:49:40"
```

## Random.now(unit, format)

* Ranndom.now(unit, format)
* Ranndom.now()
* Ranndom.now(format)
* Ranndom.now(unit)

返回当前的日期和时间字符串。

<!-- **参数的含义和默认值**如下所示： -->

### unit

可选。

表示时间单位，用于对当前日期和时间进行格式化。可选值有：`year`、`month`、`week`、`day`、`hour`、`minute`、`second`、`week`，默认不会格式化。

### format

可选。

指示生成的日期和时间字符串的格式。默认值为 `yyyy-MM-dd HH:mm:ss`。可选的占位符参考自 [Ext.Date](http://docs.sencha.com/ext-js/4-1/#!/api/Ext.Date)，请参见 [Random.date(format)](#date)。

> `Random.now()` 的实现参考了 [Moment.js](http://momentjs.cn/docs/#/manipulating/start-of/)。

<!-- **使用示例**如下所示： -->
    
```js
Random.now()
// => "2014-04-29 20:08:38 "
Random.now('day', 'yyyy-MM-dd HH:mm:ss SS')
// => "2014-04-29 00:00:00 000"
Random.now('day')
// => "2014-04-29 00:00:00 "
Random.now('yyyy-MM-dd HH:mm:ss SS')
// => "2014-04-29 20:08:38 157"

Random.now('year')
// => "2014-01-01 00:00:00"
Random.now('month')
// => "2014-04-01 00:00:00"
Random.now('week')
// => "2014-04-27 00:00:00"
Random.now('day')
// => "2014-04-29 00:00:00"
Random.now('hour')
// => "2014-04-29 20:00:00"
Random.now('minute')
// => "2014-04-29 20:08:00"
Random.now('second')
// => "2014-04-29 20:08:38"
```