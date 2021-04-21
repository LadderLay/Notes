## JS基本数据类型
bigint symbol null undefined number string boolean

2.类型判断 如何判断数组
`Object.prototype.toString.call(arr)`判断是否等于`[Object Array]`
`arr instanceof Array` instanceof
`Array.isArray(arr)去判断`
3.JS有哪些基础类型？引用类型？
基础类型(7种原始数据类型)： null undefined boolean string number bigint symbol
引用类型： object js内置对象如Array Function Math Date

两者之间的区别
值类型：
占用的空间是固定的，保存在栈中；保存和复制的是值本身；
引用类型：
占用的空间是可变的，存储在栈中的是对象的引用，对象存储在堆中，保存和复制的是引用
->对象类型 只实现了浅拷贝

4. 浅拷贝 深拷贝
浅拷贝：只复制指向某个对象的指针，而不复制对象本身，新旧对象共享一块内存
深拷贝：复制并创建一个一摸一样的对象，不共享内存，修改新对象，旧对象保持不变。
浅拷贝方法：

`Object.assign({},obj)`

`let newObj = {...obj}` //需要注意⚠️ 扩展运算符对于简单对象和一维的非对象数组

深拷贝方法：
`JSON.parse(JSON.stringfy(xxx))`
利用json.stringfy将对象序列化，再使用json.parse进行还原
手写实现深拷贝：
递归
```
function deepCopy(target) {
    if(typeof target !== 'object' && !target)
        return target;
    let res = Array.isArray(target) ? [] : {};
    for(let t in target) {
        if(target.hasOwnproperty(t)) {
            res[t] = typeof target == 'object' ? deepCopy(target[t]) : target;
        }
    }
    return res;
}
```

5. null undefined之间的区别



## var let const 之间的区别？
var
声明提升机制（先赋值后声明的代码不会报错 解析执行两个阶段）
var声明的变量是外部函数的局部变量 声明的范围是函数作用域
var可以多次声明同名变量

let
let声明的变量不会被提升 而是会有一个暂时性死区
声明的变量范围是块级作用域，let声明的全局变量不是全局对象的属性
for循环中在每次迭代循环声明一个新的迭代变量
let不能重定义同名变量
const
用来定义常量，定义的时候必须进行变量初始化
不能进行重新声明或赋值【如果是对象限制的只是不能修改引用而不是对象本身】

## 什么是闭包？什么是内存泄漏？
1.闭包
红宝书：引用了外部函数作用域中变量的函数（？）


2.内存泄漏



3.作用域链



## 原型链？如何形成？末端？

## new 操作
1. 为什么实例能继承属性？

2. new一个对象的过程 


## this

call
apply
bind

## Promise


## ES6
1. map set 特性

2. map object比较

3. proxy?

4. reduce 看一下之前笔记





## 几种不同的for循环

## 防抖 节流
都是为了优化会被高频率执行的代码 是前端性能优化的手段

防抖 ：在事件触发n秒后再执行回调函数；如果n秒内事件被再次触发，则重新计时 
防止抖动，避免用户提交表单信息的时候多次点击按钮、重复提交
文本编辑器的实时保存

节流 ：规定一个单位时间，在这个单位时间内，只能有一次触发事件的回调函数执行
控制事件的发生频率
射击游戏（子弹的发射）

杂七杂八
- 垃圾回收
- 作用域链
- this指向 箭头函数
- 函数内部arguments
- Promise
- 异步函数 async await
- array 栈 队列的操作
- 继承
- weakmap weakset

闭包【https://segmentfault.com/a/1190000039366748】第五题不懂