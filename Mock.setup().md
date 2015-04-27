<!-- API Specification -->

## Mock.setup( settings )

* Mock.setup( settings )

配置拦截 Ajax 请求时的行为。支持的配置项有：`timeout`。

### settings

必选。

配置项集合。

#### timeout

可选。

指定被拦截的 Ajax 请求的响应时间，单位是毫秒。值可以是正整数，例如 `400`，表示 400 毫秒 后才会返回响应内容；也可以是字符串，例如 `'200-600'`，表示响应时间介于 200 和 600 毫秒之间。默认值是`'10-100'`。

```js
Mock.setup({
	timeout: 400
})
Mock.setup({
	timeout: '200-600'
})
```

<!-- 共有 5 种参数格式。 -->

### Mock.mock( template )

根据数据模板生成模拟数据。

[JSFiddle](http://jsfiddle.net/nuysoft/Y3rg6/7/)

### Mock.mock( rurl, template )

记录数据模板。当拦截到匹配 `rurl` 的 Ajax 请求时，将根据数据模板 `template` 生成模拟数据，并作为响应数据返回。

[JSFiddle](http://jsfiddle.net/nuysoft/BeENf/6/)

### Mock.mock( rurl, function( options ) )

记录用于生成响应数据的函数。当拦截到匹配 `rurl` 的 Ajax 请求时，函数 `function(options)` 将被执行，并把执行结果作为响应数据返回。

[JSFiddle](http://jsfiddle.net/nuysoft/2s5t5/9/)

### Mock.mock( rurl, rtype, template )
    
记录数据模板。当拦截到匹配 `rurl` 和 `rtype` 的 Ajax 请求时，将根据数据模板 `template` 生成模拟数据，并作为响应数据返回。

[JSFiddle](http://jsfiddle.net/nuysoft/Eq68p/3/)

### Mock.mock( rurl, rtype, function( options ) )

记录用于生成响应数据的函数。当拦截到匹配 `rurl` 和 `rtype` 的 Ajax 请求时，函数 `function(options)` 将被执行，并把执行结果作为响应数据返回。

[JSFiddle](http://jsfiddle.net/nuysoft/6dpV5/5/)

<!-- **参数的含义和默认值**如下所示： -->

### rurl

可选。

表示需要拦截的 URL，可以是 URL 字符串或 URL 正则。例如 `/\/domain\/list\.json/`、`'/domian/list.json'`。

### rtype

可选。

表示需要拦截的 Ajax 请求类型。例如 `GET`、`POST`、`PUT`、`DELETE` 等。

### template

可选。

表示数据模板，可以是对象或字符串。例如 `{ 'data|1-10':[{}] }`、`'@EMAIL'`。

### function(options)

可选。

表示用于生成响应数据的函数。

#### options

指向本次请求的 Ajax 选项集。
