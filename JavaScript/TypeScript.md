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
void-  

### 变量声明
var
let  词法作用域/块作用域
const

### 接口

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

