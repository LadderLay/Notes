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