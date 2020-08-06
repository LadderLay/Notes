# 6 Syntax
## 阅读笔记

assert断言

### 1、Identifiers
#### 1 ) valid identifiers
First character:
- Unicode letter (including accented characters such as `é` and `ü` and characters from non-latin alphabets, such as `α`)
- `$`
- `_`

有效标识符不能以**数字**开头，不能是保留字。

#### 2 ) reserved words
**保留字**不能做**变量名**，但是可以做**属性名**


### 2、Statement & expression

**statement**：一段可被执行的代码，执行某种操作。
如函数声明、if语句等。

**expression**：一段可被评估（？evaluated）的代码，产生一个值。

- if 语句是 statement，而三元运算符` _?_:_ `是 if语句的 `expression` 版本。
- 对于函数而言，函数的主体必须是一系列 `statement`，而函数/方法调用的参数必须是 `expression`。
- 表达式可以用作语句（expression statements）;反之语句不能被用作表达式。
```
function f() {
  console.log(bar()); // bar() is expression
  bar(); // bar(); is (expression) statement  
}
```

### 3、Automatic semicolon insertion (ASI) 
**Semicolon**
```
function foo() {} // A
const foo = function () {} // B
```
?1
### 4、strict mode & sloppy mode
?2

## 习题笔记
### 1、考察：`statement & expression`
1）
```
Which of these pieces of code can appear in expression context?
 a = 3 //赋值表达式
 const a = 3 //变量声明 语句
 function () {} // 匿名函数 表达式
 function func() {}
 { get prop() {} }
 if (x < 0) x = -x
```
解析：

2）
```

```

?3





# 10 Variables and assignment
## 阅读笔记

### 1、const & let
```
1）let i; //可变
2）const i = 0; //不可变，必须进行初始化
```
需要注意的是，`const`仅表示绑定是不可变的. `const`保证了变量指向的内存地址不可变，因此对于简单数据类型而言，值就保存在变量指向的内存地址中，等同于常量；对于复杂数据类型而言，变量指向的内存地址为指针，无法保证指针指向的数据类型的不可变性。
?4

### 2、变量作用域
- const、let - 块级作用域
- 阴影变量：不能在同一级别多次声明同名变量；但是可以进行块级嵌套（The inner x is said to shadow the outer x）

### 3、static vs. dynamic 
变量作用域： static  静态嵌套
函数调用： dynamic  动态调用

### 4、全局变量和全局对象




## 习题笔记
### 1、考察：`const`
```
const obj = {a: 1};
obj = {};
// TypeError
```
解析：
const 绑定不可变性

### 2、考察：` Temporal dead zone`

```
let foo = 'a';
{
  console.log(foo); // (A)
  let foo;
  foo = 'b';
}
// ReferenceError
```

解析：
foo is accessed before it is declared (within the current scope).？

### 3、考察：`Closures`
1）
```
const foo = 'a';
function func() {
  return foo;
}
function returnFunc(foo) {
  return func;
}
const result = returnFunc('b')();
// assert.equal(result, 'a')
```
解析：
What variable a name refers to, can be determined statically. That’s why func() will always return the variable in the surrounding scope. Returning func() from returnFunc() before calling it, does not change that.

2）
```
const foo = 'a';
function returnFunc(foo) {
  function func() {
    return foo;
  }
  return func;
}
const result = returnFunc('b')();
//assert.equal(result, 'b')
```
解析：
func is a closure and stays connected with its birth environment. In that environment, foo is 'b'.




```

```
考察：` `
解析：


# 11 Values

## 阅读笔记

- 类型 type —— 值的集合

### 1、primitive values and objects 原始值和对象

**primitive value:**
原始值不可改变，无法对其的属性进行修改；
变量/参数存储的是 值 本身， 传递和比较的也是原始值本身。

**objects:**
对象默认可改变
将对象分配给变量或将其作为参数传递给函数时，将复制的是对象的指针/引用
```
const a = {}
const b = a
assert.equal(a === b, true)
//`a` and `b` point to the same object
//they “share” that object
```
对象比较的是标识而不是值本身
```
const obj = {}; 
assert.equal(obj === obj, true); 
// same identity
assert.equal({} === {}, false); 
// different identities, same content
```

Q：javascript引擎 共享主内存？

### 2、 typeof & instanceof

**typeof**
undefined - undefined
**null - object**
function - function

**instanceof**
`A instanof B` 判断 A 是否为 B 的实例

待补充
原始值，null...

Q：原型链部分有点生疏了需要复习


### 3、类和构造函数





## 习题笔记

### 考察：Equality
`assert.ok({} === {})`
解析：
Each time the object literal {} is used, it creates a new object. And objects are compared by reference; each one has its own identity.

### 考察：typeof
const result = typeof function () {};
// assert.equal(result, 'function')


# 13 The non-values undefined and null

### 1- 出现场合

**`undefined` 出现场合**
1）未初始化的变量
2）参数缺失、`return`语句省略
3）`obj.unknownProp` 未指定的属性
**`null` 出现场合**
1）`Object.prototype`没有原型
2）正则匹配失败
3）`JSON`不支持`undefined`只支持`null`

ps.对象类型的变量使用`null`初始化

### 2- 两者均没有属性

### 3- `null` 表明“不是对象”，而 `undefined` 表示一个“既不是对象也不是原始值的初始化值” 

# 14 Booleans

# 17 Unicode
utf-16 utf-8

code points & code units

# 18 Strings
- JS中的字符-string
- `for-of`访问字符串代码点字符
- 字符串加法规则

### 三种将 value 转换为 string 的方法
1、`String(x)`
2、`''+x`
3、`x.toString()` **对`null`和`undefined`不生效**

`JSON.stringify()`也可以将值转换为字符串，仅支持null，布尔值，数字，字符串，数组和对象（始终将其视为由对象文字创建的样子）。

### 字符串方法
- .endsWith
- .includes
- .indexOf
- .lastIndexOf
- .match
...

# 19 Template
template literals - normal string literals
- 支持字符串插入
- 可以跨越多行

tagged templates 



# 21 Control flow statement 控制流语句

控制循环： `break`,`continue`
if 语句 
while 循环
for 循环
for-of  const
**for-await-of**
**for-in**

# 22 Exception handling
`throw`

`try...catch`
`finally`(alaways executed)

`Error Classes`
`properties of err`
- .message
- .stack

# 23 Callable values
## function功能
- ordinary
  - Real function
  - Method
  - Constructor function
- specialized 只能拥有一种功能

函数声明 函数表达式

ordinary function & real function
函数表达式的名称只能在函数内部访问，而函数声明的名称可在当前作用域内访问
# 24 Modules



