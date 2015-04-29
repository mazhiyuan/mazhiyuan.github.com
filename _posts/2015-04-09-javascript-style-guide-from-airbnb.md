---
layout: post
title: JavaScript编码规范 - From Airbnb
description: 
category: work
---
<link rel="stylesheet" type="text/css" href="/js/prettify/css/github.css" />
####类型
* 基本类型 Primitives
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
  * 创建对象，使用literal syntax
  <pre class="prettyprint">
   // bad
   var item = new Object();
   // good
   var item = {};
  </pre>
  * 不要使用保留字
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
  * 使用可读性强的同义词代替保留字
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
* 创建对象，使用literal syntax
  <pre class="prettyprint">
  // bad
  var items = new Array();
  // good
  var items = [];
  </pre>
* 使用push方法
  <pre class="prettyprint">
  var someStack = [];
  // bad
  someStack[someStack.length] = 'abracadabra';
  // good
  someStack.push('abracadabra');
  </pre>
* 需要复制数组时，使用slice
  <pre class="prettyprint">
  var len = items.length;
  var itemsCopy = [];
  var i;
  // bad
  for (i = 0; i < len; i++) {
      itemsCopy[i] = items[i];
  }
  // good
  itemsCopy = items.slice();
  </pre>
* 使用slice将对象转换为数组
<pre class="prettyprint">
function trigger() {
  var args = Array.prototype.slice.call(arguments);
  ...
}
</pre> 

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
* 变量声明是在作用域顶端，但并未赋值
* 匿名表达式可以提升变量，但不能提升函数
* 命名表达式会提升变量，而不是函数名或者函数体
* 函数声明会提升变量和函数

####运算符
* 使用===和!==代替==和!=
* 比较运算符进行计算时会利用ToBoolean方法进行强制转换数据类型，并遵从以下规则
  * Objects的计算值是true
  * Undefined的计算值是false
  * Boolean的计算值是本身
  * Numbers如果是-0,+0或者NaN，则计算值是false反之是true
  * Strings如果是空，则计算值是false，反之是true

####语句块
* 对多行语句块使用大括号
* 对于if-else语句块，把if的右括号和else的左括号放在同一行

####注释
* 多行注释使用/**...*/，需包含一个描述，所有参数的具体类型，值和返回值
* 单行注释使用//，注释放在语句的上一行，并在注释之前留空行
* 如果你指出的问题需要重新定位或者提出一个待解决的问题需要实现，给注释添加FIXME or TODO 前缀有利于其他开发者快速理解。这些注释不同于通常的注释，因为它们是可实施的。这些实施措施就是FIXME -- need to figure this out or TODO -- need to implement.
* 使用//TODO:给问题解决方案作注释

####空白
* 设置制表符为两个空格
* 在左大括号前留一个空格
* 在控制语句中（if, while etc），左括号之前留一个空格。函数的参数列表之前不要有空格
* 使用空格分隔运算符
* 当调用很长的方法链时使用缩进，可以强调这行是方法调用，不是新的语句
* 在语句块和下一个语句之前留一个空行

####逗号
* 不要再语句前留逗号
* 不要有多余的逗号

####分号
* Yup

####类型分配和强制转换
* 在声明时进行类型转换
* Strings
* 使用parseInt对Numbers进行转换，不要省略进制参数
* 无论出于什么原因，或许你做了一些”粗野”的事；或许parseInt成了你的瓶颈；或许考虑到性能，需要使用位运算，都要用注释说明你为什么这么做
* 注意：当使用位运算时，Numbers被视为64位值，但是位运算总是返回32位整型(source)。对于整型值大于32位的进行位运算将导致不可预见的行为。最大的有符号32位整数是2,147,483,647
* Booleans

####命名规范
* 避免单字母名称，使其具有描述性
* 使用驼峰法命名变量、函数和类名
* 命名私有属性时使用前置下划线
* this引用使用_this变量
* 命名函数时，下面方式有利于堆栈跟踪
* 如果文件作为一个类被导出，文件名应该和类名保持一致

####存取器
* 对于属性，访问器函数不是必须的
* 如果定义了存取器函数，应参照 getVal() 和 setVal('hello') 格式
* 如果属性是boolean，格式应为 isVal() 和 hasVal()
* 创建形式一致的 get() 和 set() 方法

####构造函数
* 在原型对象上定义方法，而不要重写。重写使继承不可用，因为重写原型导致重写整个基类
* 返回this指针可以构建方法链
* 写一个自定义的toString()方法是可以的，只要确保它能正常运行并且不会产生副作用

####事件
* 当在事件对象上附加数据时（无论是DOM事件还是如Backbone一样拥有的私有事件），应传递hash对象而不是原始值，这可以让随后的贡献者给事件对象添加更多的数据，而不必去查找或者更新每一个事件处理程序。举个例子，不要用下面的方式：

####模块
* 模块应该以 ! 开始，这能确保当脚本连接时，如果畸形模块忘记导入，包括最后一个分号，不会产生错误。
* 文件应该以驼峰式命名，放在同名的文件夹中，和单出口的名称相匹配
* 定义一个noConflict()方法来设置导出模块之前的版本,并返回当前版本。
* 在模块的顶部申明’use strict';

####JQuery
* jQuery对象变量使用前缀$
* 缓存jQuery查询
* 使用级联$('.sidebar ul')或父子$('.sidebar > ul')选择器进行DOM查询
* 在范围内使用find进行jQuery对象查询