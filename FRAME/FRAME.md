## 框架面试知识点总结
整理了 VUE、React、jQuery、webpack、 Bootstrap面试的部分知识点

### 目录
- [为什么用前端框架](#)

- [VUE](#VUE)
  - [vue的生命周期函数](#vue的生命周期函数)
  - [Vue中父子组件生命周期执行顺序](#vue中父子组件生命周期执行顺序)
  - [vue双向数据绑定原理](#vue双向数据绑定原理)
  - [vuex](#vuex)
  - [MVVM和MVC的区别](#mvvm和mvc的区别)
  - [vue的优点](#vue的优点)
  - [vue的响应式原理](#vue的响应式原理)
  - [发布订阅模式和观察者模式](#发布订阅模式和观察者模式) 发布订阅模式和观察者模式
  - [Object.defineProperty介绍](#objectdefineproperty介绍)
  - [使用Object.defineProperty()来进行数据劫持有什么缺点](#使用objectdefineproperty来进行数据劫持有什么缺点)
  - [v-if和v-show的区别](#v-if和v-show的区别)
  - [vue中created和mounted区别](#vue中created和mounted区别)
  - [为什么vue组件中的data必须是函数](#为什么vue组件中的data必须是函数)
  - [vue的activated和deactivated钩子函数](#vue的activated和deactivated钩子函数)
  - [nextTick用法](#nexttick用法)
  - [vue中key属性的作用](#vue中key属性的作用)
  - [Vue中key属性用index为什么不行](#vue中key属性用index为什么不行)
  - [Vue的路由模式](#vue的路由模式)
  - [vue中$router和$route的区别](#vue中router和route的区别)
  - [vue3带来的新特性/亮点](#vue3带来的新特性亮点)
  - [VDOM：三个part](#VDOM三个part)
  - [为什么使用虚拟DOM(Virtual DOM)](#为什么使用虚拟DOMVirtual-DOM)
  - [Compositon api](#Compositon-api)
  - [Vue diff算法详解](#vue-diff算法详解)
  - [移动端适配的方法](#移动端适配的方法)
  - [rem原理](#rem-原理)
  - [rem和em的区别](#rem和em的区别)
  - [移动端300ms延迟的原因以及解决方案](#移动端300ms延迟的原因以及解决方案)
  - [](#)  5 vue 和 react技术选型
  - [Vue和React数据驱动的区别](#vue和react数据驱动的区别)


- [React](#React)
  - [React生命周期](#React生命周期)  1 React生命周期
  - [](#)  23 组件之间通信
  - [](#)  4. 组件的渲染顺序
  - [](#)  8 React组件和渲染更新过程
  - [](#)  1. React 都做过哪些优化
  - [](#)  13 React有哪些优化性能的手段
  - [](#)  9 diff算法是怎么运作
  - [](#)  24 React router
  - [](#)  18 redux 中间件
  - [](#)  14 Redux实现原理解析
  - [](#)  17 聊聊 Redux 和 Vuex 的设计思想
  - [](#)  19 redux数据管理
  - [](#)  3. React Fiber是什么
  - [](#)  2 React Fiber架构
  - [](#)  5 React Fiber架构总结
  - [](#)  7 React事务机制
  - [](#)  2. 浏览器一帧都会干些什么以及requestIdleCallback的启示
  - [](#)  3 createElement过程
  - [](#)  5 setState
  - [](#)  6 setState原理分析
  - [](#)  4 调和阶段 setState内部干了什么
  - [](#)  22 如何避免ajax数据请求重新获取
  - [](#)  12 为什么 React 元素有一个 $$typeof 属性
  - [](#)  10 合成事件原理
  - [](#)  16 react hooks，它带来了那些便利
  - [](#)  15 connect组件原理分析
  - [](#)  11 JSX语法糖本质
  - [](#)  20 受控组件和非受控组件
  - [](#)  21 SSR原理


- [jQuery](#jQuery)
  - [](#)  2 jQuery 的实现原理
  - [](#)  12 针对 jQuery 的优化方法
  - [](#)  17 jQuery对象的特点
  - [](#)  1 你觉得jQuery或zepto源码有哪些写的好的地方
  - [](#)  11 jQuery 一个对象可以同时绑定多个事件，这是如何实现的
  - [](#)  5 jQuery 的属性拷贝(extend)的实现原理是什么，如何实现深拷贝
  - [](#)  6 jQuery 的队列是如何实现的
  - [](#)  10 jQuery 中如何将数组转化为 JSON 字符串，然后再转化回来
  - [](#)  9 jQuery 通过哪个方法和 Sizzle 选择器结合的
  - [](#)  3 jQuery.fn 的 init 方法返回的 this 指的是什么对象
  - [](#)  4 jQuery.extend 与 jQuery.fn.extend 的区别
  - [](#)  7 jQuery 中的 bind(), live(), delegate(), on()的区别
  - [](#)  8 是否知道自定义事件
  - [](#)  14 jQuery UI 如何自定义组件
  - [](#)  15 jQuery 与 jQuery UI、jQuery Mobile 区别
  - [](#)  13 jQuery 的 slideUp 动画，当鼠标快速连续触发, 动画会滞后反复执行，该如何处理呢
  - [](#)  16 jQuery 和 Zepto 的区别？ 各自的使用场景


- [微信小程序](#微信小程序)
  - [](#)  5 微信小程序与vue区别
  - [](#)  1 微信小程序有几个文件
  - [](#)  2 微信小程序怎样跟事件传值
  - [](#)  3 小程序的 wxss 和 css 有哪些不一样的地方？
  - [](#)  4 小程序关联微信公众号如何确定用户的唯一性


- [webpack相关](#webpack相关)
  - [](#)  1 打包体积 优化思路
  - [](#)  2 打包效率
  - [](#)  3 Loader
  - [](#)  4 说一下webpack的一些plugin，怎么使用webpack对项目进行优化


- [Bootstrap](#Bootstrap)
  - [](#)  1 什么是Bootstrap？以及为什么要使用Bootstrap？
  - [](#)  2 使用Bootstrap时，要声明的文档类型是什么？以及为什么要这样声明？
  - [](#)  3 什么是Bootstrap网格系统
  - [](#)  4 Bootstrap 网格系统（Grid System）的工作原理
  - [](#)  5 对于各类尺寸的设备，Bootstrap设置的class前缀分别是什么
  - [](#)  6 Bootstrap 网格系统列与列之间的间隙宽度是多少
  - [](#)  7 如果需要在一个标题的旁边创建副标题，可以怎样操作
  - [](#)  8 用Bootstrap，如何设置文字的对齐方式？
  - [](#)  9 Bootstrap如何设置响应式表格？
  - [](#)  10 使用Bootstrap创建垂直表单的基本步骤？
  - [](#)  11 使用Bootstrap创建水平表单的基本步骤？
  - [](#)  12 使用Bootstrap如何创建表单控件的帮助文本？
  - [](#)  13 使用Bootstrap激活或禁用按钮要如何操作？
  - [](#)  14 Bootstrap有哪些关于的class？
  - [](#)  15 Bootstrap中有关元素浮动及清除浮动的class？
  - [](#)  16 除了屏幕阅读器外，其他设备上隐藏元素的class？
  - [](#)  17 Bootstrap如何制作下拉菜单？
  - [](#)  18 Bootstrap如何制作按钮组？以及水平按钮组和垂直按钮组的优先级？
  - [](#)  19 Bootstrap如何设置按钮的下拉菜单？
  - [](#)  20 Bootstrap中的输入框组如何制作？
  - [](#)  21 Bootstrap中的导航都有哪些？
  - [](#)  22 Bootstrap中设置分页的class？
  - [](#)  23 Bootstrap中显示标签的class？
  - [](#)  24 Bootstrap中如何制作徽章？
  - [](#)  25 Bootstrap中超大屏幕的作用是什么？






### 为什么用前端框架
- 1.前端框架是为了解决什么问题?
  - 前端要做的工作无非就是根据用户的操作将相应的数据展示到视图中。
  - 为保证状态与UI同步，前端工作人员除了将精力放在业务逻辑上，还需要将大量的精力放在操作DOM上。
  - 频繁的操作DOM，这样的结果导致了代码臃肿，不易维护，容易出错，且浏览器渲染开销大。
  - 为了解决UI与状态同步的问题，出现了前端框架。
  - 前端框架帮助我们减少DOM的操作，同时提高了渲染页面的性能。

- 2.DOM的操作昂贵在什么地方?
  - 访问dom的费用高，比较耗时。而且读取dom集合的length比数组消耗大很多。
  - 修改dom引起重排跟重绘，会伴随着重新渲染的巨大代价。

- 3.渲染引擎的工作流程
  - 解析HTML构建dom树=>构建渲染树=>渲染树布局=>绘制渲染树

- 4.什么是重绘和重排？
  - 重排：如果页面元素位置发生变化，就要从布局阶段重新开始渲染，也就是页面重排。页面重排一定会进行后续重绘。
  - 重绘：如果页面元素只是显示样式改变而布局不变，那么页面内容将会从绘制阶段开始。

- 5.什么情况下触发重排？
  - 修改dom元素的几何属性，dom树结构发生变化，改变浏览器大小等会触发重排的操作。


### VUE

  #### vue的生命周期函数
```
beforeCreate:
在实例初始化之后，数据观测 (data observer) 和 event/watcher 
事件配置之前被调用。

在new一个vue实例后，只有一些默认的生命周期钩子和默认事件，其他的东西
都还没创建。在beforeCreate生命周期执行的时候，data和methods中的
数据都还没有初始化。不能在这个阶段使用data中的数据和methods中的方法

created:
在实例创建完成后被立即调用。在这一步，实例已完成以下的配置：
数据观测 (data observer)，property 和方法的运算，watch/event 事件回调。
然而，挂载阶段还没开始，\$el property 目前尚不可用。

data 和 methods都已经被初始化好了，如果要调用 methods 中的方法，
或者操作 data 中的数据，最早可以在这个阶段中操作

beforeMount:
在挂载开始之前被调用：相关的 render 函数首次被调用。

执行到这个钩子的时候，在内存中已经编译好了模板了，
但是还没有挂载到页面中，此时，页面还是旧的

mounted:
实例被挂载后调用，这时 el 被新创建的 vm.\$el 替换了。
如果根实例挂载到了一个文档内的元素上，
当 mounted 被调用时 vm.\$el 也在文档内。

执行到这个钩子的时候，就表示Vue实例已经初始化完成了。此时组件
脱离了创建阶段，进入到了运行阶段。如果我们想要通过插件操作
页面上的DOM节点，最早可以在这个阶段中进行

beforeUpdate:
当执行这个钩子时，页面中的显示的数据还是旧的，
data中的数据是更新后的， 页面还没有和最新的数据保持同步

updated:
页面显示的数据和data中的数据已经保持同步了，都是最新的

beforeDestroy:
Vue实例从运行阶段进入到了销毁阶段，这个时候上所有的 data 和 
methods，指令，过滤器……都是处于可用状态，还没有真正被销毁

destroyed:
这个时候上所有的 data 和 methods，指令，过滤器……
都是处于不可用状态，组件已经被销毁了。

activated:
被 `keep-alive` 缓存的组件激活时调用。

deactivated:
被 `keep-alive` 缓存的组件停用时调用。
```

```
init：
1.initLifecycle/Event，往vm上挂载各种属性
2.callHook: beforeCreated: 实例刚创建
3.initInjection/initState: 初始化注入和 data 响应性
4.created: 创建完成，属性已经绑定， 但还未生成真实dom`
5.进行元素的挂载： $el / vm.$mount()
6.是否有template: 解析成 render function
    *.vue文件: vue-loader会将<template>编译成render function
7.beforeMount: 模板编译/挂载之前
8.执行render function，生成真实的dom，并替换到dom tree中
9.mounted: 组件已挂载

update：
1.执行diff算法，比对改变是否需要触发UI更新
2.flushScheduleQueue
3.watcher.before: 触发beforeUpdate钩子 - watcher.run(): 
  执行watcher中的 notify，通知所有依赖项更新UI
4.触发updated钩子: 组件已更新
5.actived / deactivated(keep-alive): 不销毁，缓存，组件激活与失活
6.destroy
  beforeDestroy: 销毁开始
  销毁自身且递归销毁子组件以及事件监听
    remove(): 删除节点
    watcher.teardown(): 清空依赖
    vm.$off(): 解绑监听
  destroyed: 完成后触发钩子
  
  
Vue2和Vue3对比：
Vue2	                  Vue3
beforeCreate	          setup(替代)
created	                setup(替代)
beforeMount	            onBeforeMount
mounted	                onMounted
beforeUpdate           	onBeforeUpdate
updated	                nUpdated
beforeDestroy	          onBeforeUnmount
destroyed	              onUnmounted
errorCaptured          	onErrorCaptured
-	                      onRenderTracked
-	                      onRenderTriggered


上面是vue的声明周期的简单梳理，
接下来我们直接以代码的形式来完成vue的初始化：
new Vue({})

// 初始化Vue实例
function _init() {
	 // 挂载属性
    initLifeCycle(vm) 
    // 初始化事件系统，钩子函数等
    initEvent(vm) 
    // 编译slot、vnode
    initRender(vm) 
    // 触发钩子
    callHook(vm, 'beforeCreate')
    // 添加inject功能
    initInjection(vm)
    // 完成数据响应性 props/data/watch/computed/methods
    initState(vm)
    // 添加 provide 功能
    initProvide(vm)
    // 触发钩子
    callHook(vm, 'created')
		
	 // 挂载节点
    if (vm.$options.el) {
        vm.$mount(vm.$options.el)
    }
}

// 挂载节点实现
function mountComponent(vm) {
	 // 获取 render function
    if (!this.options.render) {
        // template to render
        // Vue.compile = compileToFunctions
        let { render } = compileToFunctions() 
        this.options.render = render
    }
    // 触发钩子
    callHook('beforeMounte')
    // 初始化观察者
    // render 渲染 vdom， 
    vdom = vm.render()
    // update: 根据 diff 出的 patchs 挂载成真实的 dom 
    vm._update(vdom)
    // 触发钩子  
    callHook(vm, 'mounted')
}

// 更新节点实现
funtion queueWatcher(watcher) {
	nextTick(flushScheduleQueue)
}

// 清空队列
function flushScheduleQueue() {
	 // 遍历队列中所有修改
    for(){
	    // beforeUpdate
        watcher.before()
         
        // 依赖局部更新节点
        watcher.update() 
        callHook('updated')
    }
}

// 销毁实例实现
Vue.prototype.$destory = function() {
	 // 触发钩子
    callHook(vm, 'beforeDestory')
    // 自身及子节点
    remove() 
    // 删除依赖
    watcher.teardown() 
    // 删除监听
    vm.$off() 
    // 触发钩子
    callHook(vm, 'destoryed')
}
```

  #### Vue中父子组件生命周期执行顺序
```
在单一组件中，钩子的执行顺序是
beforeCreate-> created -> mounted->... ->destroyed
```

父子组件生命周期执行顺序：

加载渲染过程
  ```txt
  父beforeCreate->父created->父beforeMount->子beforeCreate->子created->子beforeMount->子mounted->父mounted
  ```

更新过程
  ```txt
  父beforeUpdate->子beforeUpdate->子updated->父updated
  ```

销毁过程
  ```txt
  父beforeDestroy->子beforeDestroy->子destroyed->父destroyed
  ```

常用钩子简易版
  ```txt
  父create->子created->子mounted->父mounted
  ```

  #### vue双向数据绑定原理
```
vue 通过使用双向数据绑定，来实现了 View 和 Model 的同步更新。
vue 的双向数据绑定主要是通过使用数据劫持和发布订阅者模式来实现的。

首先我们通过 Object.defineProperty() 方法来对 Model 数据各个
属性添加访问器属性，以此来实现数据的劫持，因此当 Model 中的数据
发生变化的时候，我们可以通过配置的 setter 和 getter 方法来
实现对 View 层数据更新的通知。

数据在 html 模板中一共有两种绑定情况，一种是使用 v-model 来对 
value 值进行绑定，一种是作为文本绑定，在对模板引擎进行解析的过程中。

如果遇到元素节点，并且属性值包含 v-model 的话，我们就从 Model 中
去获取 v-model 所对应的属性的值，并赋值给元素的 value 值。
然后给这个元素设置一个监听事件，当 View 中元素的数据发生变化
的时候触发该事件，通知 Model 中的对应的属性的值进行更新。

如果遇到了绑定的文本节点，我们使用 Model 中对应的属性的值来
替换这个文本。对于文本节点的更新，我们使用了发布订阅者模式，
属性作为一个主题，我们为这个节点设置一个订阅者对象，将这个订阅者对象
加入这个属性主题的订阅者列表中。当 Model 层数据发生改变的时候，
Model 作为发布者向主题发出通知，主题收到通知再向它的所有订阅者推送，
订阅者收到通知后更改自己的数据。
```

  #### vuex
```
Vuex 集中式存储管理应用的所有组件的状态，
并以相应的规则保证状态以可预测的方式发生变化

核心概念：
state: 状态中心
mutations: 更改状态
actions: 异步更改状态
getters: 获取状态
modules: 将state分成多个modules，便于管理

1.状态 - state
state保存应用状态

export default new Vuex.Store({ state: { counter:0 },})

2.状态变更 - mutations
mutations用于修改状态，store.js

export default new Vuex.Store({
    mutations:
    {
      add(state) {
        state.counter++
      }
    }
  })
  
3.派生状态 - getters
从state派生出新状态，类似计算属性

export default new Vuex.Store({
    getters:
    {
      doubleCounter(state) { // 计算剩余数量 return state.counter * 2;
      }
    }
  })
  
4.动作 - actions
加业务逻辑，类似于controller

export default new Vuex.Store({
    actions:
    {
      add({
        commit
      }) {
        setTimeout(() = >{}
      }
    })
测试代码:

<p @click="$store.commit('add')">counter: {{$store.state.counter}}</p>
<p @click="$store.dispatch('add')">async counter: {{$store.state.counter}}</p>
<p>double:{{$store.getters.doubleCounter}}</p>

vuex原理解析
(1)实现一个插件:声明Store类，挂载$store
(2)Store具体实现:
  创建响应式的state，保存mutations、actions和getters
  实现commit根据用户传入type执行对应mutation
  实现dispatch根据用户传入type执行对应action，同时传递上下文
  实现getters，按照getters定义对state做派生
  
// 目标1：实现Store类，管理state（响应式的），commit方法和dispatch方法
// 目标2：封装一个插件，使用更容易使用
let Vue;

class Store {
  constructor(options) {
    // 定义响应式的state
    // this.$store.state.xx
    // 借鸡生蛋
    this._vm = new Vue({
      data: {
        $$state: options.state
      }
    })
    
    this._mutations = options.mutations
    this._actions = options.actions

    // 绑定this指向
    this.commit = this.commit.bind(this)
    this.dispatch = this.dispatch.bind(this)
  }

  // 只读
  get state() {
    return this._vm._data.$$state
  }

  set state(val) {
    console.error('不能直接赋值呀，请换别的方式！！天王盖地虎！！');
    
  }
  
  // 实现commit方法，可以修改state
  commit(type, payload) {
    // 拿出mutations中的处理函数执行它
    const entry = this._mutations[type]
    if (!entry) {
      console.error('未知mutaion类型');
      return
    }

    entry(this.state, payload)
  }

  dispatch(type, payload) {
    const entry = this._actions[type]

    if (!entry) {
      console.error('未知action类型');
      return
    }

    // 上下文可以传递当前store实例进去即可
    entry(this, payload)
  }
}

function install(_Vue){
  Vue = _Vue

  // 混入store实例
  Vue.mixin({
    beforeCreate() {
      if (this.$options.store) {
        Vue.prototype.$store = this.$options.store
      }
    }
  })
}

// { Store, install }相当于Vuex
// 它必须实现install方法
export default { Store, install }
```

  #### MVVM和MVC的区别
```
MVC: MVC是应用最广泛的软件架构之一,一般MVC分为:
Model(模型),View(视图),Controller(控制器)。 这主要是
基于分层的目的,让彼此的职责分开.View一般用过Controller来
和Model进行联系。Controller是Model和View的协调者,
View和Model不直接联系。基本都是单向联系。

1. View传送指令到Controller。
2. Controller完成业务逻辑后改变Model状态。
3. Model将新的数据发送至View,用户得到反馈。

MVVM: MVVM是把MVC中的Controller改变成了ViewModel。

View的变化会自动更新到ViewModel,ViewModel的变化
也会自动同步到View上显示,通过数据来显示视图层。

MVVM和MVC的区别:
  MVC中Controller演变成MVVM中的ViewModel
  MVVM通过数据来显示视图层而不是节点操作
  MVVM主要解决了MVC中大量的dom操作使页面渲染性能降低,
  加载速度变慢,影响用户体验
```

  #### vue的优点
```
轻量级框架
简单易学
双向数据绑定
组件化
视图，数据，结构分离
虚拟 DOM
运行速度更快
```

  #### vue的响应式原理
```
数据发生变化后，会重新对页面渲染，这就是 Vue 响应式

想完成这个过程，我们需要：
  侦测数据的变化
  收集视图依赖了哪些数据
  数据变化时，自动“通知”需要更新的视图部分，并进行更新

对应专业俗语分别是：
数据劫持 / 数据代理
依赖收集
发布订阅模式
```

```
Vue 的响应式原理是核心是通过 ES5 的保护对象的 Object.defindeProperty 
中的访问器属性中的 get 和 set 方法，data 中声明的属性都被添加了
访问器属性，当读取 data 中的数据时自动调用 get 方法，当修改 data 
中的数据时，自动调用 set 方法，检测到数据的变化，会通知观察者 Wacher，
观察者 Wacher自动触发重新render 当前组件（子组件不会重新渲染）,
生成新的虚拟 DOM 树，Vue 框架会遍历并对比新虚拟 DOM 树和
旧虚拟 DOM 树中每个节点的差别，并记录下来，最后，加载操作，
将所有记录的不同点，局部修改到真实 DOM树上。

1.虚拟DOM (Virtaul DOM): 用 js 对象模拟的，保存当前视图内所有 
  DOM 节点对象基本描述属性和节点间关系的树结构。用 js 对象，
  描述每个节点，及其父子关系，形成虚拟 DOM 对象树结构。
2.因为只要在 data 中声明的基本数据类型的数据，基本不存在
  数据不响应问题，所以重点介绍数组和对象在vue中的数据响应问题，
  vue可以检测对象属性的修改，但无法监听数组的所有变动及
  对象的新增和删除，只能使用数组变异方法及$set方法。

总结：Vue 采用数据劫持结合发布—订阅模式的方法，通过
Object.defineProperty() 来劫持各个属性的 setter，getter，
在数据变动时发布消息给订阅者，触发相应的监听回调。

1.Observer 遍历数据对象，给所有属性加上 setter 和 getter，监听数据的变化
2.compile 解析模板指令，将模板中的变量替换成数据，
  然后初始化渲染页面视图，并将每个指令对应的节点绑定更新函数，
  添加监听数据的订阅者，一旦数据有变动，收到通知，更新视图
  
  Watcher 订阅者是 Observer 和 Compile 之间通信的桥梁，主要做的事情

1.在自身实例化时往属性订阅器 (dep) 里面添加自己
2.待属性变动 dep.notice() 通知时，调用自身的 update() 方法，
  并触发 Compile 中绑定的回调
  
Object.defineProperty()，那么它的用法是什么，以及优缺点是什么呢？
  1.可以检测对象中数据发生的修改
  2.对于复杂的对象，层级很深的话，是不友好的，需要经行深度监听，
    这样子就需要递归到底，这也是它的缺点。
  3.对于一个对象中，如果你新增加属性，删除属性，
    **Object.defineProperty()**是不能观测到的，那么应该如何解决呢？
    可以通过Vue.set()和Vue.delete()来实现。
// 模拟 Vue 中的 data 选项 
let data = {
    msg: 'hello'
}
// 模拟 Vue 的实例 
let vm = {}
// 数据劫持:当访问或者设置 vm 中的成员的时候，做一些干预操作
Object.defineProperty(vm, 'msg', {
  // 可枚举(可遍历)
  enumerable: true,
  // 可配置(可以使用 delete 删除，可以通过 defineProperty 重新定义) 
  configurable: true,
  // 当获取值的时候执行 
  get () {
    console.log('get: ', data.msg)
    return data.msg 
  },
  // 当设置值的时候执行 
  set (newValue) {
    console.log('set: ', newValue) 
    if (newValue === data.msg) {
      return
    }
    data.msg = newValue
    // 数据更改，更新 DOM 的值 
    document.querySelector('#app').textContent = data.msg
  } 
})

// 测试
vm.msg = 'Hello World' 
console.log(vm.msg)

Vue3.x响应式数据原理：
Vue3.x改用Proxy替代Object.defineProperty。因为Proxy可以
直接监听对象和数组的变化，并且有多达13种拦截方法。
并且作为新标准将受到浏览器厂商重点持续的性能优化。

Proxy只会代理对象的第一层，那么Vue3又是怎样处理这个问题的呢？
判断当前Reflect.get的返回值是否为Object，如果是则
再通过reactive方法做代理， 这样就实现了深度观测。

监测数组的时候可能触发多次get/set，那么如何防止触发多次呢？
我们可以判断key是否为当前被代理对象target自身属性，也可以判断
旧值与新值是否相等，只有满足以上两个条件之一时，才有可能执行trigger

// 模拟 Vue 中的 data 选项 
let data = {
  msg: 'hello',
  count: 0 
}
// 模拟 Vue 实例
let vm = new Proxy(data, {
  // 当访问 vm 的成员会执行
  get (target, key) {
    console.log('get, key: ', key, target[key])
    return target[key]
  },
  // 当设置 vm 的成员会执行
  set (target, key, newValue) {
    console.log('set, key: ', key, newValue)
    if (target[key] === newValue) {
      return
    }
    target[key] = newValue
    document.querySelector('#app').textContent = target[key]
  }
})

// 测试
vm.msg = 'Hello World'
console.log(vm.msg)

Proxy 相比于 defineProperty 的优势
数组变化也能监听到
不需要深度遍历监听

Proxy 是 ES6 中新增的功能，可以用来自定义对象中的操作

let p = new Proxy(target, handler);
// `target` 代表需要添加代理的对象
// `handler` 用来自定义对象中的操作
// 可以很方便的使用 Proxy 来实现一个数据绑定和监听

let onWatch = (obj, setBind, getLogger) => {
  let handler = {
    get(target, property, receiver) {
      getLogger(target, property)
      return Reflect.get(target, property, receiver);
    },
    set(target, property, value, receiver) {
      setBind(value);
      return Reflect.set(target, property, value);
    }
  };
  return new Proxy(obj, handler);
};

let obj = { a: 1 }
let value
let p = onWatch(obj, (v) => {
  value = v
}, (target, property) => {
  console.log(`Get '${property}' = ${target[property]}`);
})
p.a = 2 // bind `value` to `2`
p.a // -> Get 'a' = 2

总结：
Vue
  记录传入的选项，设置 $data/$el
  把 data 的成员注入到 Vue 实例
  负责调用 Observer 实现数据响应式处理(数据劫持)
  负责调用 Compiler 编译指令/插值表达式等
Observer
  数据劫持
    负责把 data 中的成员转换成 getter/setter
    负责把多层属性转换成 getter/setter
    如果给属性赋值为新对象，把新对象的成员设置为 getter/setter
    添加 Dep 和 Watcher 的依赖关系
    数据变化发送通知
Compiler
  负责编译模板，解析指令/插值表达式
  负责页面的首次渲染过程
  当数据变化后重新渲染
Dep
  收集依赖，添加订阅者(watcher)
  通知所有订阅者
Watcher
  自身实例化的时候往dep对象中添加自己
  当数据变化dep通知所有的 Watcher 实例更新视图
```

  #### 发布订阅模式和观察者模式
```
1. 发布/订阅模式
  发布/订阅模式
    订阅者
    发布者
    信号中心
我们假定，存在一个"信号中心"，某个任务执行完成，就向信号中心
"发布"(publish)一个信 号，其他任务可以向信号中心"订阅"(subscribe)
这个信号，从而知道什么时候自己可以开始执行。
这就叫做"发布/订阅模式"(publish-subscribe pattern)

Vue 的自定义事件：
let vm = new Vue()
vm.$on('dataChange', () => { console.log('dataChange')})
vm.$on('dataChange', () => { 
  console.log('dataChange1')
}) 
vm.$emit('dataChange')

兄弟组件通信过程：
// eventBus.js
// 事件中心
let eventHub = new Vue()

// ComponentA.vue
// 发布者
addTodo: function () {
  // 发布消息(事件)
  eventHub.$emit('add-todo', { text: this.newTodoText }) 
  this.newTodoText = ''
}
// ComponentB.vue
// 订阅者
created: function () {
  // 订阅消息(事件)
  eventHub.$on('add-todo', this.addTodo)
}

模拟 Vue 自定义事件的实现：
class EventEmitter {
  constructor(){
    // { eventType: [ handler1, handler2 ] }
    this.subs = {}
  }
  // 订阅通知
  $on(eventType, fn) {
    this.subs[eventType] = this.subs[eventType] || []
    this.subs[eventType].push(fn)
  }
  // 发布通知
  $emit(eventType) {
    if(this.subs[eventType]) {
      this.subs[eventType].forEach(v=>v())
    }
  }
}

// 测试
var bus = new EventEmitter()

// 注册事件
bus.$on('click', function () {
  console.log('click')
})

bus.$on('click', function () {
  console.log('click1')
})

// 触发事件 
bus.$emit('click')

2. 观察者模式
  观察者(订阅者) -- Watcher
    update():当事件发生时，具体要做的事情
  目标(发布者) -- Dep
    subs 数组:存储所有的观察者
    addSub():添加观察者
    notify():当事件发生，调用所有观察者的 update() 方法
  没有事件中心
// 目标(发布者) 
// Dependency
class Dep {
  constructor () {
    // 存储所有的观察者
    this.subs = []
  }
  // 添加观察者
  addSub (sub) {
    if (sub && sub.update) {
      this.subs.push(sub)
    }
  }
  // 通知所有观察者
  notify () {
    this.subs.forEach(sub => sub.update())
  }
}

// 观察者(订阅者)
class Watcher {
  update () {
    console.log('update')
  }
}

// 测试
let dep = new Dep()
let watcher = new Watcher()
dep.addSub(watcher) 
dep.notify()

3. 总结
1.观察者模式是由具体目标调度，比如当事件触发，Dep 就会去调用
观察者的方法，所以观察者模 式的订阅者与发布者之间是存在依赖的
2.发布/订阅模式由统一调度中心调用，因此发布者和订阅者不需要知道对方的存在

```

  #### Object.defineProperty介绍
```
Object.defineProperty 函数一共有三个参数，第一个参数是需要
定义属性的对象，第二个参数是需要定义的属性，第三个是该属性描述符。

一个属性的描述符有一下属性，分别是：
value 属性的值，
writable 属性是否可写，
enumerable 属性是否可枚举，
configurable 属性是否可配置修改。
get属性 当访问该属性时，会调用此函数
set属性 当属性值被修改时，会调用此函数。
```

  #### 使用Object.defineProperty()来进行数据劫持有什么缺点
```
有一些对属性的操作，使用这种方法无法拦截，比如说通过下标方式修改
数组数据或者给对象新增属性，vue 内部通过重写函数解决了这个问题。

在 Vue3.0 中已经不使用这种方式了，而是通过使用 Proxy 对对象进行
代理，从而实现数据劫持。使用 Proxy 的好处是它可以完美的监听到
任何方式的数据改变，唯一的缺点是兼容性的问题，因为这是 ES6 的语法。
```

  #### v-if和v-show的区别
```
v-if：每次都会重新删除或创建元素来控制 DOM 结点的存在与否

v-show:是切换了元素的样式 display:none，display: block

因而 v-if 有较高的切换性能消耗，v-show 有较高的初始渲染消耗
```

  #### vue中created和mounted区别
- created:在模板渲染成html前调用，即通常初始化某些属性值，然后再渲染成视图。
- mounted:在模板渲染成html后调用，通常是初始化页面完成后，再对html的dom节点进行一些需要的操作。

```
其实两者比较好理解，通常created使用的次数多，而mounted通常是
在一些插件的使用或者组件的使用中进行操作，比如插件chart.js的使用: 
var ctx = document.getElementById(ID); 通常会有这一步，
而如果你写入组件中，你会发现在created中无法对chart进行一些初始化配置，
一定要等这个html渲染完后才可以进行，那么mounted就是不二之选。
```

  #### vue中data和computed区别
data 和 computed都是响应式的，先看看官方的说法：
```
Data:
Vue 实例的数据对象。Vue 将会递归将 data 的属性转换为 
getter/setter，从而让 data 的属性能够响应数据变化。

深入理解响应式原理：
当你把一个普通的 JavaScript 对象传给 Vue 实例的 data 选项，
Vue 将遍历此对象所有的属性，并使用 Object.defineProperty 
把这些属性全部转为 getter/setter。

每个组件实例都有相应的 watcher 实例对象，它会在组件渲染
的过程中把属性记录为依赖，之后当依赖项的 setter 被调用时，
会通知 watcher 重新计算，从而致使它关联的组件得以更新。
```

2.两者的区别：
```
data中的属性并不会随赋值变量的改动而改动，(赋值变量类似：
num1: aaa.bbb这种，而这种是直接赋值：num1: "aaa")
```

```
当需要这种随赋值变量的改动而改动的时候，还是用计算属性
computed合适如果实在要在data里面声明属性，可以先赋一个值，
然后在methods里面定义方法操作该属性，效果等同，也会有响应式
```

computed:
- 1、基本使用：
```
在computed中定义一个函数(看起来是一个函数，其实是一个属性)，
命名按照属性规范命名(一般为名词)。
```

  - 1.1 应用场景：
```
当数据A的逻辑很复杂时，把A这个数据写在计算属性中。
```

  - 1.2 代码位置：
```
通过选项computed：{计算属性a:值}
```

  - 1.3 值：
```
带有返回值return的函数。
```

```
计算属性a和data中的数据用法一样。计算属性在computed中进行定义，
无需再在data中定义，在template中直接可进行使用，
使用方式与data中定义的数据一样。

{{msg}}
{{str}}

var vm = new Vue({
el: '#app',

data: {
msg: 'abc'
},

computed: {
str: function () {
return this.msg
}
},

methods: {
}

})
```

- 2、复杂操作-结合data中数据：
```
当计算属性b依赖了data中的数据a时，当a变化时，b会自动变化。
这也是在开发中通常用到的情况。比如在购物的时候，下某一订单时，
每选择一件商品(对应data中的数据a)，
合计费用(对应计算属性b)就会跟着变化。
```

```
总价格：{{totalPrice}}
var vm = new Vue({
el: '#app',

data: {
books: [
{ id: 1000, name: 'Linux编程之美', price: 50 },
{ id: 1001, name: 'Java疯狂讲义', price: 60 },
{ id: 1002, name: '深入理解计算机原理', price: 80 },
{ id: 1003, name: '操作系统', price: 30 },
{ id: 1004, name: '数据结构导论', price: 60 },
]
},

computed: {
totalPrice() {
let result = 0;

for (let i = 0; i < this.books.length; i++) {
result += this.books[i].price;
}

return result
}
},

methods: {
}
})
```

- 3、计算属性写法演变：
  - 3.1 计算属性的setter和getter：
```
computed：{
//computed里面是大括号，本身就是对象。
}
```

完整的计算属性写法：属性+方法
```
computed: {
//定义属性

totalPrice: {
//totalPrice 属性对应的是对象，不是字符串。对象就会有方法。

//该属性对应的set方法 和get方法

//计算属性一般是没有set方法的，是只读属性。

//【此处set测试失败 没有出现预期效果】

set: function (newValue) {
console.log('get方法调用啦', newValue);
},

get: function () {
console.log('计算属性完整写法：计算啦');

let result = 0;

for (let i = 0; i < this.books.length; i++) {
result += this.books[i].price;
}

return result
}
}
},
```

计算属性一般只有get方法，是只读属性。所以一般写法为：
```
computed: {
totalPrice: function () {
//后面对应的即为get方法。totalPrice就是一个属性，调用时采用属性调用的方式，区别于方法调用()

console.log('计算属性一般写法：计算啦');

let result = 0;

for (let i = 0; i < this.books.length; i++) {
result += this.books[i].price;

}

return result

}

},
```

语法糖—简化写法：
```
computed: {
totalPrice() {
console.log('计算属性语法糖写法：计算啦');

let result = 0;

for (let i = 0; i < this.books.length; i++) {
result += this.books[i].price;

}

return result

}

},
```

- 4、项目中实例：
```
以上即为计算属性computed的使用方式。最近在项目开发中，
有个需求为:【考试配题模块】配置某一题型(例如选择题/简答题等
某类试题)个数或者每一小题分数时，会实时计算出当前选择的
某类试题拥有的个数和当前题目个数所对应的小题分数的总分之和。
```
```
template中代码：

课程名称：{{ courseName }}
总题数：{{ allQuestion }}个
当前总分：{{ allValue }}分
computed中代码：

allQuestion: function() {
var num = 0;

this.selectedObj.forEach((item) => {
num += item.questionNum; //questionNum为拿到的selectedObj对象中的需要使用的属性

});

return num;

},

//计算总分

allValue: function() {
var source = 0;

this.selectedObj.forEach((item) => {
source += item.questionValue * item.questionNum; //questionValue 为拿到的selectedObj对象中的需要使用的属性

});

return source;

},

},

computed中依赖的data中数据部分：

// 子组件给父组件传过来的对象

selectedObj: [],
```

  #### vue中watch和computed区别
```
watch主要是监听数据变化，可以监听数据来源的三个部分：props,data,computed内的数据，然后它还提供两个参数
（new,old）,顺序一定是新值、旧值。

computed主要是处理逻辑运算，computed来存储需要处理的数据值，
它有存储的机制，只有改变时才执行。
```

  #### vue中methods,watch和computer区别
methods,watch和computed都是以函数为基础的，但各自却都不同。

- 一、作用机制上
  - 1.watch和computed都是以Vue的依赖追踪机制为基础的，它们都试图处理这样一件事情：当某一个数据（称它为依赖数据）发生变化的时候，所有依赖这个数据的“相关”数据“自动”发生变化，也就是自动调用相关的函数去实现数据的变动。
  - 2.对methods:methods里面是用来定义函数的，很显然，它需要手动调用才能执行。而不像watch和computed那样，“自动执行”预先定义的函数。
```

- 二、从性质上
  - 1.methods里面定义的是函数，你显然需要像"fuc()"这样去调用它（假设函数为fuc）。
  - 2.computed是计算属性，事实上和和data对象里的数据属性是同一类的（使用上）。
  - 3.watch:类似于监听机制+事件机制。
```
例如：
watch: {
   firstName: function(val) {this.fullName = val +this.lastName }
}

firstName的改变是这个特殊“事件”被触发的条件，
而firstName对应的函数就相当于监听到事件发生后执行的方法
```

- 三、watch和computed的对比
```
首先它们都是以Vue的依赖追踪机制为基础的，它们的共同点是：
都是希望在依赖数据发生改变的时候，被依赖的数据根据预先定义
好的函数，发生“自动”的变化。我们当然可以自己写代码完成这一切，
但却很可能造成写法混乱，代码冗余的情况。
```
 
但watch和computed也有明显不同的地方：
```
watch和computed各自处理的数据关系场景不同

1.watch擅长处理的场景：一个数据影响多个数据

2.computed擅长处理的场景：一个数据受多个数据影响

相比于watch/computed，methods不处理数据逻辑关系，只提供可调用的函数
```

```
在vue中处理复杂的逻辑的时候，我们经常使用计算属性computer，
但是很多时候，我们会把计算属性、方法和侦听器搞混淆，
在 w3cplus.com的一篇文章中是这样总结这三者的。
```
- methods：正如他的名字一样，它们是挂载在对象上的函数，通常是Vue实例本身或Vue组件。
- computed：属性最初看起来像一个方法，但事实却又不是方法。在Vue中，我们使用data来跟踪对特定属性的更改，得到一定的反应。计算属性允许我们定义一个与数据使用相同方式的属性，但也可以有一些基于其依赖关系的自定义逻辑。你可以考虑计算属性的另一个视图到你的数据。
- watchers：这些可以让你了解反应系统（Reactivity System）。我们提供了一些钩子来观察Vue存储的任何属性。如果我们想在每次发生变化时添加一些功能，或者响应某个特定的变化，我们可以观察一个属性并应用一些逻辑。这意味着观察者的名字必须与我们所观察到的相符。
如果仅仅只是看这段话，可能还是不能很清除的明白三者的区别，我们可以通过相关的实例来对三者进行区分。

computed
计算属性是根据依赖关系进行缓存的计算，并且只在需要的时候进行更新。
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>vue</title>
    <script src="./vue.js"></script>
</head>
<body>
    <div id="demo">
        <p>原数据{{message}}</p>
        <p>反转后的数据{{reversedMessage}}</p>
        <button @click="add()">补充货物1</button>
        <div>总价为：{{price}}</div>
    </div>
    <script>
        var demo = new Vue({
              el: ‘#demo‘,
              data: {
                message :‘abcdefg‘,
                package: {
                    count: 5,
                    price: 5
                },
              },
              computed:{
                  reversedMessage:function(){
                      return this.message.split(‘‘).reverse().join(‘‘)
                  },
                price: function(){
                     return this.package.count*this.package.price　　
                 }
            },
             methods: {   
                add: function(){
                    this.package.count++
                }
            }    
        })
    </script>    
</body>
</html>
```

```
上面的例子中展示了计算属性的两种用法：一个计算属性里面可以完成
各种复杂的逻辑，最终返回一个结果；计算属性可以依赖多个vue实例的
数据，只要其中一个任何一个数据发生变化，计算属性就会重新执行，视图
也会更新。除此之外，计算属性还可以依赖其他计算属性和其他实例的数据。
```

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>vue</title>
    <script src="./vue.js"></script>
</head>
<body>
    <div id="app1">{{text}}</div>
    <div id="app2">{{ reverseText}}</div>
    <script>
        var app1 = new Vue({
           el: ‘#app1‘,
             data: {
                  text: ‘computed‘
            }
        });

        var app2 = new Vue({
            el: ‘#app2‘,
            computed: {
                reverseText: function(){
                    return app1.text.split(‘‘).reverse().join(‘‘);  
                }
            }
        });
    </script>    
</body>
</html>
```

methods
```
在使用vue的时候，可能会用到很多的方法，它们可以将功能连接到
事件的指令，甚至只是创建一个小的逻辑就像其他函数一样被重用。
接下来我们用方法实现上面的字符串反转。
```

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>vue</title>
    <script src="./vue.js"></script>
</head>
<body>
    <div id="demo">
        <p>原数据{{message}}</p>
        <p>反转后的数据{{ reversedMessage() }}</p>
    </div>
    <script>
        var demo = new Vue({
              el: ‘#demo‘,
              data: {
                message :‘abcdefg‘,
                num:5
              },
              methods:{
                reversedMessage(){
                    return this.message.split(‘‘).reverse().join(‘‘)
                },
            }
        })
    </script>    
</body>
</html>
```

``
虽然使用计算属性和methods方法来实现反转，两种方法得到的结果
是相同的，但本质是不一样的，计算属性是基于它们的依赖进行缓存的。
计算属性只有在它的相关依赖发生改变的时候才会重新求值，这就意味
着只要message还没有发生改变，多次访问reversedMessage计算属性
立即返回的是之前计算的结果，而不会再次执行计算函数，
而对于methods方法，只要发生重新渲染，methods调用总会执行该函数。

如果某个计算属性a需要的遍历一个极大的数组和做大量的计算，
可以减小性能开销，如果不希望有缓存，则用methods。
```

watch
```
watch属性是一个对象，键是需要观察的表达式，值是对应回调函数，
回调函数得到的参数为新值和旧值。值也可以是方法名，或者包含选项
的对象。侦察器对于任何更新的东西都有用——无论是表单输入、异步更新
还是动画。vue实例在实例化时调用$watch()，遍历watch对象的每一个属性。
```

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>vue</title>
    <script src="./vue.js"></script>
</head>
<body>
    <div id="demo">
        <button @click=‘a++‘>a加1</button>
        <p>{{message}}</p>
    </div>
    <script>
        var demo = new Vue({
              el: ‘#demo‘,
              data: {
                message :‘‘,
                a:1
              },
              
              watch:{
              a:function(val,oldval){
                this.message = ‘a的旧值为‘ + oldval + ‘,新值为‘ + val;
              }
            }
        })
    </script>    
</body>
</html>
```





  #### 为什么vue组件中的data必须是函数
```
<!-- 一个组件被复用多次的话，也就会创建多个实例。本质上，这些实例
用的都是同一个构造函数，如果data是对象的话，对象属性引用类型，
会影响到所有的实例，为了保证组件不同的实例之间的data互不冲突，
data必须是一个函数。 -->

当一个组件被定义，data 必须声明为返回一个初始数据对象的函数，
因为组件可能被用来创建多个实例。如果 data 仍然是一个纯粹的对象，
则所有的实例将共享引用同一个数据对象！通过提供 data 函数，
每次创建一个新实例后，我们能够调用 data 函数，
从而返回初始数据的一个全新副本数据对象。

简而言之，就是 data 中数据可能会被复用，
要保证不同组件调用的时候数据是相同的。
```

  #### vue的activated和deactivated钩子函数
```html
<keep-alive>
  <component :is="view"></component>
</keep-alive>
```

```
`keep-alive`包裹动态组件时，会缓存不活动的组件实例，而不是销毁它们。

当组件在 `<keep-alive>` 内被切换，它的 `activated` 
和 `deactivated` 这两个生命周期钩子函数将会被对应执行。

`activated`在`keep-alive`组件激活时调用，
该钩子函数在服务器端渲染期间不被调用。
`deactivated`在`keep-alive`组件停用时调用，
该钩子函数在服务端渲染期间不被调用。
```

  #### nextTick用法
官网解释：
```
将回调延迟到下次 DOM 更新循环之后执行。
在修改数据之后立即使用它，然后等待 DOM 更新。
```

```html
<div class="app">
  <div ref="msgDiv">{{msg}}</div>
  <div v-if="msg1">Message got outside $nextTick: {{msg1}}</div>
  <div v-if="msg2">Message got inside $nextTick: {{msg2}}</div>
  <div v-if="msg3">Message got outside $nextTick: {{msg3}}</div>
  <button @click="changeMsg">
    Change the Message
  </button>
</div>
```

```vue
new Vue({
  el: '.app',
  data: {
    msg: 'Hello Vue.',
    msg1: '',
    msg2: '',
    msg3: ''
  },
  methods: {
    changeMsg() {
      this.msg = "Hello world."
      this.msg1 = this.$refs.msgDiv.innerHTML
      this.$nextTick(() => {
        this.msg2 = this.$refs.msgDiv.innerHTML
      })
      this.msg3 = this.$refs.msgDiv.innerHTML
    }
  }
})
```

```
nextTick 可以让我们在下次 DOM 更新循环结束之后
执行延迟回调，用于获得更新后的 DOM

nextTick主要使用了宏任务和微任务。根据执行环境分别尝试采用

Promise
MutationObserver
setImmediate
如果以上都不行则采用setTimeout
定义了一个异步方法，多次调用nextTick会将方法
存入队列中，通过这个异步方法清空当前队列
```

  #### vue中key属性的作用
```
一句话 key 的作用主要是为了高效的更新虚拟 DOM

key 的特殊 attribute 主要用在 Vue 的虚拟 DOM 算法，在新旧 nodes 
对比时辨识 VNodes。如果不使用 key，Vue 会使用一种最大限度减少
动态元素并且尽可能的尝试就地修改/复用相同类型元素的算法。而使用 key 时，
它会基于 key 的变化重新排列元素顺序，并且会移除 key 不存在的元素。

有相同父元素的子元素必须有独特的 key。重复的 key 会造成渲染错误。
```

  #### Vue中key属性用index为什么不行
这是由于diff算法的机制所决定的，话不多说，直接上反例：
当我们选中某一个（比如第3个），再添加或删除内容的时候就能发现bug了

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>

</head>
<body>
    <div id="app">
        <span>ID:</span><input type="text" v-model="id">
        <span>Name:</span><input type="text" v-model="name">
        <button @click="handleClick">添加</button>

        <div v-for="(item, index) in list" :key="index">
            <input type="checkbox" />
            <span @click="handleDelete(index)">{{item.id}} --- {{item.name}}</span>
        </div>
    </div>
    <script>
        let vm = new Vue({
            el: '#app',
            data: {
                id: '',
                name: '',
                list: [
                    {id: 1, name: '张三'},
                    {id: 2, name: '李四'},
                    {id: 3, name: '王五'},
                    {id: 4, name: '赵六'},
                ]
            },
            methods: {
                handleClick() {
                    this.list.unshift({
                        id: this.id,
                        name: this.name
                    })
                },
                handleDelete(index) {
                    this.list.splice(index, 1)
                }
            },
        })
    </script>
</body>
</html>
```

  #### Vue的路由模式
> hash模式 与 history模式
> 
- hash（即地址栏 URL 中的 # 符号)。

```txt
比如这个 URL：www.123.com/#/test，hash 的值为 #/test。

特点： hash 虽然出现在 URL 中，但不会被包括在 HTTP，因为我们hash每次页面切换其实切换的是#之后的内容，而#后内容的改变并不会触发地址的改变，
所以不存在向后台发出请求，对后端完全没有影响，因此改变 hash 不会重新加载页面。

每次hash发生变化时都会调用 onhashchange事件

优点：可以随意刷新
```

- history（利用了浏览器的历史记录栈）

```txt
特点：利用了 HTML5 History Interface 中新增的 
pushState() 和 replaceState() 方法。（需要特定浏览器支持）

在当前已有的 back、forward、go的基础之上，它们提供了对
历史记录进行修改的功能。只是当它们执行修改时，虽然改变了
当前的URL，但浏览器不会立即向后端发送请求。

history：可以通过前进 后退控制页面的跳转，刷新是真是的改变url。

缺点：不能刷新，需要后端进行配置。由于history模式下是可以
自由修改请求url，当刷新时如果不对对应地址进行匹配就会返回404。
但是在hash模式下是可以刷新的，前端路由修改的是#中的信息，
请求时地址是不会变的
```

  #### vue中$router和$route的区别
- this.\$route：当前激活的路由的信息对象。每个对象都是局部的，
  可以获取当前路由的 path, name, params, query 等属性。

- this.\$router：全局的 router 实例。通过 vue 根实例中注入 
  router 实例，然后再注入到每个子组件，从而让整个应用都有路由功能。
  其中包含了很多属性和对象（比如 history 对象），
  任何页面也都可以调用其 push(), replace(), go() 等方法。

  #### vue3带来的新特性/亮点
1. 压缩包体积更小
```
当前最小化并被压缩的 Vue 运行时大小约为 20kB（2.6.10 版为 22.8kB）。
Vue 3.0捆绑包的大小大约会减少一半，即只有10kB！
```

2. Object.defineProperty -> Proxy
- Object.defineProperty是一个相对比较昂贵的操作，因为它
  直接操作对象的属性，颗粒度比较小。将它替换为es6的Proxy，
  在目标对象之上架了一层拦截，代理的是对象而不是对象的属性。
  这样可以将原本对对象属性的操作变为对整个对象的操作，颗粒度变大。
- javascript引擎在解析的时候希望对象的结构越稳定越好，
  如果对象一直在变，可优化性降低，proxy不需要对原始对象做太多操作。

3. Virtual DOM 重构
```
vdom的本质是一个抽象层，用javascript描述界面渲染成什么样子。
react用jsx，没办法检测出可以优化的动态代码，所以做时间分片，
vue中足够快的话可以不用时间分片
```

- 传统vdom的性能瓶颈：
  - 虽然 Vue 能够保证触发更新的组件最小化，但在单个组件
    内部依然需要遍历该组件的整个 vdom 树。
  - 传统 vdom 的性能跟模版大小正相关，跟动态节点的数量无关。
    在一些组件整个模版内只有少量动态节点的情况下，
    这些遍历都是性能的浪费。
  - JSX 和手写的 render function 是完全动态的，
    过度的灵活性导致运行时可以用于优化的信息不足

- 那为什么不直接抛弃vdom呢？
  - 高级场景下手写 render function 获得更强的表达力
  - 生成的代码更简洁
  - 兼容2.x
```
vue的特点是底层为Virtual DOM，上层包含有大量静态信息的模版。
为了兼容手写 render function，最大化利用模版静态信息，
vue3.0采用了动静结合的解决方案，将vdom的操作颗粒度变小，
每次触发更新不再以组件为单位进行遍历，主要更改如下
```

- 将模版基于动态节点指令切割为嵌套的区块
- 每个区块内部的节点结构是固定的
- 每个区块只需要以一个 Array 追踪自身包含的动态节点
```
vue3.0将 vdom 更新性能由与模版整体大小相关提升为
与动态内容的数量相关
```

Vue 3.0 动静结合的 Dom diff：
- Vue3.0 提出动静结合的 DOM diff 思想，动静结合的 DOM diff
  其实是在预编译阶段进行了优化。之所以能够做到预编译优化，
  是因为 Vue core 可以静态分析 template，在解析模版时，
  整个 parse 的过程是利用正则表达式顺序解析模板，当解析到
  开始标签、闭合标签和文本的时候都会分别执行对应的回调函数，
  来达到构造 AST 树的目的。
- 借助预编译过程，Vue 可以做到的预编译优化就很强大了。比如在
  预编译时标记出模版中可能变化的组件节点，再次进行渲染前 diff 时
  就可以跳过“永远不会变化的节点”，而只需要对比“可能会变化的动态节点”。
  这也就是动静结合的 DOM diff 将 diff 成本与模版大小正相关
  优化到与动态节点正相关的理论依据。
  
4. Performance
```
vue3在性能方面比vue2快了2倍。
```
- 重写了虚拟DOM的实现
- 运行时编译
- update性能提高
- SSR速度提高

5. Tree-shaking support
```
vue3中的核心api都支持了tree-shaking，这些api都是通过包引入的方式
而不是直接在实例化时就注入，只会对使用到的功能或特性进行打包
（按需打包），这意味着更多的功能和更小的体积。
```

6. Composition API
```
vue2中，我们一般会采用mixin来复用逻辑代码，用倒是挺好用的，不过
也存在一些问题：例如代码来源不清晰、方法属性等冲突。基于此在vue3
中引入了Composition API（组合API），使用纯函数分隔复用代码。
和React中的hooks的概念很相似
```
- 更好的逻辑复用和代码组织
- 更好的类型推导

```
<template>
    <div>X: {{ x }}</div>
    <div>Y: {{ y }}</div>
</template>

<script>
import { defineComponent, onMounted, onUnmounted, ref } from "vue";

const useMouseMove = () => {
    const x = ref(0);
    const y = ref(0);

    function move(e) {
        x.value = e.clientX;
        y.value = e.clientY;
    }

    onMounted(() => {
        window.addEventListener("mousemove", move);
    });

    onUnmounted(() => {
        window.removeEventListener("mousemove", move);
    });

    return { x, y };
};

export default defineComponent({
    setup() {
        const { x, y } = useMouseMove();

        return { x, y };
    }
});
</script>
```

7. 新增的三个组件Fragment、Teleport、Suspense
Fragment
```
在书写vue2时，由于组件必须只有一个根节点，很多时候会添加一些
没有意义的节点用于包裹。Fragment组件就是用于解决这个问题的
（这和React中的Fragment组件是一样的）。
```

这意味着现在可以这样写组件了。
```
/* App.vue */
<template>
  <header>...</header>
  <main v-bind="$attrs">...</main>
  <footer>...</footer>
</template>

<script>
export default {};
</script>
```

或者这样
```
// app.js
import { defineComponent, h, Fragment } from 'vue';

export default defineComponent({
    render() {
        return h(Fragment, {}, [
            h('header', {}, ['...']),
            h('main', {}, ['...']),
            h('footer', {}, ['...']),
        ]);
    }
});
```

Teleport
```
Teleport其实就是React中的Portal。Portal 提供了一种将
子节点渲染到存在于父组件以外的 DOM 节点的优秀的方案。
```

一个 portal 的典型用例是当父组件有 overflow: hidden 或 
z-index 样式时，但你需要子组件能够在视觉上“跳出”其容器。
例如，对话框、悬浮卡以及提示框。
```
/* App.vue */
<template>
    <div>123</div>
    <Teleport to="#container">
        Teleport
    </Teleport>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
    setup() {}
});
</script>

/* index.html */
<div id="app"></div>
<div id="container"></div>
```

Suspense
同样的，这和React中的Supense是一样的。
```
Suspense 让你的组件在渲染之前进行“等待”，
并在等待时显示 fallback 的内容
```

```
// App.vue
<template>
    <Suspense>
        <template #default>
            <AsyncComponent />
        </template>
        <template #fallback>
            Loading...
        </template>
    </Suspense>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import AsyncComponent from './AsyncComponent.vue';

export default defineComponent({
    name: "App",
    
    components: {
        AsyncComponent
    }
});
</script>

// AsyncComponent.vue
<template>
    <div>Async Component</div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

const sleep = () => {
    return new Promise(resolve => setTimeout(resolve, 1000));
};

export default defineComponent({
    async setup() {
        await sleep();
    }
});
</script>
```

8. Better TypeScript support
```
在vue2中使用过TypesScript的童鞋应该有过体会，写起来实在是有点难受。
vue3则是使用ts进行了重写，开发者使用vue3时拥有更好的类型支持和更好的编写体验。
```
  
  #### VDOM：三个part
- 虚拟节点类，将真实 DOM节点用 js 对象的形式进行展示，
并提供 render 方法，将虚拟节点渲染成真实 DOM
- 节点 diff 比较：对虚拟节点进行 js 层面的计算，
并将不同的操作都记录到 patch 对象
- re-render：解析 patch 对象，进行 re-render

补充1：VDOM 的必要性？
- 创建真实DOM的代价高：真实的 DOM 节点 node 实现的属性很多，而 vnode 
仅仅实现一些必要的属性，相比起来，创建一个 vnode 的成本比较低。
- 触发多次浏览器重绘及回流：使用 vnode ，相当于加了一个缓冲，
让一次数据变动所带来的所有 node 变化，先在 vnode 中进行修改，
然后 diff 之后对所有产生差异的节点集中一次对 DOM tree 进行修改，
以减少浏览器的重绘及回流。

补充2：vue 为什么采用 vdom？
```
引入 Virtual DOM 在性能方面的考量仅仅是一方面。
```

- 性能受场景的影响是非常大的，不同的场景可能造成不同实现方案之间成倍的性能差距，所以依赖细粒度绑定及 Virtual DOM 哪个的性能更好还真不是一个容易下定论的问题。
- Vue 之所以引入了 Virtual DOM，更重要的原因是为了解耦 HTML依赖，这带来两个非常重要的好处是：
```
不再依赖 HTML 解析器进行模版解析，可以进行更多的 AOT 工作提高
运行时效率：通过模版 AOT 编译，Vue 的运行时体积可以进一步压缩，
运行时效率可以进一步提升；
可以渲染到 DOM 以外的平台，实现 SSR、同构渲染这些高级特性，
Weex等框架应用的就是这一特性。

综上，Virtual DOM 在性能上的收益并不是最主要的，
更重要的是它使得 Vue 具备了现代框架应有的高级特性。
 ``` 
  
  #### 为什么使用虚拟DOM(Virtual DOM)
- 手动操作 DOM 比较麻烦，还需要考虑浏览器兼容性问题，虽然有 
jQuery 等库简化 DOM 操作，但是随着项目的复杂 DOM 操作复杂提升
- 为了简化 DOM 的复杂操作于是出现了各种 MVVM 框架，MVVM 框架解决了视图和状态的同步问题
- 为了简化视图的操作我们可以使用模板引擎，但是模板引擎没有解决跟踪状态变化的问题，于是Virtual DOM 出现了
- Virtual DOM 的好处是当状态改变时不需要立即更新 DOM，只需要创建一个虚拟树来描述DOM，Virtual DOM 内部将弄清楚如何有效(diff)的更新 DOM
- 虚拟 DOM 可以维护程序的状态，跟踪上一次的状态
- 通过比较前后两次状态的差异更新真实 DOM

虚拟 DOM 的作用
- 维护视图和状态的关系
- 复杂视图情况下提升渲染性能
- 除了渲染 DOM 以外，还可以实现 SSR(Nuxt.js/Next.js)、原生应用(Weex/React Native)、小程序(mpvue/uni-app)等
img

  #### Compositon api
Composition API也叫组合式API，是Vue3.x的新特性。
```
通过创建 Vue 组件，我们可以将接口的可重复部分及其功能提取到
可重用的代码段中。仅此一项就可以使我们的应用程序在可维护性和
灵活性方面走得更远。然而，我们的经验已经证明，光靠这一点可能
是不够的，尤其是当你的应用程序变得非常大的时候——想想几百个组件。
在处理如此大的应用程序时，共享和重用代码变得尤为重要
```

通俗的讲：
```
没有Composition API之前vue相关业务的代码需要配置到option的
特定的区域，中小型项目是没有问题的，但是在大型项目中会导致后期的
维护性比较复杂，同时代码可复用性不高。Vue3.x中的
composition-api就是为了解决这个问题而生的
```

compositon api提供了以下几个函数：
- setup
- ref
- reactive
- watchEffect
- watch
- computed
- toRefs
- 生命周期的hooks

  #### Vue diff算法详解
- updateChildren
- 
> 这个函数是用来比较两个结点的子节点

```js
updateChildren(parentElm, oldCh, newCh) {
    let oldStartIdx = 0,
        newStartIdx = 0
    let oldEndIdx = oldCh.length - 1
    let oldStartVnode = oldCh[0]
    let oldEndVnode = oldCh[oldEndIdx]
    let newEndIdx = newCh.length - 1
    let newStartVnode = newCh[0]
    let newEndVnode = newCh[newEndIdx]
    let oldKeyToIdx
    let idxInOld
    let elmToMove
    let before
    while (oldStartIdx <= oldEndIdx && newStartIdx <= newEndIdx) { // 只有 oldS>oldE 或者 newS>newE 才会终止循环
        if (oldStartVnode == null) { // 对于vnode.key的比较，会把oldVnode = null
            oldStartVnode = oldCh[++oldStartIdx]
        } else if (oldEndVnode == null) {
            oldEndVnode = oldCh[--oldEndIdx]
        } else if (newStartVnode == null) {
            newStartVnode = newCh[++newStartIdx]
        } else if (newEndVnode == null) { // 到这里是找到第一个不为null的oldStartVnode oldEndVnode newStartVnode newEndVnode
            newEndVnode = newCh[--newEndIdx]
        } else if (sameVnode(oldStartVnode, newStartVnode)) { // oldS指针和newS指针对应的结点相同时，将oldS和newS指针同时向后移一位
            patchVnode(oldStartVnode, newStartVnode)
            oldStartVnode = oldCh[++oldStartIdx]
            newStartVnode = newCh[++newStartIdx]
        } else if (sameVnode(oldEndVnode, newEndVnode)) { // oldE指针和newE指针对应的结点相同时，将oldE和newE指针同时向前移一位
            patchVnode(oldEndVnode, newEndVnode)
            oldEndVnode = oldCh[--oldEndIdx]
            newEndVnode = newCh[--newEndIdx]
        } else if (sameVnode(oldStartVnode, newEndVnode)) { // oldS指针和newE指针对应的结点相同时，将oldS指针对应结点移动到oldE指针之后，同时将oldS指针向后移动一位，newE指针向前移动一位
            patchVnode(oldStartVnode, newEndVnode)
            api.insertBefore(parentElm, oldStartVnode.el, api.nextSibling(oldEndVnode.el))
            oldStartVnode = oldCh[++oldStartIdx]
            newEndVnode = newCh[--newEndIdx]
        } else if (sameVnode(oldEndVnode, newStartVnode)) { // oldE指针和newS指针对应的结点相同时，将oldE指针对应的结点移动到oldS指针之前，同时将oldE指针向前移动一位，newS指针想后移动一位
            patchVnode(oldEndVnode, newStartVnode)
            api.insertBefore(parentElm, oldEndVnode.el, oldStartVnode.el)
            oldEndVnode = oldCh[--oldEndIdx]
            newStartVnode = newCh[++newStartIdx]
        } else { // 使用key时的比较
            if (oldKeyToIdx === undefined) {
                oldKeyToIdx = createKeyToOldIdx(oldCh, oldStartIdx, oldEndIdx) // 有key生成index表
            }
            idxInOld = oldKeyToIdx[newStartVnode.key]
            if (!idxInOld) {
                api.insertBefore(parentElm, createEle(newStartVnode).el, oldStartVnode.el)
                newStartVnode = newCh[++newStartIdx]
            } else {
                elmToMove = oldCh[idxInOld]
                if (elmToMove.sel !== newStartVnode.sel) {
                    api.insertBefore(parentElm, createEle(newStartVnode).el, oldStartVnode.el)
                } else {
                    patchVnode(elmToMove, newStartVnode)
                    oldCh[idxInOld] = null
                    api.insertBefore(parentElm, elmToMove.el, oldStartVnode.el)
                }
                newStartVnode = newCh[++newStartIdx]
            }
        }
    }
    if (oldStartIdx > oldEndIdx) { // oldVnode遍历结束了，那就将newVnode里newS指针和newE指针之间的结点添加到oldVnode里
        before = newCh[newEndIdx + 1] == null ? null : newCh[newEndIdx + 1].el
        addVnodes(parentElm, before, newCh, newStartIdx, newEndIdx)
    } else if (newStartIdx > newEndIdx) { // newVnode遍历结束了，那就将oldVnonde里oldS指针和oldE指针之间的结点删除
        removeVnodes(parentElm, oldCh, oldStartIdx, oldEndIdx)
    }
}
```

  #### 移动端适配的方法
```
起因:手机设备屏幕尺寸不一，做移动端的Web页面，需要考虑安卓/IOS的
各种尺寸设备上的兼容，针对移动端设备的页面，设计与前端实现怎样做
能更好地适配不同屏幕宽度的移动设备；
```

- 1. flex 弹性布局
- 2. viewport 适配

    ```html
    <meta name="viewport" content="width=750,initial-scale=0.5">
    ```

    initial-scale = 屏幕的宽度 / 设计稿的宽度

- 3. rem 弹性布局
- 4. rem + viewport 缩放

```
这也是淘宝使用的方案，根据屏幕宽度设定 rem 值，需要适配的元素都
使用 rem 为单位，不需要适配的元素还是使用 px 为单位。（1em = 16px）
```

  #### rem原理
```
rem 布局的本质是等比缩放

rem 是（根）字体大小相对单位，也就是说跟当前元素的 
font-size 没有关系，而是跟整个 body 的 font-size 有关系。
```

  #### rem和em的区别
> 一句话概括：em相对于父元素，rem相对于根元素。

- em
  ```css
  子元素字体大小的 em 是相对于父元素字体大小
  元素的width/height/padding/margin用em的话是
  相对于该元素的font-size
  ```

- rem
  ```js
  rem 是全部的长度都相对于根元素，根元素是谁？<html>元素。
  通常做法是给html元素设置一个字体大小，
  然后其他元素的长度单位就为rem。
  ```

  #### 移动端300ms延迟的原因以及解决方案
```
移动端点击有 300ms 的延迟是因为移动端会有双击缩放的这个操作，
因此浏览器在 click 之后要等待 300ms，看用户有没有下一次点击，
来判断这次操作是不是双击。
```

有三种办法来解决这个问题：
- 1. 通过 meta 标签禁用网页的缩放。

    ```html
    <meta name="viewport" content="user-scalable=no">
    ```

- 2. 更改默认的视口宽度
    ```html
    <meta name="viewport" content="width=device-width">
    ```

- 3. 调用一些 js 库，比如 FastClick
```
   FastClick 是 FT Labs 专门为解决移动端浏览器 300 毫秒
   点击延迟问题所开发的一个轻量级的库。FastClick 的实现原理是
   在检测到 touchend 事件的时候，会通过 DOM 自定义事件
   立即出发模拟一个 click 事件，
   并把浏览器在 300ms 之后的click 事件阻止掉。
```

  #### vue和react技术选型
相同点：
- 数据驱动页面，提供响应式的试图组件
- 都有virtual DOM,组件化的开发，通过props参数进行父子之间组件传递数据，都实现了webComponents规范
- 数据流动单向，都支持服务器的渲染SSR
- 都有支持native的方法，react有React native， vue有wexx

不同点：
- 数据绑定：Vue实现了双向的数据绑定，react数据流动是单向的
- 数据渲染：大规模的数据渲染，react更快
- 使用场景：React配合Redux架构适合大规模多人协作复杂项目，Vue适合小快的项目

```
vue是采用webpack +vue-loader单文件组件格式，html, js, css同一个文件
```

  #### Vue和React数据驱动的区别
```
在数据绑定上来说，vue的特色是双向数据绑定，
而在react中是单向数据绑定。

vue中实现数据绑定靠的是
数据劫持（Object.defineProperty()）+发布-订阅模式
```

vue中实现双向绑定
```html
<input v-model="msg" />
```

react中实现双向绑定
```html
<input value={this.state.msg} onChange={() => this.handleInputChange()} />
```


### React

  #### React生命周期
react旧版生命周期包含三个过程：
- 1、挂载过程
constructor()
componentWillMount()
componentDidMount()

- 2、更新过程
componentWillReceiveProps(nextProps)
shouldComponentUpdate(nextProps,nextState)
componentWillUpdate (nextProps,nextState)
render()
componentDidUpdate(prevProps,prevState)

- 3、卸载过程
componentWillUnmount()

其具体作用分别为：
- 1、constructor()
完成了React数据的初始化。

- 2、componentWillMount()
组件已经完成初始化数据，但是还未渲染DOM时执行的逻辑，主要用于服务端渲染。

- 3、componentDidMount()
组件第一次渲染完成时执行的逻辑，此时DOM节点已经生成了。

- 4、componentWillReceiveProps(nextProps)
接收父组件新的props时，重新渲染组件执行的逻辑。

- 5、shouldComponentUpdate(nextProps, nextState)
在setState以后，state发生变化，组件会进入重新渲染的流程时执行的逻辑。在这个生命周期中return false可以阻止组件的更新，主要用于性能优化。

- 6、componentWillUpdate(nextProps, nextState)
shouldComponentUpdate返回true以后，组件进入重新渲染的流程时执行的逻辑。

- 7、render()
页面渲染执行的逻辑，render函数把jsx编译为函数并生成虚拟dom，然后通过其diff算法比较更新前后的新旧DOM树，并渲染更改后的节点。

- 8、componentDidUpdate(prevProps, prevState)
重新渲染后执行的逻辑。

- 9、componentWillUnmount()
组件的卸载前执行的逻辑，比如进行“清除组件中所有的setTimeout、setInterval等计时器”或“移除所有组件中的监听器removeEventListener”等操作。

react新版生命周期：
```
react16.4后使用了新的生命周期，使用getDerivedStateFromProps
代替了旧的componentWillReceiveProps及componentWillMount。
使用getSnapshotBeforeUpdate代替了旧的componentWillUpdate。
```

使用getDerivedStateFromProps(nextProps, prevState)的原因：
```
旧的React中componentWillReceiveProps方法是用来判断前后两个 props 
是否相同，如果不同，则将新的 props 更新到相应的 state 上去。
在这个过程中我们实际上是可以访问到当前props的，这样我们可能会对
this.props做一些奇奇怪怪的操作，很可能会破坏 state 数据的
单一数据源，导致组件状态变得不可预测。

而在 getDerivedStateFromProps 中禁止了组件去访问 this.props，
强制让开发者去比较 nextProps 与 prevState 中的值，以确保当
开发者用到 getDerivedStateFromProps 这个生命周期函数时，
就是在根据当前的 props 来更新组件的 state，而不是去访问
this.props并做其他一些让组件自身状态变得更加不可预测的事情。
```

使用getSnapshotBeforeUpdate(prevProps, prevState)的原因：
```
在 React 开启异步渲染模式后，在执行函数时读到的 DOM 元素状态
并不总是渲染时相同，这就导致在 componentDidUpdate 中使用 
componentWillUpdate 中读取到的 DOM 元素状态是不安全的，
因为这时的值很有可能已经失效了。

而getSnapshotBeforeUpdate 会在最终的 render 之前被调用，
也就是说在 getSnapshotBeforeUpdate 中读取到的 DOM 元素
状态是可以保证与componentDidUpdate 中一致的。
```

  #### 组件之间通信
- 父子组件通信
- 自定义事件
- redux和context

context如何运用
- 父组件向其下所有子孙组件传递信息
- 如一些简单的信息：主题、语言
- 复杂的公共信息用redux

  #### 组件的渲染顺序
假如有A,B,C,D组件，层级结构为：
```
   顶层       A
   子组件     B
   子组件   C   D
```

我们知道组件的生命周期为：
挂载阶段：
- constructor()
- componentWillMount()
- render()
- componentDidMount()

更新阶段为：
- componentWillReceiveProps()
- shouldComponentUpdate()
- componentWillUpdate()
- render()
- componentDidUpdate

那么在挂载阶段，A,B,C,D的生命周期渲染顺序是如何的呢？
```
以render()函数为分界线。从顶层组件开始，一直往下，
直至最底层子组件。然后再往上
```

组件update阶段同理
前面是react16以前的组建渲染方式。这就存在一个问题
```
如果这是一个很大，层级很深的组件，react渲染它需要几十甚至几百毫秒，在这期间，react会一直占用浏览器主线程，任何其他的操作（包括用户的点击，鼠标移动等操作）都无法执行
```

Fiber架构就是为了解决这个问题
```
fiber架构 组建的渲染顺序

加入fiber的react将组件更新分为两个时期
```

这两个时期以render为分界
- render前的生命周期为phase1,
- render后的生命周期为phase2
```
phase1的生命周期是可以被打断的，每隔一段时间它会跳出当前渲染进程，
去确定是否有其他更重要的任务。此过程，React在 workingProgressTree 
（并不是真实的virtualDomTree）上复用 current 上的 Fiber 数据结构
来一步地（通过requestIdleCallback）来构建新的 tree，
标记处需要更新的节点，放入队列中

phase2的生命周期是不可被打断的，React 将其所有的变更一次性
更新到DOM上
```

这里最重要的是phase1这是时期所做的事。
因此我们需要具体了解phase1的机制
- 如果不被打断，那么phase1执行完会直接进入render函数，构建真实的virtualDomTree
- 如果组件再phase1过程中被打断，即当前组件只渲染到一半（也许是在willMount,也许是willUpdate~反正是在render之前的生命周期），那么react会怎么干呢？ react会放弃当前组件所有干到一半的事情，去做更高优先级更重要的任务（当然，也可能是用户鼠标移动，或者其他react监听之外的任务），当所有高优先级任务执行完之后，react通过callback回到之前渲染到一半的组件，从头开始渲染。（看起来放弃已经渲染完的生命周期，会有点不合理，反而会增加渲染时长，但是react确实是这么干的）

所有phase1的生命周期函数都可能被执行多次，因为可能会被打断重来
```
这样的话，就和react16版本之前有很大区别了，因为可能会被执行多次，
那么我们最好就得保证phase1的生命周期每一次执行的结果都是一样的，
否则就会有问题，因此，最好都是纯函数
```
- 如果高优先级的任务一直存在，那么低优先级的任务则永远无法进行，组件永远无法继续渲染。这个问题facebook目前好像还没解决
- 所以，facebook在react16增加fiber结构，其实并不是为了减少组件的渲染时间，事实上也并不会减少，最重要的是现在可以使得一些更高优先级的任务，如用户的操作能够优先执行，提高用户的体验，至少用户不会感觉到卡顿

  #### React组件和渲染更新过程
渲染和更新过程
- jsx如何渲染为页面
- setState之后如何更新页面
- 面试考察全流程

JSX本质和vdom
- JSX即createElement函数
- 执行生成vnode
- patch(elem,vnode)和patch(vnode,newNode)

组件渲染过程
- props state
- render()生成vnode
- patch(elem, vnode)

组件更新过程
- setState-->dirtyComponents(可能有子组件)
- render生成newVnode
- patch(vnode, newVnode)

  #### React都做过哪些优化
- React渲染页面的两个阶段
  - 调度阶段（reconciliation）：在这个阶段 React 会更新数据生成新的 Virtual DOM，然后通过Diff算法，快速找出需要更新的元素，放到更新队列中去，得到新的更新队列。
  - 渲染阶段（commit）：这个阶段 React 会遍历更新队列，将其所有的变更一次性更新到DOM上

- React 15 架构
  - React15架构可以分为两层
    - Reconciler（协调器）—— 负责找出变化的组件；
    - Renderer（渲染器）—— 负责将变化的组件渲染到页面上；

```
  在React15及以前，Reconciler采用递归的方式创建虚拟DOM，
递归过程是不能中断的。如果组件树的层级很深，递归会占用线程
很多时间，递归更新时间超过了16ms，用户交互就会卡顿。

  为了解决这个问题，React16将递归的无法中断的更新重构为异步的
可中断更新，由于曾经用于递归的虚拟DOM数据结构已经无法满足需要。
于是，全新的Fiber架构应运而生。
```

- React 16 架构
  - 为了解决同步更新长时间占用线程导致页面卡顿的问题，也为了探索运行时优化的更多可能，React开始重构并一直持续至今。重构的目标是实现Concurrent Mode（并发模式）。
  - 从v15到v16，React团队花了两年时间将源码架构中的Stack Reconciler重构为Fiber Reconciler
  - React16架构可以分为三层：
    - Scheduler（调度器）—— 调度任务的优先级，高优任务优先进入Reconciler；
    - Reconciler（协调器）—— 负责找出变化的组件：更新工作从递归变成了可以中断的循环过程。Reconciler内部采用了Fiber的架构；
    - Renderer（渲染器）—— 负责将变化的组件渲染到页面上。

- React 17 优化
  - 使用Lane来管理任务的优先级。Lane用二进制位表示任务的优先级，方便优先级的计算（位运算），不同优先级占用不同位置的“赛道”，而且存在批的概念，优先级越低，“赛道”越多。高优先级打断低优先级，新建的任务需要赋予什么优先级等问题都是Lane所要解决的问题。
  - Concurrent Mode的目的是实现一套可中断/恢复的更新机制。其由两部分组成：
    - 一套协程架构：Fiber Reconciler
    - 基于协程架构的启发式更新算法：控制协程架构工作方式的算法

  #### React有哪些优化性能的手段
类组件中的优化手段
- 使用纯组件 PureComponent 作为基类。
- 使用 React.memo 高阶函数包装组件。
- 使用 shouldComponentUpdate 生命周期函数来自定义渲染逻辑。

方法组件中的优化手段
- 使用 useMemo。
- 使用 useCallBack。

其他方式
- 在列表需要频繁变动时，使用唯一 id 作为 key，而不是数组下标。
- 必要时通过改变 CSS 样式隐藏显示组件，而不是通过条件判断显示隐藏组件。
- 使用 Suspense 和 lazy 进行懒加载，例如：
```
import React, { lazy, Suspense } from "react";

export default class CallingLazyComponents extends React.Component {
  render() {
    var ComponentToLazyLoad = null;

    if (this.props.name == "Mayank") {
      ComponentToLazyLoad = lazy(() => import("./mayankComponent"));
    } else if (this.props.name == "Anshul") {
      ComponentToLazyLoad = lazy(() => import("./anshulComponent"));
    }

    return (
      <div>
        <h1>This is the Base User: {this.state.name}</h1>
        <Suspense fallback={<div>Loading...</div>}>
          <ComponentToLazyLoad />
        </Suspense>
      </div>
    )
  }
}
```

  #### diff算法是怎么运作
```
每一种节点类型有自己的属性，也就是prop，每次进行diff的时候，
react会先比较该节点类型，假如节点类型不一样，那么react会直接
删除该节点，然后直接创建新的节点插入到其中，假如节点类型一样，
那么会比较prop是否有更新，假如有prop不一样，那么react会判定
该节点有更新，那么重渲染该节点，然后在对其子节点进行比较，
一层一层往下，直到没有子节点
```

- 把树形结构按照层级分解，只比较同级元素。
- 给列表结构的每个单元添加唯一的key属性，方便比较。
- React 只会匹配相同 class 的 component（这里面的class指的是组件的名字）
- 合并操作，调用 component 的 setState 方法的时候, React 将其标记为 - dirty.到每一个事件循环结束, React 检查所有标记 dirty的 component重新绘制.
- 选择性子树渲染。开发人员可以重写shouldComponentUpdate提高diff的性能

优化
```
为了降低算法复杂度，React的diff会预设三个限制：
```
- 只对同级元素进行Diff。如果一个DOM节点在前后两次更新中跨越了层级，那么React不会尝试复用他。
- 两个不同类型的元素会产生出不同的树。如果元素由div变为p，React会销毁div及其子孙节点，并新建p及其子孙节点。
- 开发者可以通过 key prop来暗示哪些子元素在不同的渲染下能保持稳定。考虑如下例子：

Diff的思路
该如何设计算法呢？如果让我设计一个Diff算法，我首先想到的方案是：
```
判断当前节点的更新属于哪种情况
如果是新增，执行新增逻辑
如果是删除，执行删除逻辑
如果是更新，执行更新逻辑
```
- 按这个方案，其实有个隐含的前提——不同操作的优先级是相同的
- 但是React团队发现，在日常开发中，相较于新增和删除，更新组件发生的频率更高。所以Diff会优先判断当前节点是否属于更新。

基于以上原因，Diff算法的整体逻辑会经历两轮遍历：
- 第一轮遍历：处理更新的节点。
- 第二轮遍历：处理剩下的不属于更新的节点。


diff算法的作用
```
计算出Virtual DOM中真正变化的部分，并只针对该部分进行原生DOM操作，
而非重新渲染整个页面。
```

传统diff算法
```
通过循环递归对节点进行依次对比，算法复杂度达到 O(n^3) ，n是树
的节点数，这个有多可怕呢？——如果要展示1000个节点，得执行上亿次比较。
即便是CPU快能执行30亿条命令，也很难在一秒内计算出差异。
```

React的diff算法
```
什么是调和？
将Virtual DOM树转换成actual DOM树的最少操作的过程 称为 调和 。

什么是React diff算法？
diff算法是调和的具体实现。
```

diff策略
```
React用 三大策略 将O(n^3)复杂度 转化为 O(n)复杂度
```

策略一（tree diff）：
- Web UI中DOM节点跨层级的移动操作特别少，可以忽略不计。

策略二（component diff）：
- 拥有相同类的两个组件 生成相似的树形结构，
- 拥有不同类的两个组件 生成不同的树形结构。

策略三（element diff）：
对于同一层级的一组子节点，通过唯一id区分。
tree diff
- React通过updateDepth对Virtual DOM树进行层级控制。
- 对树分层比较，两棵树 只对同一层次节点 进行比较。如果该节点不存在时，则该节点及其子节点会被完全删除，不会再进一步比较。
- 只需遍历一次，就能完成整棵DOM树的比较。

那么问题来了，如果DOM节点出现了跨层级操作,diff会咋办呢？
```
答：diff只简单考虑同层级的节点位置变换，如果是跨层级的话，
只有创建节点和删除节点的操作。

以A为根节点的整棵树会被重新创建，而不是移动，因此官方建议
不要进行DOM节点跨层级操作，可以通过CSS隐藏、显示节点，
而不是真正地移除、添加DOM节点
```

component diff
```
React对不同的组件间的比较，有三种策略
```

- 同一类型的两个组件，按原策略（层级比较）继续比较Virtual DOM树即可。
- 同一类型的两个组件，组件A变化为组件B时，可能Virtual DOM没有任何变化，如果知道这点（变换的过程中，Virtual DOM没有改变），可节省大量计算时间，所以 用户 可以通过 shouldComponentUpdate() 来判断是否需要 判断计算。
- 不同类型的组件，将一个（将被改变的）组件判断为dirty component（脏组件），从而替换 整个组件的所有节点。

```
注意：如果组件D和组件G的结构相似，但是 React判断是 不同类型的组件，则不会比较其结构，而是删除 组件D及其子节点，创建组件G及其子节点。
```

element diff
```
当节点处于同一层级时，diff提供三种节点操作：删除、插入、移动。
```
- 插入：组件 C 不在集合（A,B）中，需要插入
- 删除：
  - 组件 D 在集合（A,B,D）中，但 D的节点已经更改，不能复用和更新，所以需要删除 旧的 D ，再创建新的。
  - 组件 D 之前在 集合（A,B,D）中，但集合变成新的集合（A,B）了，D 就需要被删除。
- 移动：组件D已经在集合（A,B,C,D）里了，且集合更新时，D没有发生更新，只是位置改变，如新集合（A,D,B,C），D在第二个，无须像传统diff，让旧集合的第二个B和新集合的第二个D 比较，并且删除第二个位置的B，再在第二个位置插入D，而是 （对同一层级的同组子节点） 添加唯一key进行区分，移动即可。

总结
- tree diff：只对比同一层的 dom 节点，忽略 dom 节点的跨层级移动
```
react 只会对相同颜色方框内的 DOM 节点进行比较，即同一个父节点下
的所有子节点。当发现节点不存在时，则该节点及其子节点会被完全删除掉，
不会用于进一步的比较。

这样只需要对树进行一次遍历，便能完成整个 DOM 树的比较。

这就意味着，如果 dom 节点发生了跨层级移动，react 会删除旧的节点，
生成新的节点，而不会复用。
```

- component diff：如果不是同一类型的组件，会删除旧的组件，创建新的组件

- element diff：对于同一层级的一组子节点，需要通过唯一 id 进行来区分
```
  如果没有 id 来进行区分，一旦有插入动作，
会导致插入位置之后的列表全部重新渲染

  这也是为什么渲染列表时为什么要使用唯一的 key。
```

diff的不足与待优化的地方
```
尽量减少类似将最后一个节点移动到列表首部的操作，
当节点数量过大或更新操作过于频繁时，会影响React的渲染性能
```

  #### React router
react-router如何配置懒加载
```
import { BrowserRouter as Router, Route, Switch } from ' react- router-dom' ;
import React, { Suspense, lazy } from 'react' ;
const Home = lazy(() => import(' ./ routes/Home'));
const About = lazy(() => import('./ routes/About'));
constApp=()=>(
<Router>
<Suspense fallback= {<div>Loading... </div>}>
<Switch>
<Route exact path="/" component= {Home}/>
Route path=" / about" component= {About}/>
</ Switch>
</ Suspense>
</Route r>
);
```




- [jQuery](#jQuery)
  - [](#)  2 jQuery 的实现原理
  - [](#)  12 针对 jQuery 的优化方法
  - [](#)  17 jQuery对象的特点
  - [](#)  1 你觉得jQuery或zepto源码有哪些写的好的地方
  - [](#)  11 jQuery 一个对象可以同时绑定多个事件，这是如何实现的
  - [](#)  5 jQuery 的属性拷贝(extend)的实现原理是什么，如何实现深拷贝
  - [](#)  6 jQuery 的队列是如何实现的
  - [](#)  10 jQuery 中如何将数组转化为 JSON 字符串，然后再转化回来
  - [](#)  9 jQuery 通过哪个方法和 Sizzle 选择器结合的
  - [](#)  3 jQuery.fn 的 init 方法返回的 this 指的是什么对象
  - [](#)  4 jQuery.extend 与 jQuery.fn.extend 的区别
  - [](#)  7 jQuery 中的 bind(), live(), delegate(), on()的区别
  - [](#)  8 是否知道自定义事件
  - [](#)  14 jQuery UI 如何自定义组件
  - [](#)  15 jQuery 与 jQuery UI、jQuery Mobile 区别
  - [](#)  13 jQuery 的 slideUp 动画，当鼠标快速连续触发, 动画会滞后反复执行，该如何处理呢
  - [](#)  16 jQuery 和 Zepto 的区别？ 各自的使用场景


- [微信小程序](#微信小程序)
  - [](#)  5 微信小程序与vue区别
  - [](#)  1 微信小程序有几个文件
  - [](#)  2 微信小程序怎样跟事件传值
  - [](#)  3 小程序的 wxss 和 css 有哪些不一样的地方？
  - [](#)  4 小程序关联微信公众号如何确定用户的唯一性


- [webpack相关](#webpack相关)
  - [](#)  1 打包体积 优化思路
  - [](#)  2 打包效率
  - [](#)  3 Loader
  - [](#)  4 说一下webpack的一些plugin，怎么使用webpack对项目进行优化


- [Bootstrap](#Bootstrap)
  - [](#)  1 什么是Bootstrap？以及为什么要使用Bootstrap？
  - [](#)  2 使用Bootstrap时，要声明的文档类型是什么？以及为什么要这样声明？
  - [](#)  3 什么是Bootstrap网格系统
  - [](#)  4 Bootstrap 网格系统（Grid System）的工作原理
  - [](#)  5 对于各类尺寸的设备，Bootstrap设置的class前缀分别是什么
  - [](#)  6 Bootstrap 网格系统列与列之间的间隙宽度是多少
  - [](#)  7 如果需要在一个标题的旁边创建副标题，可以怎样操作
  - [](#)  8 用Bootstrap，如何设置文字的对齐方式？
  - [](#)  9 Bootstrap如何设置响应式表格？
  - [](#)  10 使用Bootstrap创建垂直表单的基本步骤？
  - [](#)  11 使用Bootstrap创建水平表单的基本步骤？
  - [](#)  12 使用Bootstrap如何创建表单控件的帮助文本？
  - [](#)  13 使用Bootstrap激活或禁用按钮要如何操作？
  - [](#)  14 Bootstrap有哪些关于的class？
  - [](#)  15 Bootstrap中有关元素浮动及清除浮动的class？
  - [](#)  16 除了屏幕阅读器外，其他设备上隐藏元素的class？
  - [](#)  17 Bootstrap如何制作下拉菜单？
  - [](#)  18 Bootstrap如何制作按钮组？以及水平按钮组和垂直按钮组的优先级？
  - [](#)  19 Bootstrap如何设置按钮的下拉菜单？
  - [](#)  20 Bootstrap中的输入框组如何制作？
  - [](#)  21 Bootstrap中的导航都有哪些？
  - [](#)  22 Bootstrap中设置分页的class？
  - [](#)  23 Bootstrap中显示标签的class？
  - [](#)  24 Bootstrap中如何制作徽章？
  - [](#)  25 Bootstrap中超大屏幕的作用是什么？


















