在我们使用 vue时，我们可以引用两个不同版本的 Vue，分别是 Vue完整版（vue.js）和 Vue（vue.runtime.js ）非完整版，那么它们的区别是什么呢，今天我们就来分析下这两个不同版本之间的区别
#### 1. 文件名
![image](https://user-images.githubusercontent.com/81228918/119464801-b2971080-bd75-11eb-906f-de9d6b392d0c.png)

#### 2. 文件大小
完整版：同时包含编译器和运行时的版本。

编译器：用来将模板字符串编译成为 JavaScript 渲染函数的代码。

而非完整版不包含编译器，体积约比完整版小 30%。

#### 3. 视图

完整版

视图写在 HTML里或者 template选项里，由于有 compiler(编译器)的存在，完整版运行时：用来创建 Vue 实例、渲染并处理虚拟 DOM 等的代码。基本上就是除去编译器的其它一切。

非完整版

完整版运行时：当使用 vue-loader 或 vueify 的时候，*.vue 文件内部的模板会在构建时预编译成 JavaScript。你在最终打好的包里实际上是不需要编译器的，所以只用运行时版本即可。
```
// 不需要编译器
new Vue({
 render (h) {
 return h('div', this.hi)
 }
})

// 需要编译器
new Vue({
 template: '<div>{{ hi }}</div>'
})
```
### template解析
```
<body>
   <div id="app">
       <h-title level=1>
           <p>li</p>
       </h-title>
       <h-title level=2>
           <p>li</p>
       </h-title>
   </div>
</body>

</html>
<scriptsrc="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
<script>
//在这里玩们需要通过v-if来进行判断
   Vue.component("h-title", {
       template: `<div>
           <h1 v-if="level==1"><slot></slot></h1>
           <h2 v-else-if="level==2"><slot></slot></h2>
       </div>`,
       props: {
           level: {
               type: Number,
               required: true
          }
      }
  })

   let vm=newVue({
       el: "#app"
  })
</script>
```
render解析
```
<body>
   <divid="app">
       <h-titlelevel=1>
           <p>Alley</p>
       </h-title>
       <h-titlelevel=2>
           <p>Alley</p>
       </h-title>
   </div>
</body>

</html>
<scriptsrc="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
<script>
   Vue.component("h-title", {
       render:function(createElement){
           returncreateElement(
               "h"+this.level,
               this.$slots.default
          )
      },
       props: {
           level: {
               type: Number,
               required: true
          }
      }
  })

   letvm=newVue({
       el: "#app"
  })
</script>
```

