### values(7)
1. numbers（special: Infinity,-Infinity,NaN）
2. strings(`${}`will be computed,and converted to a string)
3. booleans: true & false
4. undefined
5. null
6. object(array,function,object)
7. symbol

#### null&undefined&boolean
- `undefined == null` is true
- undefined&null:`null`是一个**表示“空”**的对象，转为数值时为0；`undefined`是一个**表示"此处无定义"**的原始值，转为数值时为NaN。
- `typeof null`-> `object`历史遗留问题
- Boolean **false**(6):`undefined`,`null`,`false`,`0`,`NaN`,`" "或' '(空字符串)`
- 接上一条，所以，空数组（`[]`）和空对象（`{}`）对应的布尔值，都是true

#### 数值
- `NaN == NaN` is false【？】
- 方法：parseInt,parseFloat,isNaN,isFinite
- `typeof` 运算符:`typeof`可以用来检查一个没有声明的变量，而不报错

#### 对象
- `key-value`的集合
- 属性 方法
属性的操作：
- `Object.keys`：查看一个对象本身的所有属性
- `in`运算符用于检查对象是否包含某个属性（注意，检查的是键名，不是键值）,`hasOwnProperty`可判断是否为自身属性而不是继承属性
- `for...in`循环：遍历所有可遍历（enumerable）的属性，包括自身和继承属性（可以用`hasOwnProperty`去排除）
- `with`:操作同一个对象的不同属性（赋值操作必须是当前对象已存在的属性），不推荐使用（？）

#### 函数

functions
bindings,scopes(global,local)
let,const,var

1.函数的声明
重复声明，新的会把旧的覆盖
函数名的提升

#### 数组 Array

##### `...`拓展运算符：将一个数组转为用逗号分隔的参数序列。

```
console.log(1, ...[2, 3, 4], 5)
// 1 2 3 4 5
```
1. 将数组转化成函数参数
```
function f(x, y, z) {
  // ...
}
let args = [0, 1, 2];
f(...args);
```
2. 两个数组的连接
```
let arr1 = [0, 1, 2];
let arr2 = [3, 4, 5];
arr1.push(...arr2);
```
3. 复制数组
```
const a1 = [1, 2];
// 写法一
const a2 = [...a1];
// 写法二
const [...a2] = a1;
```
4. **解构赋值！**
```
const [first, ...rest] = [1, 2, 3, 4, 5];
first // 1
rest  // [2, 3, 4, 5]
```
扩展运算符在用于数组赋值时只能用于最后一位

5. 字符串转数组
```
[...'hello']
// [ "h", "e", "l", "l", "o" ]
```
涉及到 Unicode时最好考虑用这种方法
具体如求字符串的长度时可以避免错误处理Unicode字符

Q1：**浅拷贝深拷贝是啥**
`Array.from()` 用于将**类数组**和**可遍历对象**（如 Set, Map）转化为真正的数组。Q2

类数组：有length属性

/*
对于还没有部署该方法的浏览器，可以用Array.prototype.slice方法替代。

const toArray = (() =>
  Array.from ? Array.from : obj => [].slice.call(obj)
)();

*/
这一段 再看一下

6. 接受多个参数并在转化为数组时进行处理（类似于map）
```
Array.from(arrayLike, x => x * x);
// 等同于
Array.from(arrayLike).map(x => x * x);
```
##### Array.of()
作用：将一组值转化为数组，可替代`Array()``new Array()`
原因：`Array()`方法只有在参数大于等于两个时才能返回由参数组成的新数组

##### 检索
`find`: 可识别`NaN`
`findIndex`: 可识别`NaN`  使用`Object.is`
`indexOf`

`includes`: 返回一个布尔值，表示某个数组是否包含给定的值

#### 变量的解构赋值


### some...
#### == & === & Object .is()
同：都是用于判断两个值是否相等
异：
**==**：会进行隐式类型转换
**===**-0与+0相等，且Number.NaN 不等于 NaN（？）
**Object.is()**
#### Object.keys() 
Object.keys() 方法会返回一个由一个给定对象的自身**可枚举**属性组成的数组
