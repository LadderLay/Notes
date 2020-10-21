## core concepts
### entry
dependency graph 依赖图

```
//单入口
entry: './path/to/my/entry/file.js'

//对象语法
entry: {
  app: './src/app.js',
  adminApp: './src/adminApp.js'
}
//多页面应用
entry: {
  pageOne: './src/pageOne/index.js',
  pageTwo: './src/pageTwo/index.js',
  pageThree: './src/pageThree/index.js'
}

```
### output
property: .test, .use
### plugins
webpack 插件是一个具有 apply 方法的 JavaScript 对象。  
apply 方法会被 webpack compiler 调用，并且在整个编译生命周期都可以访问 compiler 对象。
### loaders
loaders allow webpack to process other types of files and convert them into valid modules.  
在import/load模块预处理文件  
使用方式：  
- 配置：loader 从右到左（或从下到上）地取值(evaluate)/执行(execute)
- 内联
- CLI
loader特性：
- 支持链式调用
- 同步/异步
### mode
- development  
- production
- none

### browser compatibility

## why webpack?
IIFE
