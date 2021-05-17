# CSS 知识总结

## 浏览器的渲染原理
1. 根据HTML构建HTML树（DOM）
2. 根据CSS构建CSS树 （CSSDOM）
3. 根据两棵树合并一颗渲染树 （render tree）
4. layout布局 
5. paint绘制
6. compose合成

## CSS盒模型

盒模型分为两种

- content-box   内容盒
- border-box    边框盒

用图来说就是

![image](https://user-images.githubusercontent.com/81228918/118476135-b7d5d900-b73f-11eb-8169-2d9d6304fdb9.png)

## CSS布局分类

- DIV+CSS布局 （现在常说CSS布局）
- float布局
- flex布局
- grid布局

## 定位
定位是垂直于屏幕的
position
- static默认值，待在文档流里
- relative相对定位，升起来，但不脱离文档流
- absolute绝对定位， 定位基准的是祖先里的非static
- fixed固定定位，
- sticky，

## 动画

CSS 动画的两种做法 （transition 和 animation）

#### transition 过渡
transition CSS 属性是一个简写属性。
语法
- 作用是补充中间帧
- transition：属性名 时长 过度方式 延迟
- 可以用逗号分隔两个不同属性 不过为了方便 用 all 代表所有元素

但不是所有属性都可以过滤的
- display:none 不能过度到block

animation 语法
animation: 时长 过度方式 延迟 次数 方向 填充模式 是否暂停 动画名


