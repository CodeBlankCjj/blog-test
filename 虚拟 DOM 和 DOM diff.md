### 虚拟 DOM 是什么
> 虚拟 DOM 就是用来模拟 DOM 的一个对象，这个对象拥有一些重要属性，并且更新 UI 主要就是通过对比
### 虚拟 DOM 的优点
- 虚拟 DOM 可以将多次操作合并为一次操作，比如你添加 1000 个节点，却是一个接一个操作的（减少频率）
- 虚拟 DOM 借助 DOM diff 可以把多余的操作省掉，比如你添加 1000 个节点，其实只有 10 个是新增的（减少范围）
跨平台
- 虚拟 DOM 不仅可以变成 DOM，还可以变成小程序、iOS 应用、安卓应用，因为虚拟 DOM 本质上只是一个 JS 对象

### 虚拟 DOM 的缺点
- 需要额外的创建函数，如 createElement 或 h，但可以通过 JSX 来简化成 XML 写法
### DOM diff 是什么
- 新旧虚拟DOM的对比算法
- 就是一个函数，我们称之为 patch
- patches = patch(oldVNode, newVNode)
- patches 就是要运行的 DOM 操作，可能长这样：
```
[
  {type: 'INSERT', vNode: ... },
  {type: 'TEXT',  vNode: ... },
  {type: 'PROPS', propsPatch: [...]}
]
```
### DOM diff 的优点
- 可以做到只把变化的部分重新渲染,提高渲染效率的过程。
### DOM diff 的问题
- 同级节点对比存在 bug

- 解决方法：用唯一Key值进行区分
