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


# Values

## 习题笔记

### 考察：Equality
`assert.ok({} === {})`
解析：
Each time the object literal {} is used, it creates a new object. And objects are compared by reference; each one has its own identity.

### 考察：typeof
const result = typeof function () {};
// assert.equal(result, 'function')