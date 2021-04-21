## 盒模型
标准模型：
`box-sizing: content-box`
width height 指的是content区域
IE模型：
`box-sizing: border-box`
width height 包含 content padding border区域

1. 边距重叠 margin collapse

2. BFC
- 什么是 BFC？
块格式化上下文
它是一个独立的块级渲染区域，拥有一套规则约束内部块级盒子的布局，且与外部区域无关

- BFC 规则
BFC元素垂直方向上的边距会重叠，不同BFC外边距不重叠（？）
BFC元素不会与浮动元素布局重叠
BFC元素为独立容器，内部和外部互不影响
计算BFC高度时，浮动元素也会参与计算（清除浮动？）

- BFC解决什么问题（具体场景）
边距重叠 margin collapse
清除浮动（子元素float导致父元素坍塌高度为0）


- 什么会创建BFC？
设置float
position是除了static relative以外的值
overflow设置为auto/hidden

3. 清除浮动

4. position的各个值：


## 常用布局
两栏布局
- 利用margin-left和浮动元素隔离
```
.left { 
    float: left;//脱离节点流
    width:  200px;
}
.main {
    margin-left: 200px;//留出空间避免重叠
}
```
- 利用BFC实现
```
.left { 
    float: left;
    width:  200px;
}
.main {
    overflow: hidden;//触发BFC -》看一下BFC
}
```
- 使用flex布局
```
container {
    display: flex;//flex常考考点
    .left {
        width: 100;
    }
    .main {
        flex: 1//具体含义
    }
}
```
三栏布局
- 圣杯布局 使用padding去做
圣杯的不足：当middle宽度小于两边宽度时，布局会乱掉
- 双飞翼 
在圣杯的基础上进行了改进 使用margin去预留空间
[圣杯 双飞翼的说明](https://www.zhihu.com/question/21504052)
- flex布局 flex:1

## css预处理器


## flex


1.flex:1 === flex: 1 1 0
css 动画 js动画
