### Array.prototype.join()
join() 将一个数组或类数组对象的所有元素连接成一个**字符串**并返回这个字符串；如果数组只有一个元素则返回该元素而不使用分隔符。
```
const elements = ['Fire', 'Air', 'Water'];
console.log(elements.join()); //默认，用逗号分隔  Fire,Air,Wate
console.log(elements.join(''));//为空           FireAirWater
console.log(elements.join('-'));//-分隔         Fire-Air-Water
```

如果 arr.length 为0，则返回空字符串

### Array.prototype.filter()
不修改原数组
创建一个新数组，包含所有通过所提供函数实现的测试的所有元素
callback 只会在已经赋值的索引上被调用，对于那些已经被删除或者从未被赋值的索引不会被调用
### Array.prototype.concat()
不修改原数组
返回一个新数组，用于合并多个数组。

### slice()
不修改原数组
返回一个新的数组对象,是原数组的一个浅拷贝
[begin,end)
如果 begin 超出原数组的索引范围，则会返回空数组
如果 end 被省略，则 slice 会一直提取到原数组末尾。
如果 end 大于数组的长度，slice 也会一直提取到原数组末尾。

通过 slice 可以将一个类数组对象转换为一个新数组
### Array.prototype.splice()
修改原数组
`array.splice(start,deleteCount,item...)`
通过删除或替换现有元素或者原地添加新的元素来修改数组,并以数组形式返回被修改的内容
### pop()
修改原数组
与shift行为类似，但是从数组中删除最后一个元素，并返回该元素的值
### shift()
修改原数组
从数组中删除第一个元素，并返回该元素的值
当数组为空时返回`undefined`
数组长度也随之改变
注意 如果 length 属性的值为 0 (长度为 0)，则返回 `undefined`
### unshift()
修改原数组
将一个或多个元素添加到数组的开头，并返回该数组的新长度
