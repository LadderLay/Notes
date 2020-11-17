## 设计思想  ✓
基本原则
- 数据驱动 UI=f(data)
- 组件化
- 组件交流：props
## 组件实践  
123
设计原则
- 接口小，props数量少
- 组合的原则，根据数据边界进行组件划分
- state提升到上层组件，下层组件实现纯函数

## 组件设计模式
12345
- 聪明组件和傻瓜组件（容器组件和展示组件）
    外层父组件管理数据状态，内层子组件负责界面渲染逻辑
    便于修改数据状态的管理方式
- PureComponent
- 提供者模式


## React 单元测试
Jest
Enzyme

## React 状态管理
### Redux
组件自身状态  
setState  
- 异步性
- 函数式setState
基本概念： action reducer store  
redux 应用场景  
- 状态是否被多个组件共享
- 状态是否需要被保留（unmount->mount)
代码组织形式：  
- 基于角色
- 基于功能 将一个模块相关的所有源代码放在一个目录下

**提供者模式** 
redux/react最佳实践   
- store中的数据应该范式化
- 使用selector(?)
- 只 connect 关键点的 React 组件（关键点再通过 props 向下传递数据）

### Mobx
## 路由
