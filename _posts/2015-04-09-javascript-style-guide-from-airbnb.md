---
layout: post
title: JavaScript编码规范 - From Airbnb
description: 
category: work
---
<link rel="stylesheet" type="text/css" href="/js/prettify/css/github.css" />
####类型
* 基本类型
  * string
  * number
  * boolean
  * null
  * undefined
  <pre class="prettyprint">
    var foo = 1;
    var bar = foo;
    bar = 9;
    console.log(foo, bar); // => 1, 9
  </pre>
* 复合类型
  * 创建对象
  <pre class="prettyprint">
   // bad
   var item = new Object();
   // good
   var item = {};
  </pre>
  *不要使用保留字
  <pre class="prettyprint">
  // bad
  var superman = {
    default: { clark: 'kent' },
    private: true
  };
  // good
  var superman = {
    defaults: { clark: 'kent' },
    hidden: true
  };
  </pre>
  *使用简单的同义词代替保留字
  <pre class="prettyprint">
  // bad
  var superman = {
    class: 'alien'
  };
  // bad
  var superman = {
    klass: 'alien'
  };
  // good
  var superman = {
    type: 'alien'
  };
  </pre>

####数组
* 创建对象
* 需要复制数组时，使用slice
* 使用slice将对象转换为数组
* 

####字符串
* 对字符串使用单引号
* 超过80个字符的字符串应该使用字符串连接符进行跨行
  Notice：对长字符串过度使用连接符将会影响性能
* 以编程方式创建字符串的时应该使用Array的join方法而不是通过连接符，尤其是在IE中

####函数
* 函数表达式
* 不要再非函数块(if,while)中声明函数
* 不要命名一个参数为arguments，否则它将优先于传递给每个函数作用域中的arguments对象

####属性
* 使用点表示法访问属性
* 用变量访问属性时要使用下标表示法([])

####变量
* 总是使用var声明变量，不然其将变为全局变量。我们要想办法避免全局空间污染
* 使用var声明每个变量，这样很容易添加新的变量声明
* 最后声明未赋值的变量，这对于你需要根据之前已经赋值的变量对一个变量进行赋值时是很有帮助的
* 在作用域顶端对变量赋值

####声明

