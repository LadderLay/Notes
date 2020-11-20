React 路由解决方案

- 单页应用 SPA
    局部刷新，提升了交互体验
    首屏时间慢
    通过动态重写当前页面来与用户交互，而非传统的从服务器重新加载整个新页面。路由由前端来处理，用js动态替换html内容，从而模拟在多个视图间的跳转。
    SEO优化 SSR
- 多页应用
    前后端耦合


前端路由
为 spa 的每个视图匹配一个特殊的 url  
监听 url 变化； 不向服务器请求地改变 url 
  
静态路由
动态路由

两种模式
**Hash 模式**
# 
hashchange 事件

**History API**  
提供了对浏览器的会话历史的访问。允许你在用户浏览历史中向前和向后跳转，同时提供了对 history 栈中内容对操作。
`window.history.back();` // 在history中向后跳转  
`window.history.forward();` // 在history中向前跳转  
`window.history.go(-1);`    //跳转到 history中指定对一个点  
`history.pushState();`         // 添加新的状态到历史状态栈
`history.replaceState();`      // 用新的状态代替当前状态
`history.state`                // 返回当前状态对象
pushState() 会增加一条新的历史记录，而 replaceState() 会替换当前的历史记录。

**React-Router**
组件即路由
动态路由

---
router v2/3 & v4
Router 容器
Route 每一个路径对应页面的路由规则
history
嵌套路由
默认路由设置改变
---
包含式路由/独立路由/重定向路由
嵌套路由的处理
组件化

**API**
Hooks-
- useHistory
    
- useLocation
- useParams
- useRouteMatch
