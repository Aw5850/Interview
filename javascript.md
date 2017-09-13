### 1. js 把一个函数赋给一个变量时带括号与不带括号的区别
```js
 function hi() {
        var a = 1;
        return function() {
            console.log(a++);
        };
    };
    var aaa = hi();
    var bbb = hi;
    console.log(aaa);
    /* function(){
       console.log(a++);
       };  */
    console.log(bbb);
    /*hi(){  
      var a = 1;  
      return function(){
       console.log(a++);
      };  
    }*/
    aaa(); //1

    console.log(bbb());
    /* function(){
     console.log(a++);
     };  */
```
`aaa`是将 `hi()` 的运行结果赋值给它，即 `return` 返回的匿名函数，此时有一个闭包，则每次调用`aaa`时都访问的同一个 a，`aaa()` 运行结果为 1
而`bbb`将是将 `hi` 这个函数名赋值给它，则调用`bbb()`后返回一个函数表达式，即`function(){console.log(a++)}`;
