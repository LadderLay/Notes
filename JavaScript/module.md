# 0

definition:  
A module is a piece of program that specifies which other pieces it relies on and which functionality it provides for other modules to use (its interface).

export
import

prior to ES6: 
1.CommonJS
- designed for servers,compact syntax
- modules are meant to be loaded synchronously (the importer waits while the imported module is loaded and executed)
2.AMD 
- ...browsers
- ex. require.js
- modules are meant to be loaded asynchronously.
3.characteristics of js modules
- Modules are **singletons**: Even if a module is imported multiple times, only a single “instance” of it exists.
- **no global variables** are used.
- 文件结构：local scope, exports, imports

4.ES modules
- Modules have static structures (which can’t be changed at runtime).
- Support for cyclic imports is completely transparent.

```
//example of syntax
import {importedFunc1} from './other-module1.mjs';
import {importedFunc2} from './other-module2.mjs';

function internalFunc() {
  ···
}

export function exportedFunc() {
  importedFunc1();
  importedFunc2();
  internalFunc();
}

```
辨析： import & destructuring
**Imports** remain **connected** with their **exports**.
You can destructure again inside a destructuring pattern, but the {} in an import statement can’t be nested.


```
import {foo} from './bar.mjs'; // import
const {foo} = require('./bar.mjs'); // destructuring
```



