## arguments
`arguments`对象是所有函数（箭头函数除外）都可用的**局部变量**。因此只能在函数内部使用。参数从索引0开始。
arguments对象本身不是Array，但可以被转换成数组（...方法很多）
arguments.length 可以用于确定传递给函数参数的个数，而Function.length用于确定形参的个数。