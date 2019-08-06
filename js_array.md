##### 检测数组（detect arrray）
1. 原生方法，（iframes中的数组也可以检测）
``` javascript
function isArray(data) {
  if(!Array.isArray) {
    return Object.prototype.toString.call(data) === '[object Array]';
  }
  return Array.isArray(data);
}
```
2. 像数组所以是数组
``` javascript
function isArray(data) {
  return Boolean(data) && (typeof data.length === 'number') && (typeof data.push === 'function');
}
```

*以下方法不支持iframes页面嵌套情况（每个页面的constructor/prototype 是独立不共享的）*

3. 
``` javascript
function isArray(data) {
  return Boolean(constructor) && data.constructor === Array;
}
```
4. 
``` javascript
function isArray(data) {
  return data instanceof Array;
}
```

[MDN Array.isArray](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/isArray)
[JavaScript array type check - “is array” vs object in-depth](https://codewithhugo.com/detecting-object-vs-array-in-javascript-by-example/)
