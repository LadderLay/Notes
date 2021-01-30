## 项目
### 编译上下文 
`tsconfig.json`
对文件进行逻辑分组 携带编译选项等等
### 声明空间
**1.类型声明空间**
用于类型注解
```
//声明
class Foo {}
interface Bar {}
type Bas = {}

//应用
let foo: Foo;
lat bar: Bar;
let bas: Bas;

```
Attention:
注意，interface `Bar`不能作为变量使用，因为它并没有定义在变量空间中
因此`const bar = Bar;`这种写法是错误的

**2.变量声明空间**
包含可用作变量的内容
 interface 定义的内容不能当作变量使用
 同理， var 声明的变量只能在变量声明空间使用而不能作为类型注解
### 模块
文件模块
使用 module: commonjs选项/ES模块语法进行导入导出
```
//export

//import

//export default +变量/函数/类
```
Q：import/require 仅仅是导入类型
### 命名空间

### 动态导入表达式
                                 
## 类型系统
**接口**：  
```
interface Name {
  first: string;
  second: string;
}
//合并了类型说明
```
**特殊类型**：  
1.`null`  2.`undefined`
null、undefined和any一样，能被赋予任意类型的变量。
3.`void`
4.`any`   
在类型系统中，any能够兼容所有的类型包括其本身。「后门」一般的存在。

**泛型**
类型安全


联合类型：
属性可能为多种类型之一
```
function fnc(command: string[] | string) {
    //...
}
```
交叉类型：
在 JavaScript 中， extend 是一种非常常见的模式，在这种模式中，你可以从两个对象中创建一个新对象，新对象拥有着两个对象所有的功能。
交叉类型使得这种模式可以被安全地使用

**接口**
**JSX**
**FAQs**