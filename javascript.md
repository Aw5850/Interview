### 1. js 把一个函数赋给一个变量时带括号与不带括号的区别
```js
function hi(){  
  var a = 1;  
  return function(){
   console.log(a++);
  };  
};         
var aaa = hi();
var bbb = hi;
aaa();
bbb();
```
