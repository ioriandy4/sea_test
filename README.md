# sea_test
测试模块合并

我在html里面有以下调用代码：
```javascript
seajs.config({
  base:'./modules/',
  alias:{}
});

seajs.use(['all/a', 'all/b'], function(a, b) {
    alert(a); //undefined
    alert(b); //undefined
});
```
在moudels文件夹下有all文件夹，all文件夹有all.js，代码如下
```javascript
define('all/a',function(require,exports,module){
    module.exports=10;

});

define('all/b',function(require,exports,module){
    module.exports=20;
});
```
为什么我all.js每个模块都定义了id，还是use不到接口a和接口b呢？？应该怎么use合并后all.js的文件啊？
页面报错：
```javascript
...seajs/module_test/events_transfer_hb/modules/all/a.js net::ERR_FILE_NOT_FOUND
...seajs/module_test/events_transfer_hb/modules/all/b.js net::ERR_FILE_NOT_FOUND
```
怎么会当作路径来处理了呢？不是说id对了，就可以引用吗？

