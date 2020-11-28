## 文档
### 基础类型
数据类型：  
boolean number string 
数组-
```
//1 元素类型+[]
let list: number[] = [1,2,3];
//2 使用数组泛型 Array<元素类型>
let list: Array<number> = [1,2,3]
```
元组Tuple-  
`let x: [string,number]`
Q:联合类型？

枚举enum-  
//默认从0开始为元素编号
```
enum Color {Red（=0）, Green, Blue}
let c: Color = Color.Green;
```
Any-
避免类型检查器对这些值进行检查而是直接让他们通过编译阶段对检查
void-  
表示没有任何类型。只能赋值为 null 或 undefined
null,undefined-
默认情况下，这两个值是所有类型的子类型。（特殊情况：指定了--strictNullChecks除外）
Never-  
表示永不存在的值的类型。
never类型是任何类型的子类型，也可以赋值给任何类型；然而，没有类型是never的子类型或可以赋值给never类型（除了never本身之外）。 即使 any也不可以赋值给never。  
Object-
表示非原始类型  

**类型断言:** 
```
//1 尖括号
let someValue: any = "this is a string";
let strLength: number = (<string>someValue).length;

//2 as 语法
let someValue: any = "this is a string";
let strLength: number = (someValue as string).length;

```
注意，当你在TypeScript里使用JSX时，只有 as语法断言是被允许的。

### 变量声明
var
let  词法作用域/块作用域
const

### 接口
对值所具有的结构进行类型检验
```
interface SquareConfig {
  color: string;
  width?: number;//可选属性
  readonly x: number;//只读属性
}
```
可选属性的作用： 对可能存在的属性进行预定义；捕获引用了不存在的属性值时的错误

**判断 readonly vs const 的使用**
readonly: 属性 properties
const: 变量 variable

处理对象字面量存在目标类型不包含的属性时，
```
//使用类型断言
let mySquare = createSqure({...} as SqureConfig);
//字符串索引签名
interface SquareConfig {
    color?: string;
    width?: number;
    [propName: string]: any;
}
//
```
**函数类型的接口**
```
interface SearchFunc {
    (source: string, subString: string): boolean;
}
```
对于函数类型的类型检查来说，函数的参数名不需要与接口中定义的名字相匹配；函数的参数会逐个进行检查，要求对应位置上的参数类型是兼容的。
`mySearch = function (src: string, sub: string): boolean{...}`

**可索引类型**
```
interface StringArray {
    [index: number]: string;
}
let myArray: StringArray;
myArray = ["Bob", "Fred"];

let myStr: string = myArray[0];

```
TS 支持字符串和数字两种索引签名
数字索引的返回值必须是字符串索引返回值类型的子类型？Q1

**type Vs. interface**

**类接口**
```
interface ClockInterface {...}

class Clock implements ClockInterface {...}

```
接口描述了类的公共部分；接口不会检查类的私有部分
类的静态部分和实例部分
当一个类实现了一个接口时，只对其实例部分进行类型检查。 constructor存在于类的静态部分，所以不在检查的范围内。
对于类的静态部分，应该直接进行操作。

**接口继承**
一个接口可以继承多个接口，创建出多个接口的合成接口

混合类型
```
interface Counter {
    (start: number): string;
    ...
}

function getCounter(): Counter {
    let counter = <Counter>function (start: number) {...}
}

let c = getCounter();
c(10);

```

**接口继承类**
当你创建了一个接口继承了一个拥有私有或受保护的成员的类时，
这个接口类型只能被这个类或其子类所实现（implement）

### 类
protected
当构造函数被protected修饰时，该类不能在类外被实例化，但是能被继承
readonly 只读修饰符
使用getters/setters有效控制对对象成员的访问
```
get fullName(): string {
    return this._fullName
}
set fullName(newName: string) {
    if(...)
        this._fullName = newName;
    else
        console.log("Error:...");
}
```
注意：只带get不带set属性的存取器会被自动推断为 readonly
  
静态属性-

抽象类- 

### 函数

### 泛型
泛型约束

### 枚举

### 类型推论

### 类型兼容性


## 声明文件
类型别名 type

## handbook
### 1⃣️ 基本类型
Boolean: true/false
Number bigint
String "/'
Array number[]/Array<number>
Tuple
Enum
Unknown
Any
Void
Null and Undefined
Never
Object
Type assertions

### 2⃣️ 接口
type checking


### 3⃣️ 函数
### 4⃣️ Literal Types
### 5⃣️ Unions and Intersection Types
### 6⃣️ 类
### 7⃣️ 枚举
### 8⃣️ Generics



