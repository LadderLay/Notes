# 三、基本概念

## 语法
- JavaScript中区分大小写
- 标识符：指变量、函数、属性名，或函数参数。第一个字符必须是字母、下划线（_）或美元符号（💲）；标识符 采用小驼峰的写法。
- 关键字和保留字
- 变量： 松散类型 

## 数据类型
基本数据类型： Undefined, Null,  Boolean, Number, String
复杂数据类型： Object
(Q不是最新版！)

### undefined
- 引入`undefined`是为了正式区分空对象指针和未经初始化的变量

- 
    ```
    var m;
    //var n;
    alert(typeof m);  // "undefined"
    alert(typeof n);  // "undefined"
    ```
    需要注意的是，对于未初始化和未声明的变量执行`typeof`操作符均返回`undefined`

### Null
- `typeof`操作符检测`NULL`返回`object`【逻辑上理解，`NULL`表示一个空对象指针】

### Number
- `NaN`
- 数值转换： Number()、parseInt()和 parseFloat()
### String类型
`toString`

### 操作符

## 流控制语句

## 函数


# 四、变量、作用域和内存问题