### 什么是MVC
> MVC模式就是架构模式的一种
> MVC是三个单词的首字母缩写，它们是Model（模型）、View（视图）和Controller（控制）
- 最上面的一层，是直接面向最终用户的"视图层"（View）。它是提供给用户的操作界面，是程序的外壳
- 中间的一层，就是"控制层"（Controller），它负责根据用户从"视图层"输入的指令，选取"数据层"中的数据，然后对其进行相应的操作，产生最终结果。
- 最底下的一层，是核心的"数据层"（Model），也就是程序需要操作的数据或信息。
```js
var model = {
  data: null,
  init(){},
  fetch(){},
  fetch(){},
  save(){},
  update(){},
  delete(){}
}
view = {
  init(){},
  template: '<h1>hi</h1>'
}
controller ={
  view: null,
  model: null,
  init(view, model){
    this.view = view,
    this.model = model,
    this.bindEvents()
  },
  render() {
    this.view.querySelector('name').innerHTML = this.model.data.name
  },
  bindEvents(){}
}
```
### EventBus 使用

> EventBus 是一个非常优秀的事件总线框架，可以用来简化组件间通信与数据传输，比如 Activity 之间、Fragment 之间、子线程与 UI 线程间等等情况。它基于发布/订阅模式，实现业务代码的解耦，提高了开发的效率。

### 表驱动编程

> 表驱动法就是一种编程模式(scheme)——从表里面查找信息而不使用逻辑语句(if 和case)。事实上，凡是能通过逻辑语句来选择的事物，都可以通过查表来选择。对简单的情况而言，使用逻辑语句更为容易和直白。但随着逻辑链的越来越复杂，查表法也就愈发显得更具吸引力。
```js
const day = new Date().getDay()
let day_zh;
if(day === 0){
    day_zh = '星期日'
}else if(day === 1) {
    day_zh = '星期一'
}
...
else{
    day_zh = '星期六'
}
//实现同样功能的一种更简单、更容易修改的方法是把这些数据存到一张表里面。
const week = ['星期日', '星期一',..., '星期六']
const day = new Date().getDay()
const day_zh = week[day]
```

### 模块化

模块：类比android 中的模块就是业务模块，单指业务，是按照业务对 app 进行拆分，比如说订单我们搞成一个模块，个人中心我们搞成一个模块，视频，音频这些都搞成模块，在app中的体现就是 一个个module，module 的中文意思也是模块，这不准这就是 google 对我们的暗示呢。模块化的目的时为了搭积木，随便拿几个模块module 出来就可以随随便便的上线一个 app，你还别说现在影子 app 的需求很旺盛，你去看看大公司的项目那个不是一堆影子工程，头条还搞出一个头条视频的马甲呢，这其实就是把视频 module 拿出来，加上一个启动页。这样的例子是比比皆是的，要不说不会组件化影子工程对你就是噩梦呢，哈哈，到时候维护那是想也别想了，代码你要搞多少份啊

