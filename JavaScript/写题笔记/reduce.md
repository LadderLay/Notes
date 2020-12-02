## definition
reduce() 方法对数组中的每个元素执行传入的reducer函数（升序执行） 

接收四个参数：累加器 当前值 当前索引 源数组
reducer 函数的返回值会分配给累加器
`arr.reduce(callback(accumulator,currentvalue,index,array), initialvalue)`
initialValue 作为第一次调用 callback 函数时的第一个参数的值
如果没有提供，则使用数组中的第一个元素；此时若为空数组没有初始值则会报错

原文表述：
回调函数第一次执行时，accumulator 和currentValue的取值有两种情况：如果调用reduce()时提供了initialValue，accumulator取值为initialValue，currentValue取数组中的第一个值；如果没有提供 initialValue，那么accumulator取数组中的第一个值，currentValue取数组中的第二个值。

## example
### 数组求和
```
var arr = [0,1,2,3]

var sum1 = arr.reduce(function(accum,cur) {
    return accum + cur;
},0)

var sum2 = arr.reduce(
    (accum,cur) => accum+cur, 
    0
)

```
### 累加对象数组中的值
```
var initialValue = 0;
var obj = [{x:1},{x:2},{x:3}];
var sum = obj.reduce((accum,cur) => accum + cur.x, initialValue);
```

### 二维数组转化为一位数组
```
var arr = [[0, 1], [2, 3], [4, 5]]
var flattened1 = arr.reduce(
    function(a, b) {
        return a.concat(b);
    },
    []
)
var flattened2  = arr.reduce(
    (arr, cur)  => arr.concat(cur),
    []
)
```
### 计算数组中每个元素出现的次数

```
var names = ['Alice', 'Bob', 'Tiff', 'Bruce', 'Alice'];
var countNames = names.reduce(function(allNames, name) {
  if(name in allNames)
    allNames[name]++; 
  else 
    allNames[name] = 1; //对象中未赋值的属性的值为undefined，因此需要单独处理进行初始化
  return allNames;
}, {})

```

### 按属性对 object 分类

### 使用扩展运算符和initialValue绑定包含在对象数组中的数组

### 数组去重


## polyfill
```
// Production steps of ECMA-262, Edition 5, 15.4.4.21
// Reference: http://es5.github.io/#x15.4.4.21
// https://tc39.github.io/ecma262/#sec-array.prototype.reduce
if (!Array.prototype.reduce) {
  Object.defineProperty(Array.prototype, 'reduce', {
    value: function(callback /*, initialValue*/) {
      if (this === null) {
        throw new TypeError( 'Array.prototype.reduce ' + 
          'called on null or undefined' );
      }
      if (typeof callback !== 'function') {
        throw new TypeError( callback +
          ' is not a function');
      }

      // 1. Let O be ? ToObject(this value).
      var o = Object(this);

      // 2. Let len be ? ToLength(? Get(O, "length")).
      var len = o.length >>> 0; 

      // Steps 3, 4, 5, 6, 7      
      var k = 0; 
      var value;

      if (arguments.length >= 2) {
        value = arguments[1];
      } else {
        while (k < len && !(k in o)) {
          k++; 
        }

        // 3. If len is 0 and initialValue is not present,
        //    throw a TypeError exception.
        if (k >= len) {
          throw new TypeError( 'Reduce of empty array ' +
            'with no initial value' );
        }
        value = o[k++];
      }

      // 8. Repeat, while k < len
      while (k < len) {
        // a. Let Pk be ! ToString(k).
        // b. Let kPresent be ? HasProperty(O, Pk).
        // c. If kPresent is true, then
        //    i.  Let kValue be ? Get(O, Pk).
        //    ii. Let accumulator be ? Call(
        //          callbackfn, undefined,
        //          « accumulator, kValue, k, O »).
        if (k in o) {
          value = callback(value, o[k], k, o);
        }

        // d. Increase k by 1.      
        k++;
      }

      // 9. Return accumulator.
      return value;
    }
  });
}
```