### Array.prototype.join()
join() 将一个数组或类数组对象的所有元素连接成一个**字符串**并返回这个字符串；如果数组只有一个元素则返回该元素而不使用分隔符。
```
const elements = ['Fire', 'Air', 'Water'];
console.log(elements.join()); //默认，用逗号分隔  Fire,Air,Wate
console.log(elements.join(''));//为空           FireAirWater
console.log(elements.join('-'));//-分隔         Fire-Air-Water
```

如果 arr.length 为0，则返回空字符串
