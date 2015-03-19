# 用法

### Node (CommonJS)

```shell
# 安装
npm install mockjs
```
   
```js
// 使用 Mock
var Mock = require('mockjs')
var data = Mock.mock({
    'list|1-10': [{
        'id|+1': 1
    }]
})
// 输出结果
console.log(JSON.stringify(data, null, 4))
```

### Bower

<!-- If you'd like to use [bower](http://bower.io/), it's as easy as: -->

```shell    
# 安装
npm install -g bower
bower install --save mockjs
```

```html    
<script type="text/javascript" src="./bower_components/mockjs/dist/mock.js"></script>
```

### RequireJS (AMD)

```js
// 配置 Mock 路径
require.config({
  paths:{
    'mock':'http://mockjs.com/dist/mock'
  }
})
// 加载 Mock
require(['mock'], function(Mock){
    // 使用 Mock
    var data = Mock.mock({
        'list|1-10': [{
            'id|+1': 1
        }]
    })
    // 输出结果
    $('<pre>').text(JSON.stringify(data, null, 4))
        .appendTo('body')
})
```

[JSFiddle](http://jsfiddle.net/uTSqT/3/)

### Sea.js (CMD)

```js
// 配置 Mock 路径
seajs.config({
  alias: {
    "mock": "http://mockjs.com/dist/mock.js"
  }
})

// 加载 Mock
seajs.use('mock', function(Mock){
    // 使用 Mock
    var data = Mock.mock({
        'list|1-10': [{
            'id|+1': 1
        }]
    })
    // 输出结果
    $('<pre>').text(JSON.stringify(data, null, 4))
        .appendTo('body')
})
```

[JSFiddle](http://jsfiddle.net/5jX6e/2/)


<!-- ### KISSY

```js
// 配置 Mock 路径
KISSY.config({
    packages: {
        mock: {
            base: 'http://mockjs.com/dist/'
        }
    }
})
// 加载 Mock
KISSY.use(['node', 'mock'], function (S, _, Mock) {
    // 使用 Mock
    var data = Mock.mock({
        'list|1-10': [{
            'id|+1': 1
        }]
    })
    // 输出结果
    KISSY.all('<pre>').text(JSON.stringify(data, null, 4))
        .appendTo('body')
})
```

[JSFiddle](http://jsfiddle.net/En2sX/2/) -->


### Random CLI

    // 全局安装
    npm install mockjs -g

    // 执行
    $ random url
    // => http://rmcpx.org/funzwc

    // 帮助
    random -h

---