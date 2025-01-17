## JavaScript 面试知识点总结
整理了 JavaScript 面试的部分知识点

### 目录

- [js数据类型](#js数据类型)
  - [js有几种类型的值](#js有几种类型的值)
  - [堆和栈](#堆和栈)
  - [undefined与undeclared区别](#undefined与undeclared区别)
  - [null和undefined区别](#null和undefined区别)
  - [null是对象吗？为什么](#null是对象吗为什么)
  - [如何获取安全的undefined值](#如何获取安全的undefined值)
  - [Symbol类型的注意点](#Symbol类型的注意点)
  - [js中整数的安全范围是多少](#js中整数的安全范围是多少)
  - [JS整数是怎么表示的](#JS整数是怎么表示的)
  - [Number()的存储空间是多大？如果后台发送了一个超过最大自己的数字怎么办](#Number的存储空间是多大如果后台发送了一个超过最大自己的数字怎么办)
  - ['1'.toString()为什么可以调用](#1toString为什么可以调用)
  - [如何理解BigInt](#如何理解BigInt)

- [js类型判断](#js类型判断)
  - [typeof操作符](#typeof操作符)
    - [typeof NaN的结果是什么](#typeof-NaN的结果是什么)
  - [instanceof](#instanceof)
  - [typeof和instanceof区别](#typeof和instanceof区别)
  - [constructor](#constructor)
  - [Object.prototype.toString.call()](#ObjectprototypetoStringcall)
  - [判断是否是promise对象](#判断是否是promise对象)
  - [封装javascript的类型判断函数](#封装javascript的类型判断函数)
  - [Object.is和===的区别](#Objectis和的区别)

- [js类型转换](#js类型转换)
  - [转化规则](#转化规则)
  - [转Boolean](#转Boolean)
  - [对象转原始类型是根据什么流程运行的](#对象转原始类型是根据什么流程运行的)
  - [如何让if(a == 1 && a == 2)条件成立](#如何让ifa--1--a--2条件成立)
  - [四则运算符](#四则运算符)
  - [比较运算符](#比较运算符)
  - [其他值到字符串的转换规则](#其他值到字符串的转换规则)
  - [其他值到数字值的转换规则](#其他值到数字值的转换规则)
  - [其他值到布尔类型的值的转换规则](#其他值到布尔类型的值的转换规则)
  - [如何将字符串转化为数字，例如'12.3b'](#如何将字符串转化为数字例如123b)
  - [什么情况下会发生布尔值的隐式强制类型转换](#什么情况下会发生布尔值的隐式强制类型转换)
  - [Symbol值的强制类型转换](#Symbol值的强制类型转换)
  - [将浮点数点左边的数每三位添加一个逗号,12000000.11转化为『12,000,000.11』](#将浮点数点左边的数每三位添加一个逗号1200000011转化为1200000011)
  - [解析字符串中的数字和将字符串强制类型转换为数字的返回结果都是数字,区别](#解析字符串中的数字和将字符串强制类型转换为数字的返回结果都是数字区别)
  - [[] == ![]结果是什么？为什么](#--结果是什么为什么)
  - [==和===有什么区别](#和有什么区别)

- [js属性](#js属性)
  - [内部属性[[Class]]是什么](#内部属性Class是什么)
  - [属性的遍历](#属性的遍历)

- [js操作符](#js操作符)
  - [||和&&操作符的返回值](#和操作符的返回值)
  - [==操作符的强制类型转换规则](#操作符的强制类型转换规则)
  - [操作符什么时候用于字符串的拼接](#操作符什么时候用于字符串的拼接)
  - [~操作符的作用](#操作符的作用)

- [类和对象](#类和对象)
  - [JavaScript如何实现一个类，怎么实例化这个类](#JavaScript如何实现一个类怎么实例化这个类)
  - [ECMAScript6怎么写class，为什么会出现class这种东西](#ECMAScript6怎么写class为什么会出现class这种东西)
  - [javascript创建对象的几种方式](#javascript创建对象的几种方式)
  - [如何判断一个对象是否属于某个类](#如何判断一个对象是否属于某个类)
  - [如何判断一个对象是否为空对象](#如何判断一个对象是否为空对象)
  - [怎么判断两个对象相等](#怎么判断两个对象相等)
  - [js有哪些内置对象](#js有哪些内置对象)
  - [什么是假值对象](#什么是假值对象)
  - [Object.is()与原来的比较操作符“===”、“==”的区别](#Objectis与原来的比较操作符的区别)
  - [Object.assign()](#Objectassign)
  - [使用Object.defineProperty()来进行数据劫持有什么缺点](#使用ObjectdefineProperty来进行数据劫持有什么缺点)

- [数组和对象](#数组和对象)
  - [数组(array)](#数组array)
  - [如何实现数组的随机排序](#如何实现数组的随机排序)
  - [快速的让一个数组乱序](#快速的让一个数组乱序)
  - [数组去重方法总结](#数组去重方法总结)
  - [数组扁平化](#数组扁平化)
  - [JS中flat---数组扁平化](#JS中flat数组扁平化)
  - [判断是否是数组](#判断是否是数组)
  - [数组的fill方法](#数组的fill方法)
  - [数组和对象有哪些原生方法](#数组和对象有哪些原生方法)
  - [JS数组和对象的遍历方式，以及几种方式的比较](#JS数组和对象的遍历方式以及几种方式的比较)
  - [JavaScript类数组对象的定义](#JavaScript类数组对象的定义)
  - [Array构造函数只有一个参数值时的表现](#Array构造函数只有一个参数值时的表现)
  - [Array.splice()与Array.splice()的区别](#Arraysplice与Arraysplice的区别)
  - [[].forEach.call(\$\$("<em>"),function(a){a.style.outline="1px solid#"(~~(Math.random()</em>(1&lt;&lt;24))).toString(16)})能解释一下这段代码的意思吗](#forEachcallemfunctionaastyleoutline1px-solidMathrandomem1ltlt24toString16能解释一下这段代码的意思吗)
  - [["1","2","3"].map(parseInt)答案是多少](#123mapparseint答案是多少)
  - [map与forEach的区别](#map与forEach的区别)
  - [Map和WeakMap结构](#Map和WeakMap结构)
  - [Set和WeakSet结构](#Set和WeakSet结构)
  - [{}和[]的valueOf和toString的结果是什么](#和的valueOf和toString的结果是什么)
  - [如何转化类数组成数组](#如何转化类数组成数组)
  - [forEach中return有效果吗？如何中断forEach循环](#forEach中return有效果吗如何中断forEach循环)
  - [JS判断数组中是否包含某个值](#JS判断数组中是否包含某个值)
  - [Array(3)和Array(3,4)的区别](#Array3和Array34的区别)
  - [请创建一个长度为100，值都为1的数组](#请创建一个长度为100值都为1的数组)
  - [请创建一个长度为100，值为对应下标的数组](#请创建一个长度为100值为对应下标的数组)

- [函数](#函数)
  - [JavaScript中，调用函数有哪几种方式](#JavaScript中调用函数有哪几种方式)
  - [函数式编程](#函数式编程)
  - [箭头函数与普通函数的区别](#箭头函数与普通函数的区别)
  - [封装一个函数，参数是定时器的时间，.then执行回调函数](#封装一个函数参数是定时器的时间then执行回调函数)
  - [函数节流，应用场景和原理](#函数节流应用场景和原理)
  - [isNaN和Number.isNaN函数的区别](#isNaN和NumberisNaN函数的区别)
  - [Javascript全局函数和全局变量](#Javascript全局函数和全局变量)
  - [什么是闭包，为什么要用它](#什么是闭包为什么要用它)
  - [闭包产生的原因](#闭包产生的原因)
  - [闭包有哪些表现形式](#闭包有哪些表现形式)
  - [如何解决下面的循环输出问题](#如何解决下面的循环输出问题)
  - [使用闭包实现每隔一秒打印1,2,3,4](#使用闭包实现每隔一秒打印1234)
  - [eval是做什么的](#eval是做什么的)

- [js原型和原型链](#js原型和原型链)
  - [原型/构造函数/实例](#原型构造函数实例)
  - [原型对象和构造函数有何关系](#原型对象和构造函数有何关系)
  - [能不能描述一下原型链](#能不能描述一下原型链)
  - [js获取原型的方法](#js获取原型的方法)
  - [Javascript中，有一个函数，执行时对象查找时，永远不会去查找原型，这个函数是](#Javascript中有一个函数执行时对象查找时永远不会去查找原型这个函数是)

- [js继承](#js继承)
  - [借助call](#借助call)
  - [原型链继承](#原型链继承)
  - [将call和原型链组合](#将call和原型链组合)
  - [组合继承的优化1](#组合继承的优化1)
  - [(最推荐使用):组合继承的优化2](#最推荐使用组合继承的优化2)
  - [构造函数继承](#构造函数继承)
  - [实例继承](#实例继承)
  - [拷贝继承](#拷贝继承)
  - [组合继承](#组合继承)
  - [寄生组合继承](#寄生组合继承)
    - [寄生式组合继承的实现](#寄生式组合继承的实现)
  - [es6使用extends关键字扩展一个类并继承它的行为](#es6使用extends关键字扩展一个类并继承它的行为)
  - [ES6的extends被编译后的JavaScript代码](#ES6的extends被编译后的JavaScript代码)
  - [从设计思想上谈谈继承本身的问题](#从设计思想上谈谈继承本身的问题)
  - [继承-简版](#继承-简版)


- [this对象](#this对象)
  - [this](#this)
  - [this指向](#this指向)
  - [call、apply、bind](#callapplybind)
  - [.call()和.apply()的区别](#call和apply的区别)
  - [手写call、apply及bind函数](#手写callapply及bind函数)
  - [简单实现Function.bind函数](#简单实现Functionbind函数)
  - [new操作符具体干了什么呢？如何实现](#new操作符具体干了什么呢如何实现)
  - [Javascript的作用域链](#Javascript的作用域链)
  - [JavaScript中的作用域与变量声明提升](#JavaScript中的作用域与变量声明提升)
  - [变量提升](#变量提升)

- [事件](#事件)
  - [事件是什么？IE与火狐的事件机制有什么区别？如何阻止冒泡](#事件是什么IE与火狐的事件机制有什么区别如何阻止冒泡)
  - [事件的各个阶段](#事件的各个阶段)
  - [事件冒泡](#事件冒泡)
  - [事件“捕获”和“冒泡”执行顺序和事件的执行次数](#事件捕获和冒泡执行顺序和事件的执行次数)
  - [在一个DOM上同时绑定两个点击事件：一个用捕获，一个用冒泡。事件会执行几次，先执行冒泡还是捕获](#在一个DOM上同时绑定两个点击事件一个用捕获一个用冒泡事件会执行几次先执行冒泡还是捕获)
  - [如何派发事件(dispatchEvent)？（如何进行事件广播？）](#如何派发事件dispatchEvent如何进行事件广播)
  - [事件代理](#事件代理)
  - [三种事件模型是什么](#三种事件模型是什么)
  - [事件委托](#事件委托)
  - [js的事件循环是什么](#js的事件循环是什么)
  - [事件流](#事件流)
  - [JS事件轮询机制](#JS事件轮询机制)
  - [写一个通用的事件侦听器函数](#写一个通用的事件侦听器函数)
  - [移动端的点击事件的有延迟，时间是多久，为什么会有？怎么解决这个延时](#移动端的点击事件的有延迟时间是多久为什么会有怎么解决这个延时)

- [浏览器](#浏览器)
  - [从输入URL到看到页面发生的全过程](#从输入URL到看到页面发生的全过程)
  - [浏览器的渲染过程，DOM树和渲染树的区别](#浏览器的渲染过程DOM树和渲染树的区别)
  - [浏览器的缓存机制](#浏览器的缓存机制)
  - [Ajax解决浏览器缓存问题](#Ajax解决浏览器缓存问题)
  - [常见兼容性问题](#常见兼容性问题)
  - [请求方式](#请求方式)
    - [get和post请求在缓存方面的区别](#get和post请求在缓存方面的区别)
    - [get请求传参长度的误区](#get请求传参长度的误区)
  - [检测浏览器版本版本有哪些方式](#检测浏览器版本版本有哪些方式)
  - [把script标签放在页面的最底部的body封闭之前和封闭之后有什么区别？浏览器会如何解析它们](#把script标签放在页面的最底部的body封闭之前和封闭之后有什么区别浏览器会如何解析它们)
  - [script的位置是否会影响首屏显示时间](#script的位置是否会影响首屏显示时间)
  - [实现一个页面操作不会整页刷新的网站，并且能在浏览器前进、后退时正确响应。给出你的技术实现方案](#实现一个页面操作不会整页刷新的网站并且能在浏览器前进后退时正确响应给出你的技术实现方案)
  - [如何检测浏览器所支持的最小字体大小](#如何检测浏览器所支持的最小字体大小)
  - [开发中常用的几种Content-Type](#开发中常用的几种ContentType)
  - [如何判断当前脚本运行在浏览器还是node环境中？（阿里）](#如何判断当前脚本运行在浏览器还是node环境中阿里)
  - [V8引擎的垃圾回收机制](#V8引擎的垃圾回收机制)
  - [垃圾回收](#垃圾回收)
  - [Javascript垃圾回收方法](#Javascript垃圾回收方法)
  - [URL和URI的区别](#URL和URI的区别)
  - [在输入框中如何判断输入的是一个正确的网址](#在输入框中如何判断输入的是一个正确的网址)
  - [页面编码和被请求的资源编码如果不一致如何处理](#页面编码和被请求的资源编码如果不一致如何处理)
  - [加载](#加载)
  - [WEB应用从服务器主动推送Data到客户端有那些方式](#WEB应用从服务器主动推送Data到客户端有那些方式)

- [cookie](#cookie)
  - [如何删除一个cookie](#如何删除一个cookie)
  - [服务器代理转发时，该如何处理cookie](#服务器代理转发时该如何处理cookie)
  - [什么是Samesite Cookie属性](#什么是Samesite-Cookie属性)

- [面向对象](#面向对象)
  - [什么是面向对象编程及面向过程编程，它们的异同和优缺点](#什么是面向对象编程及面向过程编程它们的异同和优缺点)

- [同步和异步](#同步和异步)
  - [同步和异步的区别](#同步和异步的区别)
  - [异步加载JS的方式有哪些](#异步加载JS的方式有哪些)
  - [异步编程的实现方式](#异步编程的实现方式)
  - [什么是单线程，和异步的关系](#什么是单线程和异步的关系)
  - [什么是Promise对象，什么是Promises/A+规范](#什么是Promise对象什么是PromisesA规范)
  - [手写一个Promise](#手写一个Promise)
  - [js中的callback和promise区别](#js中的callback和promise区别)
  - [defer和async](#defer和async)
  - [js脚本加载问题，async、defer问题](#js脚本加载问题asyncdefer问题)
  - [async原理](#async原理)

- [模式](#模式)
  - [用过哪些设计模式](#用过哪些设计模式)
  - [单例模式模式](#单例模式模式)
  - [策略模式](#策略模式)
  - [代理模式](#代理模式)
  - [中介者模式](#中介者模式)
  - [适配器模式](#适配器模式)
  - [观察者模式和发布订阅模式有什么不同](#观察者模式和发布订阅模式有什么不同)
  - [严格模式的限制](#严格模式的限制)
  - [手写一个观察者模式](#手写一个观察者模式)
  - [说说JavaScript对象的几种创建方式](#说说JavaScript对象的几种创建方式)



- [模块化](#模块化)
  - [模块化开发怎么做](#模块化开发怎么做)
  - [js的几种模块规范](#js的几种模块规范)
  - [ES6模块与CommonJS模块、AMD、CMD的差异](#ES6模块与CommonJS模块AMDCMD的差异)
  - [JS模块加载器的轮子怎么造，也就是如何实现一个模块加载器](#JS模块加载器的轮子怎么造也就是如何实现一个模块加载器)
  - [require模块引入的查找方式](#require模块引入的查找方式)

- [DOM](#DOM)
  - [什么是DOM和BOM](#什么是DOM和BOM)
  - [介绍DOM的发展](#介绍DOM的发展)
  - [DOM操作怎样添加、移除、移动、复制、创建和查找节点](#DOM操作怎样添加移除移动复制创建和查找节点)
  - [操作DOM节点方法](#操作DOM节点方法)
  - [虚拟DOM(Virtual DOM),为什么虚拟DOM比原生DOM快](#虚拟DOMVirtual-DOM为什么虚拟DOM比原生DOM快)
  - [如何比较两个DOM树的差异](#如何比较两个DOM树的差异)
  - [介绍DOM0，DOM2，DOM3事件处理方式区别](#介绍DOM0DOM2DOM3事件处理方式区别)
  - [说说有几种类型的DOM节点](#说说有几种类型的DOM节点)

- [优化](#优化)
  - [项目做过哪些性能优化](#项目做过哪些性能优化)
  - [懒加载 预加载 懒执行](#懒加载-预加载-懒执行)
  - [如何渲染几万条数据并不卡住界面](#如何渲染几万条数据并不卡住界面)
  - [一个列表，假设有100000个数据，这个该怎么办](#一个列表假设有100000个数据这个该怎么办)

- [安全](#安全)
  - [同源](#同源)
    - [浏览器的同源政策](#浏览器的同源政策)
  - [限制](#限制)
  - [跨域](#跨域)
    - [jsonp](#jsonp)
      - [手写一个jsonp](#手写一个jsonp)
    - [postMessage](#postMessage)
    - [CORS](#CORS)
    - [WebSocket](#WebSocket)
    - [proxy代理跨域(最常见)](#proxy代理跨域最常见)
  - [鉴权](#鉴权)
    - [HTTP Basic Authentication](#HTTP-Basic-Authentication)
    - [session-cookie](#session-cookie)
    - [token验证](#token验证)
    - [OAuth](#OAuth)
  - [常见web安全及防护原理](#常见web安全及防护原理)
  - [什么是XSS攻击？如何防范XSS攻击](#什么是XSS攻击如何防范XSS攻击)
  - [什么是CSRF攻击？如何防范CSRF攻击](#什么是CSRF攻击如何防范CSRF攻击)
  - [SQL注入攻击](#SQL注入攻击)
  - [什么是CSP](#什么是CSP)
  - [什么是点击劫持？如何防范点击劫持](#什么是点击劫持如何防范点击劫持)
  - [哪些操作会造成内存泄漏](#哪些操作会造成内存泄漏)

- [Ajax和axios](#Ajax和axios)
  - [Ajax是什么?原理?如何创建一个Ajax](#Ajax是什么原理如何创建一个Ajax)
  - [Ajax总结](#Ajax总结)
  - [ajax、axios、fetch区别](#ajaxaxiosfetch区别)
  - [关于http,XMLHttpRequest,Ajax的关系](#关于httpXMLHttpRequestAjax的关系)

- [概念](#概念)
  - [写JavaScript的基本规范](#写JavaScript的基本规范)
  - [js的节流与防抖](#js的节流与防抖)
  - [js中的深浅拷贝实现](#js中的深浅拷贝实现)
  - [JS中浅拷贝的手段有哪些](#JS中浅拷贝的手段有哪些)
  - [js中的命名规则](#js中的命名规则)
  - [对原生Javascript了解程度](#对原生Javascript了解程度)
  - [渐进增强和优雅降级](#渐进增强和优雅降级)
  - [JavaScript的组成](#JavaScript的组成)
  - [如何编写高性能的JavaScript](#如何编写高性能的JavaScript)
  - [js语句末尾分号是否可以省略](#js语句末尾分号是否可以省略)
  - [js延迟加载的方式有哪些](#js延迟加载的方式有哪些)
  - [使用JS实现获取文件扩展名](#使用JS实现获取文件扩展名)
  - [对web标准、可用性、可访问性的理解](#对web标准可用性可访问性的理解)
  - [对于JSON的了解](#对于JSON的了解)
  - [XML和JSON的区别](#XML和JSON的区别)
  - [JavaScript对象生命周期的理解](#JavaScript对象生命周期的理解)
  - [requireJS的核心原理是什么？（如何动态加载的？如何避免多次加载的？如何缓存的？）](#requireJS的核心原理是什么如何动态加载的如何避免多次加载的如何缓存的)
  - [什么是“前端路由”？什么时候适合使用“前端路由”？“前端路由”有哪些优点和缺点](#什么是前端路由什么时候适合使用前端路由前端路由有哪些优点和缺点)
  - [Polyfill](#Polyfill)
  - [rest参数](#rest参数)
  - [Proxy](#Proxy)
  - [gulp](#gulp)
  - [web开发中会话跟踪的方法有哪些](#web开发中会话跟踪的方法有哪些)
  - [进程间通信的方式](#进程间通信的方式)
  - [Reflect对象创建目的](#Reflect对象创建目的)

- [实现](#实现)
  - [Js动画与CSS动画区别及相应实现](#Js动画与CSS动画区别及相应实现)
  - [js拖拽功能的实现,对页面某个节点的拖曳如何做？（使用原生JS）](#js拖拽功能的实现对页面某个节点的拖曳如何做使用原生JS)
  - [使用js实现一个持续的动画效果](#使用js实现一个持续的动画效果)
  - [实现点击容器内的图标，图标边框变成border:1px solid red，点击空白处重置](#实现点击容器内的图标图标边框变成border1px-solid-red点击空白处重置)
  - [canvas上面随机布着一些黑块，请实现方法，计算canvas上有多少个黑块](#canvas上面随机布着一些黑块请实现方法计算canvas上有多少个黑块)
  - [怎么做JS代码Error统计](#怎么做JS代码Error统计)
  - [完成一个Dialog组件，说说你设计的思路？它应该有什么功能](#完成一个Dialog组件说说你设计的思路它应该有什么功能)
  - [js中倒计时的纠偏实现](#js中倒计时的纠偏实现)
  - [函数柯里化的实现](#函数柯里化的实现)
  - [EventEmitter实现](#EventEmitter实现)
  - [如何查找一篇英文文章中出现频率最高的单词](#如何查找一篇英文文章中出现频率最高的单词)
  - [实现Storage，使得该对象为单例，并对localStorage进行封装设置值setItem(key,value)和getItem(key)](#实现Storage使得该对象为单例并对localStorage进行封装设置值setItemkeyvalue和getItemkey)
  - [获取页面所有的checkbox](#获取页面所有的checkbox)

- [宏任务和微任务](#宏任务和微任务)
  - [requestAnimationFrame](#requestAnimationFrame)
  - [requestAnimationFrame对比setTimeout](#requestAnimationFrame对比setTimeout)
  - [setTimeout、Promise、Async/Await的区别](#setTimeoutPromiseAsyncAwait的区别)
  - [为什么使用setTimeout实现setInterval？怎么模拟](#为什么使用setTimeout实现setInterval怎么模拟)
  - [setTimeout(fn,0)多久才执行，Event Loop](#setTimeoutfn0多久才执行Event-Loop)
  - [setInterval存在哪些问题](#setInterval存在哪些问题)
  - [链式调用setTimeout对比setInterval](#链式调用setTimeout对比setInterval)
  - [event loop](#event-loop)
  - [浏览器宏微任务](#浏览器宏微任务)

- [对比](#对比)
  - [addEventListener()和attachEvent()的区别](#addEventListener和attachEvent的区别)
  - [attribute和property的区别是什么](#attribute和property的区别是什么)
  - [caller和callee的区别](#caller和callee的区别)
  - [Javascript中callee和caller的作用](#Javascript中callee和caller的作用)
  - [documen.write和innerHTML的区别](#documenwrite和innerHTML的区别)
  - [escape,encodeURI,encodeURIComponent区别](#escapeencodeURIencodeURIComponent区别)
  - [innerHTML与outerHTML的区别](#innerHTML与outerHTML的区别)
  - [js代码中的"use strict";是什么意思?使用它区别是什么](#js代码中的use-strict是什么意思使用它区别是什么)
  - [mouseover和mouseenter区别](#mouseover和mouseenter区别)
  - [offsetWidth/offsetHeight,clientWidth/clientHeight与scrollWidth/scrollHeight的区别](#offsetWidthoffsetHeightclientWidthclientHeight与scrollWidthscrollHeight的区别)
  - [toPrecision和toFixed和Math.round的区别](#toPrecision和toFixed和Mathround的区别)
  - [Unicode和UTF-8之间的关系](#Unicode和UTF-8之间的关系)
  - [window.onload和$(document).ready](#windowonload和documentready)
  - [区分什么是“客户区坐标”、“页面坐标”、“屏幕坐标”](#区分什么是客户区坐标页面坐标屏幕坐标)

- [算法](#算法)
  - [常用正则表达式](#常用正则表达式)
  - [生成随机数的各种方法](#生成随机数的各种方法)
  - [为什么0.1+0.2!=0.3？如何解决这个问题](#为什么010203如何解决这个问题)
  - [原码、反码和补码的介绍](#原码反码和补码的介绍)
  - [什么是尾调用，使用尾调用有什么好处](#什么是尾调用使用尾调用有什么好处)
  - [js中不同进制数字的表示方式](#js中不同进制数字的表示方式)
  - [Math.ceil和Math.floor](#Mathceil和Mathfloor)
  - [[,,,]的长度](#的长度)
  - [js for循环注意点](#js-for循环注意点)

- [其他](#其他)
  - [hybrid](#hybrid)
  - [组件化](#组件化)
  - [如何测试前端代码？知道BDD,TDD,Unit Test吗？知道怎么测试你的前端工程吗(mocha,sinon,jasmin,qUnit..)](#如何测试前端代码知道BDDTDDUnit-Test吗知道怎么测试你的前端工程吗mochasinonjasminqUnit)
  - [为什么通常在发送数据埋点请求的时候使用的是1x1像素的透明gif图片](#为什么通常在发送数据埋点请求的时候使用的是1x1像素的透明gif图片)
  - [如何确定页面的可用性时间，什么是Performance API](#如何确定页面的可用性时间什么是Performance-API)
  - [Electron](#Electron)
  - [有四个操作会忽略enumerable为false的属性](#有四个操作会忽略enumerable为false的属性)
  - [一道常被人轻视的前端JS面试题](#一道常被人轻视的前端JS面试题)
  - [内存机制](#内存机制)
  - [执行上下文](#执行上下文)
  - [代码的复用](#代码的复用)
  - [JavaScript实现对上传图片的压缩](#JavaScript实现对上传图片的压缩)


- [ES6](#ES6)
  - [ES6的了解](#ES6的了解)
  - [ES5、ES6和ES2015有什么区别](#ES5ES6和ES2015有什么区别)
  - [es6新特性](#es6新特性)
  - [let var const](#let-var-const)
  - [全局作用域中，用const和let声明的变量不在window上，那到底在哪里？如何去获取](#全局作用域中用const和let声明的变量不在window上那到底在哪里如何去获取)
  - [箭头函数](#箭头函数)
  - [模板字符串](#模板字符串)
  - [for in和for of的区别](#箭头函数)
  - [arguments对象](#arguments对象)
  - [async/await](#asyncawait)
  - [解构赋值](#解构赋值)
  - [babel是什么，有什么作用](#babel是什么有什么作用)
  - [let有什么用，有了var为什么还要用let](#let有什么用有了var为什么还要用let)
  - [举一些ES6对String字符串类型做的常用升级优化](#举一些ES6对String字符串类型做的常用升级优化)
  - [举一些ES6对Array数组类型做的常用升级优化](#举一些ES6对Array数组类型做的常用升级优化)
  - [举一些ES6对Number数字类型做的常用升级优化](举一些ES6对Number数字类型做的常用升级优化)
  - [举一些ES6对Object类型做的常用升级优化](#举一些ES6对Object类型做的常用升级优化)
  - [举一些ES6对Function函数类型做的常用升级优化](#举一些ES6对Function函数类型做的常用升级优化)
  - [Symbol是什么，有什么作用](#Symbol是什么有什么作用)
  - [Set是什么，有什么作用](#Set是什么有什么作用)
  - [Map是什么，有什么作用](#Map是什么有什么作用)
  - [介绍下Set、Map、WeakSet和WeakMap的区别](#介绍下SetMapWeakSet和WeakMap的区别)
  - [Proxy是什么，有什么作用](#Proxy是什么有什么作用)
  - [Reflect是什么，有什么作用](#Reflect是什么有什么作用)
  - [Promise是什么，有什么作用](#Promise是什么有什么作用)
  - [Promise的构造函数](#Promise的构造函数)
  - [promise的用法和几种状态](#promise的用法和几种状态)
  - [Promise.all()和Promise.allSettled()的比较](#Promiseall和PromiseallSettled的比较)
  - [Iterator是什么，有什么作用](#Iterator是什么有什么作用)
  - [for...in和for...of有什么区别](#forin和forof有什么区别)
  - [Generator函数是什么，有什么作用](#Generator函数是什么有什么作用)
  - [async函数是什么，有什么作用](#async函数是什么有什么作用)
  - [Class、extends是什么，有什么作用](#Classextends是什么有什么作用)
  - [module、export、import是什么，有什么作用](#moduleexportimport是什么有什么作用)
  - [日常前端代码开发中，有哪些值得用ES6去改进的编程优化或者规范](#日常前端代码开发中有哪些值得用ES6去改进的编程优化或者规范)
  - [es6模块化](#es6模块化)
  - [ES5/ES6的继承除了写法以外还有什么区别](#ES5ES6的继承除了写法以外还有什么区别)














### js数据类型
```
js基本数据类型：
Undefined、Null、Boolean、Number、String，还有在 ES6 中新增的 
Symbol 和 ES10 中新增的 BigInt 类型。

Symbol 代表创建后独一无二且不可变的数据类型，它的出现我认为主要是
为了解决可能出现的全局变量冲突的问题。

BigInt 是一种数字类型的数据，它可以表示任意精度格式的整数，
使用 BigInt 可以安全地存储和操作大整数，
即使这个数已经超出了 Number 能够表示的安全整数范围。
```

```
js引用数据类型：object、array、function
```

  #### js有几种类型的值
```
js 可以分为两种类型的值，一种是基本数据类型，一种是复杂数据类型。
基本数据类型：undefined、null、boolean、number、string、symbol
复杂数据类型指的是 Object 类型，所有其他的如 Array、Date 
等数据类型都可以理解为 Object 类型的子类。

两种类型间的主要区别是它们的存储位置不同，基本数据类型的值直接保存在栈中，
而复杂数据类型的值保存在堆中，通过使用在栈中保存对应的指针来获取堆中的值。
```

栈：原始数据类型（Undefined、Null、Boolean、Number、String） <br>
堆：引用数据类型（对象、数组和函数）

```
两种类型的区别是：存储位置不同。
原始数据类型直接存储在栈（stack）中的简单数据段，占据空间小、
大小固定，属于被频繁使用数据，所以放入栈中存储。

引用数据类型存储在堆（heap）中的对象，占据空间大、大小不固定。
如果存储在栈中，将会影响程序运行的性能；引用数据类型在栈中存储了指针，
该指针指向堆中该实体的起始地址。当解释器寻找引用值时，
会首先检索其在栈中的地址，取得地址后从堆中获得实体。
```

JS内置类型
- JS 中分为七种内置类型，七种内置类型又分为两大类型：基本类型和对象（Object）。
- 基本类型有七种： null，undefined，boolean，number，string，symbol, bigint。
- 其中 JS 的数字类型是浮点类型的，没有整型。并且浮点类型基于 IEEE 754标准实现，在使用中会遇到某些 Bug。NaN 也属于 number 类型，并且 NaN 不等于自身。
- 对于基本类型来说，如果使用字面量的方式，那么这个变量只是个字面量，只有在必要的时候才会转换为对应的类型。

引用数据类型:
- 对象Object（包含普通对象-Object，数组对象-Array，正则对象-RegExp，日期对象-Date，数学函数-Math，函数对象-Function）
```
let a = 111 // 这只是字面量，不是 number 类型
a.toString() // 使用时候才会转换为对象类型
```

```
对象（Object）是引用类型，在使用过程中会遇到
浅拷贝和深拷贝的问题。
```

```
let a = { name: 'FE' }
let b = a
b.name = 'EF'
console.log(a.name) // EF
```

说出下面运行的结果，解释原因。
```
function test(person) {
  person.age = 26
  person = {
    name: 'hzj',
    age: 18
  }
  return person
}
const p1 = {
  name: 'fyq',
  age: 19
}
const p2 = test(p1)
console.log(p1) // -> ?
console.log(p2) // -> ?
```
```
// 结果:
p1：{name: “fyq”, age: 26}
p2：{name: “hzj”, age: 18}
```
- 原因: 在函数传参的时候传递的是对象在堆中的内存地址值，test函数中的实参person是p1对象的内存地址，通过调用person.age = 26确实改变了p1的值，但随后person变成了另一块内存空间的地址，并且在最后将这另外一份内存空间的地址返回，赋给了p2。

  #### 堆和栈
```
堆和栈的概念存在于数据结构中和操作系统内存中。

（1）在数据结构中，栈中数据的存取方式为先进后出。而堆是一个优先队列，
是按优先级来进行排序的，优先级可以按照大小来规定。完全二叉树是堆的一种实现方式。
（2）在操作系统中，内存被分为栈区和堆区。

栈区内存由编译器自动分配释放，存放函数的参数值，局部变量的值等。
其操作方式类似于数据结构中的栈。

堆区内存一般由程序员分配释放，若程序员不释放，程序结束时可能由垃圾回收机制回收。
```

- JS中栈和堆的区别
```
Js中内存空间主要为三种：栈、堆、池。栈中存放变量，
池中存放常量，堆中存放复杂的对象。
```

- 栈
```
栈是一种后入先出的数据结构，遵循先进后出，后进先出的原则
```

- 堆
```
所有的堆内存都有一个可被后续查找的16进制地址，
后续关联赋值的时候，是把堆内存中的内存地址给与变量操作。
```

- 区别
```
栈内存中变量一般在它的当前执行环境结束就会被
销毁被垃圾回收制回收， 而堆内存中的变量则不会，
因为不确定其他的地方是不是还有一些对它的引用。 
堆内存中的变量只有在所有对它的引用都结束的时候才会被回收。
```

```
注：由上述可知，闭包中的基本数据类型保存在堆中。
```

js中的变量类型与栈和堆的关系：
- 基本数据类型
```
js中基本数据类型都存储在栈内存中，大小固定，
可以根据值来访问，属于被频繁使用的数据。

var a = 1; //开辟栈内存，保存在栈中
var b = a; //不开辟新的栈内存，保存在栈中
var b = 2; //开辟新的栈内存，保存在栈中
console.log(a,b); //1 2
```

- 引用数据类型
```
js中引用数据类型都存储在堆内存中，大小不固定，
占据空间大。如果将引用数据类型存储在栈中会影响
成程序运行的性能。引用数据类型将在堆内存中的地址
保存到栈中，通过栈中的地址可以访问其实体。
var obj1 = {name : 1} ;//开辟堆内存，实体保存在堆中，obj1保存在栈中
var obj2 = obj1; //将{name : 1}的地址复制一份给b，并在栈中开辟新内存
obj2.name = 2; //改变堆中的对象
console.log(obj1);//obj1也被改变
```

  #### undefined与undeclared区别
```
已在作用域中声明但还没有赋值的变量，是 undefined 的。
相反，还没有在作用域中声明过的变量，是 undeclared 的。

对于 undeclared 变量的引用，浏览器会报引用错误，
如 ReferenceError: b is not defined。但是我们可以使用 
typeof 的安全防范机制来避免报错，因为对于 undeclared
（或者 not defined ）变量，typeof 会返回 "undefined"。
```

  #### null和undefined区别
```
首先 Undefined 和 Null 都是基本数据类型，这两个基本数据类型分别
都只有一个值，就是 undefined 和 null。

undefined 代表的含义是未定义，null 代表的含义是空对象。
一般变量声明了但还没有定义的时候会返回 undefined，
null主要用于赋值给一些可能会返回对象的变量，作为初始化。

undefined 在 js 中不是一个保留字，这意味着我们可以使用 undefined 
来作为一个变量名，这样的做法是非常危险的，它会影响我们对 undefined 
值的判断。但是我们可以通过一些方法获得安全的 undefined 值，比如说 void 0。

当我们对两种类型使用 typeof 进行判断的时候，Null 类型化会返回 
“object”，这是一个历史遗留的问题。当我们使用双等号对两种类型
的值进行比较时会返回 true，使用三个等号时会返回 false。
```

```
undefined 表示不存在这个值。

undefined :是一个表示"无"的原始值或者说表示"缺少值"，
就是此处应该有一个值，但是还没有定义。当尝试读取时会返回 undefined

例如变量被声明了，但没有赋值时，就等于undefined

null 表示一个对象被定义了，值为“空值”

null : 是一个对象(空对象, 没有任何属性和方法)

例如作为函数的参数，表示该函数的参数不是对象；

在验证null时，一定要使用　=== ，因为 ==无法分别null 和　undefined
```

- Undefined类型只有一个值，即undefined。当声明的变量还未被初始化时，变量的默认值为undefined。用法

- 变量被声明了，但没有赋值时，就等于undefined。
- 调用函数时，应该提供的参数没有提供，该参数等于undefined。
- 对象没有赋值的属性，该属性的值为undefined。
- 函数没有返回值时，默认返回undefined
```
Null类型也只有一个值，即null。null用来表示尚未存在的
对象，常用来表示函数企图返回一个不存在的对象。用法
```
- 作为函数的参数，表示该函数的参数不是对象。
- 作为对象原型链的终点

  #### null是对象吗？为什么
- 结论: null不是对象。
- 解释: 虽然 typeof null 会输出 object，但是这只是 JS 存在的一个悠久 Bug。在 JS 的最初版本中使用的是 32 位系统，为了性能考虑使用低位存储变量的类型信息，000 开头代表是对象然而 null 表示为全零，所以将它错误的判断为 object 。

  #### 如何获取安全的undefined值
```
因为 undefined 是一个标识符，所以可以被当作变量来使用和赋值，
但是这样会影响 undefined 的正常判断。

表达式 void ___ 没有返回值，因此返回结果是 undefined。
void 并不改变表达式的结果，只是让表达式不返回值。

按惯例我们用 void 0 来获得 undefined。
```

  #### Symbol类型的注意点
```
Symbol 函数前不能使用 new 命令，否则会报错。

Symbol 函数可以接受一个字符串作为参数，表示对 Symbol 实例的描述，
主要是为了在控制台显示，或者转为字符串时，比较容易区分。

Symbol 作为属性名，该属性不会出现在 for...in、for...of 循环中，
也不会被 Object.keys()、Object.getOwnPropertyNames()、JSON.stringify() 返回。

Object.getOwnPropertySymbols 方法返回一个数组，
成员是当前对象的所有用作属性名的 Symbol 值。

Symbol.for 接受一个字符串作为参数，然后搜索有没有以该参数作为名称的 Symbol 值。
如果有，就返回这个 Symbol 值，否则就新建并返回一个以该字符串为名称的 Symbol 值。

Symbol.keyFor 方法返回一个已登记的 Symbol 类型值的 key。
```

  #### js中整数的安全范围是多少
```
安全整数指的是，在这个范围内的整数转化为二进制存储的时候不会出现精度丢失，
能够被“安全”呈现的最大整数是 2^53 - 1，即9007199254740991，
在 ES6 中被定义为 Number.MAX_SAFE_INTEGER。
最小整数是-9007199254740991，在 ES6 中被定义为 Number.MIN_SAFE_INTEGER。

如果某次计算的结果得到了一个超过 JavaScript 数值范围的值，
那么这个值会被自动转换为特殊的 Infinity 值。如果某次计算返回了
正或负的 Infinity 值，那么该值将无法参与下一次的计算。
判断一个数是不是有穷的，可以使用 isFinite 函数来判断。
```

#### JS整数是怎么表示的
- 通过 Number 类型来表示，遵循 IEEE754 标准，通过 64 位来表示一个数字，（1 + 11 + 52），最大安全数字是 Math.pow(2, 53) - 1，对于 16 位十进制。（符号位 + 指数位 + 小数部分有效位）

#### Number()的存储空间是多大？如果后台发送了一个超过最大自己的数字怎么办
- Math.pow(2, 53) ，53 为有效数字，会发生截断，等于 JS 能支持的最大数字。

  #### '1'.toString()为什么可以调用
其实在这个语句运行的过程中做了这样几件事情：
```
var s = new Object('1');
s.toString();
s = null;
```
- 第一步: 创建Object类实例。注意为什么不是String ？ 由于Symbol和BigInt的出现，对它们调用new都会报错，目前ES6规范也不建议用new来创建基本类型的包装类。
- 第二步: 调用实例方法。
- 第三步: 执行完方法立即销毁这个实例。
```
整个过程体现了基本包装类型的性质，而基本包装类型恰恰
属于基本数据类型，包括Boolean, Number和String。
```

  #### 如何理解BigInt
什么是BigInt?
- BigInt是一种新的数据类型，用于当整数值大于Number数据类型支持的范围时。这种数据类型允许我们安全地对大整数执行算术操作，表示高分辨率的时间戳，使用大整数id，等等，而不需要使用库。

为什么需要BigInt?
- 在JS中，所有的数字都以双精度64位浮点格式表示，那这会带来什么问题呢？
  - 这导致JS中的Number无法精确表示非常大的整数，它会将非常大的整数四舍五入，确切地说，JS中的Number类型只能安全地表示-9007199254740991(-(2^53-1))和9007199254740991（(2^53-1)），任何超出此范围的整数值都可能失去精度。
```
console.log(999999999999999);  //=>10000000000000000
```
同时也会有一定的安全性问题:
```
9007199254740992 === 9007199254740993;    // → true 居然是true!
```
如何创建并使用BigInt？
- 要创建BigInt，只需要在数字末尾追加n即可
```
console.log( 9007199254740995n );    // → 9007199254740995n	
console.log( 9007199254740995 );     // → 9007199254740996
```
- 另一种创建BigInt的方法是用BigInt()构造函数
```
BigInt("9007199254740995");    // → 9007199254740995n
```
简单使用如下:
```
10n + 20n;    // → 30n	
10n - 20n;    // → -10n	
+10n;         // → TypeError: Cannot convert a BigInt value to a number	
-10n;         // → -10n	
10n * 20n;    // → 200n	
20n / 10n;    // → 2n	
23n % 10n;    // → 3n	
10n ** 3n;    // → 1000n	

const x = 10n;	
++x;          // → 11n	
--x;          // → 9n
console.log(typeof x);   //"bigint"
```
值得警惕的点
- BigInt不支持一元加号运算符, 这可能是某些程序可能依赖于 + 始终生成 Number 的不变量，或者抛出异常。另外，更改 + 的行为也会破坏 asm.js 代码。

- 因为隐式类型转换可能丢失信息，所以不允许在bigint和 Number 之间进行混合操作。当混合使用大整数和浮点数时，结果值可能无法由BigInt或Number精确表示。
```
10 + 10n;    // → TypeError
```
- 不能将BigInt传递给Web api和内置的 JS 函数，这些函数需要一个 Number 类型的数字。尝试这样做会报TypeError错误。
```
Math.max(2n, 4n, 6n);    // → TypeError
```
- 当 Boolean 类型与 BigInt 类型相遇时，BigInt 的处理方式与Number类似，换句话说，只要不是0n，BigInt就被视为truthy的值。
```
if(0n){//条件判断为false

}
if(3n){//条件为true

}
```
- 元素都为BigInt的数组可以进行sort。
- BigInt可以正常地进行位运算，如|、&、<<、>>和^

浏览器兼容性
- 其实现在的兼容性并不怎么好，只有chrome67、firefox、Opera这些主流实现，要正式成为规范，其实还有很长的路要走。

  ### js类型判断
typeof，instanceof，constructor，Object.prototype.toString.call()

- typeof
  - 直接在计算机底层基于数据类型的值（二进制）进行检测
  - typeof null为object 原因是对象存在在计算机中，都是以000开始的二进制存储，所以检测出来的结果是对象
  - typeof 普通对象/数组对象/正则对象/日期对象 都是object
  - typeof NaN === 'number'
- instanceof
  - 检测当前实例是否属于这个类的
  - 底层机制：只要当前类出现在实例的原型上，结果都是true
  - 不能检测基本数据类型
- constructor
  - 支持基本类型
  - constructor可以随便改，也不准
- Object.prototype.toString.call([val])
  - 返回当前实例所属类信息
```
判断 Target 的类型，单单用 typeof 并无法完全满足，
这其实并不是 bug，本质原因是 JS 的万物皆对象的理论。
因此要真正完美判断时，我们需要区分对待:
```
- 基本类型(null): 使用 String(null)
- 基本类型(string / number / boolean / undefined) + function: - 直接使用 typeof即可
- 其余引用类型(Array / Date / RegExp Error): 调用toString后根据[object XXX]进行判断
很稳的判断封装:
```
let class2type = {}
'Array Date RegExp Object Error'.split(' ').forEach(e => class2type[ '[object ' + e + ']' ] = e.toLowerCase()) 

function type(obj) {
    if (obj == null) return String(obj)
    return typeof obj === 'object' ? class2type[ Object.prototype.toString.call(obj) ] || 'object' : typeof obj
}
```

  #### typeof操作符
优点：能够快速区分基本数据类型 
缺点：不能将Object、Array和Null区分，都返回object  

（1）对于原始类型来说，除了 null 都可以显示正确的类型
```
Number、String，Undefined、Boolean、Null、
还有在 ES6 中新增的 Symbol 和 ES10 中新增的 BigInt 

typeof 1             // 'number'
typeof '1'           // 'string'
typeof undefined     // 'undefined'
typeof true          // 'boolean'
typeof Symbol()      // 'symbol'
typeof null          // 'object'
PS：为什么null会出现这种情况呢？因为在 JS的最初版本中，
使用的是 32 位系统，为了性能考虑使用低位存储了变量的类型信息，
000 开头代表是对象，然而 null表示为全零，所以将它错误的判断为 object 。
虽然现在的内部类型判断代码已经改变了，但是对于这个Bug却是一直流传下来。
```

（2）typeof 对于对象来说，除了函数都会显示 object，
所以说 typeof 并不能准确判断变量到底是什么类型
```
array、object、function
typeof []             // 'object'
typeof {}             // 'object'
typeof console.log    // 'function'
```

- 在写业务逻辑的时候，经常要用到JS数据类型的判断，面试常见的案例深浅拷贝也要用到数据类型的判断。

typeof
```
console.log(typeof 2);               // number
console.log(typeof true);            // boolean
console.log(typeof 'str');           // string
console.log(typeof undefined);       // undefined
console.log(typeof []);              // object 
console.log(typeof {});              // object
console.log(typeof function(){});    // function
console.log(typeof null);            // object
```
- 优点：能够快速区分基本数据类型 
- 缺点：不能将Object、Array和Null区分，都返回object

   #### typeof NaN的结果是什么
```
typeof NaN;           // "number"

NaN 意指“不是一个数字”（not a number），NaN 是一个“警戒值”
（sentinel value，有特殊用途的常规值），用于指出数字类型中的错误情况，
即“执行数学运算没有成功，这是失败后返回的结果”。NaN 是一个特殊值，
它和自身不相等，是唯一一个非自反（自反，reflexive，
即 x === x 不成立）的值。而 NaN != NaN为 true。
```

  #### instanceof
```
作用：用于判断实例属于哪个构造函数。
原理：判断实例对象的__proto__属性，和构造函数的prototype属性，
是否为同一个引用（是否指向同一个地址）。instanceof 可以正确的判断对象的类型，
因为内部机制是通过判断对象的原型链中是不是能找到类型的 prototype

优点：能够区分Array、Object和Function，适合用于判断自定义的类实例对象
缺点：Number，Boolean，String基本数据类型不能判断

console.log(2 instanceof Number);                    // false
console.log(true instanceof Boolean);                // false 
console.log('str' instanceof String);                // false  
console.log([] instanceof Array);                    // true
console.log(function(){} instanceof Function);       // true
console.log({} instanceof Object);                   // true    

instanceof 在MDN中的解释：instanceof 运算符用来测试一个对象
在其原型链中是否存在一个构造函数的 prototype 属性。
其意思就是判断对象是否是某一数据类型（如Array）的实例，
请重点关注一下是判断一个对象是否是数据类型的实例。
在这里字面量值，2， true ，'str'不是实例，所以判断值为false
```

```
实现instanceof：
(1)首先获取类型的原型
(2)获得对象的原型
(3)一直循环判断对象的原型是否等于类型的原型，
直到对象原型为 null，因为原型链最终为 null

function instanceof(left, right) {
    // 获得类型的原型
    let prototype = right.prototype
    // 获得对象的原型
    left = left.__proto__
    // 判断对象的类型是否等于类型的原型
    while (true) {
    	if (left === null)
    		return false
    	if (prototype === left)
    		return true
    	left = left.__proto__
    }
}
```

```
注意1：虽然说，实例是由构造函数 new 出来的，但是实例的__proto__属性引用的是
构造函数的prototype。也就是说，实例的__proto__属性与构造函数本身无关。
注意2：在原型链上，原型的上面可能还会有原型，以此类推往上走，继续找__proto__属性。
这条链上如果能找到， instanceof 的返回结果也是 true。

比如说：
foo instance of Foo的结果为true，
因为foo.__proto__ === M.prototype为true。

foo instance of Object的结果也为true，
为Foo.prototype.__proto__ === Object.prototype为true。

但我们不能轻易的说：foo 一定是 由Object创建的实例。
这句话是错误的。我们来看下一个问题就明白了。

问题：已知A继承了B，B继承了C。怎么判断 a 是由A直接生成的实例，
还是B直接生成的实例呢？还是C直接生成的实例呢？
分析：这就要用到原型的constructor属性了。
foo.__proto__.constructor === M的结果为true，
但是 foo.__proto__.constructor === Object的结果为false。
所以，用 consturctor判断就比用 instanceof判断，更为严谨。
```

instanceof
```
console.log(2 instanceof Number);                    // false
console.log(true instanceof Boolean);                // false 
console.log('str' instanceof String);                // false  
console.log([] instanceof Array);                    // true
console.log(function(){} instanceof Function);       // true
console.log({} instanceof Object);                   // true
```
- 优点：能够区分Array、Object和Function，适合用于判断自定义的类实例对象
- 缺点：Number，Boolean，String基本数据类型不能判断

  #### typeof和instanceof区别
- typeof 对于基本类型，除了 null都可以显示正确的类型
```
typeof 1 // 'number'
typeof '1' // 'string'
typeof undefined // 'undefined'
typeof true // 'boolean'
typeof Symbol() // 'symbol'
typeof b // b 没有声明，但是还会显示 undefined
```
- typeof 对于对象，除了函数都会显示 object
```
typeof [] // 'object'
typeof {} // 'object'
typeof console.log // 'function'
```
- 对于 null 来说，虽然它是基本类型，但是会显示 object，这是一个存在很久了的 Bug
```
typeof null // 'object'
```
- instanceof 可以正确的判断对象的类型，因为内部机制是通过判断对象的原型链中是不是能找到类型的 iprototype
```
// 我们也可以试着实现一下 instanceof
function instanceof(left, right) {
    // 获得类型的原型
    let prototype = right.prototype
    // 获得对象的原型
    left = left.__proto__
    // 判断对象的类型是否等于类型的原型
    while (true) {
    	if (left === null)
    		return false
    	if (prototype === left)
    		return true
    	left = left.__proto__
    }
}
```

  #### constructor
```
console.log((2).constructor === Number);                  // true
console.log((true).constructor === Boolean);              // true
console.log(('str').constructor === String);              // true
console.log(([]).constructor === Array);                  // true
console.log((function() {}).constructor === Function);    // true
console.log(({}).constructor === Object);                 // true

坑：如果创建一个对象，更改它的原型，constructor就会变得不可靠了
function Fn(){};
Fn.prototype=new Array();
var f=new Fn();
console.log(f.constructor===Fn);    // false
console.log(f.constructor===Array); // true 
```

  #### Object.prototype.toString.call()
```
使用 Object 对象的原型方法 toString ，使用 call 
进行狸猫换太子，借用Object的 toString 方法

优点：精准判断数据类型
缺点：写法繁琐不容易记，推荐进行封装后使用

var a = Object.prototype.toString;
console.log(a.call(2));               // [object Number]
console.log(a.call(true));            // [object Boolean]
console.log(a.call('str'));           // [object String]
console.log(a.call([]));              // [object Array]
console.log(a.call(function(){}));    // [object Function]
console.log(a.call({}));              // [object Object]
console.log(a.call(undefined));       // [object Undefined]
console.log(a.call(null));            // [object Null]
```

Object.prototype.toString.call()
```
var toString = Object.prototype.toString;
 
console.log(toString.call(2));                      //[object Number]
console.log(toString.call(true));                   //[object Boolean]
console.log(toString.call('str'));                  //[object String]
console.log(toString.call([]));                     //[object Array]
console.log(toString.call(function(){}));           //[object Function]
console.log(toString.call({}));                     //[object Object]
console.log(toString.call(undefined));              //[object Undefined]
console.log(toString.call(null));                   //[object Null]
```
- 优点：精准判断数据类型
- 缺点：写法繁琐不容易记，推荐进行封装后使用

  #### 判断是否是promise对象
```
function isPromise (val) {
    return (
      typeof val.then === 'function' &&
      typeof val.catch === 'function'
    )
}
```

  #### 封装javascript的类型判断函数
```js
function getType(value) {
  // 判断数据是 null 的情况
  if (value === null) {
    return value + "";
  }

  // 判断数据是引用类型的情况
  if (typeof value === "object") {
    let valueClass = Object.prototype.toString.call(value),
      type = valueClass.split(" ")[1].split("");

    type.pop();

    return type.join("").toLowerCase();
  } else {
    // 判断数据是基本数据类型的情况和函数的情况
    return typeof value;
  }
}
```

  #### Object.is和===的区别
- Object在严格等于的基础上修复了一些特殊情况下的失误，具体来说就是+0和-0，NaN和NaN。 源码如下
```
function is(x, y) {
  if (x === y) {
    //运行到1/x === 1/y的时候x和y都为0，但是1/+0 = +Infinity， 1/-0 = -Infinity, 是不一样的
    return x !== 0 || y !== 0 || 1 / x === 1 / y;
  } else {
    //NaN===NaN是false,这是不对的，我们在这里做一个拦截，x !== x，那么一定是 NaN, y 同理
    //两个都是NaN的时候返回true
    return x !== x && y !== y;
  }
}
```


### js类型转换
- 大家都知道 JS 中在使用运算符号或者对比符时，会自带隐式转换，规则如下:

#### 转化规则
- -、*、/、%：一律转换成数值后计算
- +：
  - 数字 + 字符串 = 字符串， 运算顺序是从左到右
  - 数字 + 对象， 优先调用对象的valueOf -> toString
  - 数字 + boolean/null -> 数字
  - 数字 + undefined -> NaN
- [1].toString() === '1'
- {}.toString() === '[object object]'
- NaN !== NaN 、+undefined 为 NaN
```
首先我们要知道，在 JS 中类型转换只有三种情况，分别是：
```
- 转换为布尔值
- 转换为数字
- 转换为字符串
```
原始值                     转换目标           结果
number                     布尔值         除了0、-0、NaN都为true
string                     布尔值         除了空串都为true
undefined、null            布尔值         FALSE
引用类型                    布尔值         TRUE
number                     字符串         5 => '5'
Boolean、函数、Symbol       字符串        'true'
数组                       字符串         [1,2] => '1,2'
对象                       字符串         '[object Object]'
string                     数字          '1' => 1,'a' => NaN
数组                       数字           空数组为0，存在一个元素且为数字转数字，其他情况NaN
null                       数字            0
除了数组的引用类型           数字           NaN
Symbol                     数字           抛错
```

#### 转Boolean
- 在条件判断时，除了 undefined，null， false， NaN， ''， 0， -0，其他所有值都转为 true，包括所有对象

#### 对象转原始类型是根据什么流程运行的
- 对象转原始类型，会调用内置的[ToPrimitive]函数，对于该函数而言，其逻辑如下：
  - 如果有Symbol.toPrimitive()方法，优先调用再返回
  - 调用valueOf()，如果转换为原始类型，则返回
  - 调用toString()，如果转换为原始类型，则返回
  - 如果都没有返回原始类型，会报错
```
var obj = {
  value: 3,
  valueOf() {
    return 4;
  },
  toString() {
    return '5'
  },
  [Symbol.toPrimitive]() {
    return 6
  }
}
console.log(obj + 1); // 输出7
```

#### 如何让if(a == 1 && a == 2)条件成立
其实就是上一个问题的应用。
```
var a = {
  value: 0,
  valueOf: function() {
    this.value++;
    return this.value;
  }
};
console.log(a == 1 && a == 2);//true
```

#### 四则运算符
它有以下几个特点：
- 运算中其中一方为字符串，那么就会把另一方也转换为字符串
- 如果一方不是字符串或者数字，那么会将它转换为数字或者字符串
```
1 + '1' // '11'
true + true // 2
4 + [1,2,3] // "41,2,3"
```
- 对于第一行代码来说，触发特点一，所以将数字 1 转换为字符串，得到结果 '11'
- 对于第二行代码来说，触发特点二，所以将 true 转为数字 1
- 对于第三行代码来说，触发特点二，所以将数组通过 toString转为字符串 1,2,3，得到结果 41,2,3

另外对于加法还需要注意这个表达式 'a' + + 'b'

- 'a' + + 'b' // -> "aNaN"
因为 + 'b' 等于 NaN，所以结果为 "aNaN"，你可能也会在一些代码中看到过 + '1'的形式来快速获取 number 类型。
- 那么对于除了加法的运算符来说，只要其中一方是数字，那么另一方就会被转为数字
4 * '3' // 12
4 * [] // 0
4 * [1, 2] // NaN

#### 比较运算符
- 如果是对象，就通过 toPrimitive 转换对象
- 如果是字符串，就通过 unicode 字符索引来比较
```
let a = {
  valueOf() {
    return 0
  },
  toString() {
    return '1'
  }
}
a > -1 // true
```
- 在以上代码中，因为 a 是对象，所以会通过 valueOf 转换为原始类型再比较值。

  #### 其他值到字符串的转换规则
```
规范的 9.8 节中定义了抽象操作 ToString ，
它负责处理非字符串到字符串的强制类型转换。
（1）Null 和 Undefined 类型 ，null 转换为 "null"，
undefined 转换为 "undefined"，

（2）Boolean 类型，true 转换为 "true"，false 转换为 "false"。

（3）Number 类型的值直接转换，不过那些极小和极大的数字会使用指数形式。

（4）Symbol 类型的值直接转换，但是只允许显式强制类型转换，
使用隐式强制类型转换会产生错误。

（5）对普通对象来说，除非自行定义 toString() 方法，否则会调用 
toString()（Object.prototype.toString()）来返回内部属性 
[[Class]] 的值，如"[object Object]"。如果对象有自己的 
toString() 方法，字符串化时就会调用该方法并使用其返回值。
```

  #### 其他值到数字值的转换规则
```
有时我们需要将非数字值当作数字来使用，比如数学运算。
为此 ES5 规范在 9.3 节定义了抽象操作 ToNumber。

（1）Undefined 类型的值转换为 NaN。

（2）Null 类型的值转换为 0。

（3）Boolean 类型的值，true 转换为 1，false 转换为 0。

（4）String 类型的值转换如同使用 Number() 函数进行转换，
如果包含非数字值则转换为 NaN，空字符串为 0。

（5）Symbol 类型的值不能转换为数字，会报错。

（6）对象（包括数组）会首先被转换为相应的基本类型值，如果
返回的是非数字的基本类型值，则再遵循以上规则将其强制转换为数字。

为了将值转换为相应的基本类型值，抽象操作 ToPrimitive 会首先
（通过内部操作 DefaultValue）检查该值是否有valueOf() 方法。
如果有并且返回基本类型值，就使用该值进行强制类型转换。
如果没有就使用 toString() 的返回值（如果存在）来进行强制类型转换。

如果 valueOf() 和 toString() 均不返回基本类型值，会产生 TypeError 错误。
```

  #### 其他值到布尔类型的值的转换规则
```
ES5 规范 9.2 节中定义了抽象操作 ToBoolean，
列举了布尔强制类型转换所有可能出现的结果。

以下这些是假值：
• undefined
• null
• false
• +0、-0 和 NaN
• ""

假值的布尔强制类型转换结果为 false。
从逻辑上说，假值列表以外的都应该是真值。
```

  #### 如何将字符串转化为数字，例如'12.3b'
```
（1）使用 Number() 方法，前提是所包含的字符串不包含不合法字符。

（2）使用 parseInt() 方法，parseInt() 函数可解析一个字符串，
并返回一个整数。还可以设置要解析的数字的基数。当基数的值为 0，
或没有设置该参数时，parseInt() 会根据 string 来判断数字的基数。

（3）使用 parseFloat() 方法，该函数解析一个字符串参数并返回一个浮点数。

（4）使用 + 操作符的隐式转换。
```

  #### 什么情况下会发生布尔值的隐式强制类型转换
```
（1） if (..) 语句中的条件判断表达式。
（2） for ( .. ; .. ; .. ) 语句中的条件判断表达式（第二个）。
（3） while (..) 和 do..while(..) 循环中的条件判断表达式。
（4） ? : 中的条件判断表达式。
（5） 逻辑运算符 ||（逻辑或）和 &&（逻辑与）左边的操作数（作为条件判断表达式）。
```

  #### Symbol值的强制类型转换
```
ES6 允许从符号到字符串的显式强制类型转换，
然而隐式强制类型转换会产生错误。

Symbol 值不能够被强制类型转换为数字（显式和隐式都会产生错误），
但可以被强制类型转换为布尔值（显式和隐式结果都是 true ）。
```

  #### 将浮点数点左边的数每三位添加一个逗号,12000000.11转化为『12,000,000.11』
```js
// 方法一
function format(number) {
  return number && number.replace(/(?!^)(?=(\d{3})+\.)/g, ",");
}
// 方法二
function format1(number) {
  return Intl.NumberFormat().format(number)
}
// 方法三
function format2(number) {
  return number.toLocaleString('en')
}
```

  #### 解析字符串中的数字和将字符串强制类型转换为数字的返回结果都是数字,区别
```
解析允许字符串（如 parseInt() ）中含有非数字字符，
解析按从左到右的顺序，如果遇到非数字字符就停止。而转换
（如 Number ()）不允许出现非数字字符，否则会失败并返回 NaN。
```

#### [] == ![]结果是什么？为什么
- == 中，左右两边都需要转换为数字然后进行比较
- []转换为数字为0
- ![] 首先是转换为布尔值，由于[]作为一个引用类型转换为布尔值为true
- 因此![]为false，进而在转换成数字，变为0
- 0 == 0 ， 结果为true

#### ==和===有什么区别
- ===叫做严格相等，是指：左右两边不仅值要相等，类型也要相等，例如'1'===1的结果是false，因为一边是string，另一边是number

- ==不像===那样严格，对于一般情况，只要值相等，就返回true，但==还涉及一些类型转换，它的转换规则如下

  - 两边的类型是否相同，相同的话就比较值的大小，例如1==2，返回false
  - 判断的是否是null和undefined，是的话就返回true
  - 判断的类型是否是String和Number，是的话，把String类型转换成Number，再进行比较
  - 判断其中一方是否是Boolean，是的话就把Boolean转换成Number`，再进行比较
  - 如果其中一方为Object，且另一方为String、Number或者Symbol，会将Object转换成字符串，再进行比较

```
对于 == 来说，如果对比双方的类型不一样的话，就会进行类型转换
```

假如我们需要对比 x 和 y 是否相同，就会进行如下判断流程
- 1.首先会判断两者类型是否相同。相同的话就是比大小了
- 2.类型不相同的话，那么就会进行类型转换
- 3.会先判断是否在对比 null 和 undefined，是的话就会返回 true
- 4.判断两者类型是否为 string 和 number，是的话就会将字符串转换为 number
```
1 == '1'
      ↓
1 ==  1
```
- 5.判断其中一方是否为 boolean，是的话就会把 boolean 转为 number 再进行判断
```
'1' == true
        ↓
'1' ==  1
        ↓
 1  ==  1
```
- 6.判断其中一方是否为 object 且另一方为 string、number 或者 symbol，是的话就会把 object 转为原始类型再进行判断
```
'1' == { name: 'yck' }
        ↓
'1' == '[object Object]'
```

```
对于 === 来说就简单多了，就是判断两者类型和值是否相同
```


### js属性

  #### 内部属性[[Class]]是什么
```
所有 typeof 返回值为 "object" 的对象（如数组）都包含一个
内部属性 [[Class]]（我们可以把它看作一个内部的分类，而非
传统的面向对象意义上的类）。这个属性无法直接访问，
一般通过 Object.prototype.toString(..) 来查看。例如：

Object.prototype.toString.call( [1,2,3] );
// "[object Array]"

Object.prototype.toString.call( /regex-literal/i );
// "[object RegExp]"

// 我们自己创建的类就不会有这份特殊待遇，因为 toString() 找不到 toStringTag 属性时只好返回默认的 Object 标签
// 默认情况类的[[Class]]返回[object Object]
class Class1 {}
Object.prototype.toString.call(new Class1()); // "[object Object]"
// 需要定制[[Class]]
class Class2 {
  get [Symbol.toStringTag]() {
    return "Class2";
  }
}
Object.prototype.toString.call(new Class2()); // "[object Class2]"
```

  #### 属性的遍历
```
ES6 一共有 5 种方法可以遍历对象的属性。

（1）for...in
for...in循环遍历对象自身的和继承的可枚举属性（不含 Symbol 属性）。

（2）Object.keys(obj)
Object.keys返回一个数组，包括对象自身的（不含继承的）
所有可枚举属性（不含 Symbol 属性）的键名。

（3）Object.getOwnPropertyNames(obj)
Object.getOwnPropertyNames返回一个数组，包含对象自身的
所有属性（不含 Symbol 属性，但是包括不可枚举属性）的键名。

（4）Object.getOwnPropertySymbols(obj)
Object.getOwnPropertySymbols返回一个数组，
包含对象自身的所有 Symbol 属性的键名。

（5）Reflect.ownKeys(obj)
Reflect.ownKeys返回一个数组，包含对象自身的（不含继承的）所有键名，
不管键名是 Symbol 或字符串，也不管是否可枚举。

以上的 5 种方法遍历对象的键名，都遵守同样的属性遍历的次序规则。

首先遍历所有数值键，按照数值升序排列。
其次遍历所有字符串键，按照加入时间升序排列。
最后遍历所有 Symbol 键，按照加入时间升序排列。
Reflect.ownKeys({ [Symbol()]:0, b:0, 10:0, 2:0, a:0 })
// ['2', '10', 'b', 'a', Symbol()]
上面代码中，Reflect.ownKeys方法返回一个数组，包含了参数对象的所有属性。
这个数组的属性次序是这样的，首先是数值属性2和10，
其次是字符串属性b和a，最后是 Symbol 属性。
```

### js操作符

  #### ||和&&操作符的返回值
```
|| 和 && 首先会对第一个操作数执行条件判断，如果其不是布尔值
就先进行 ToBoolean 强制类型转换，然后再执行条件判断。

对于 || 来说，如果条件判断结果为 true 就返回第一个操作数的值，
如果为 false 就返回第二个操作数的值。

&& 则相反，如果条件判断结果为 true 就返回第二个操作数的值，
如果为 false 就返回第一个操作数的值。

|| 和 && 返回它们其中一个操作数的值，而非条件判断的结果
```

  #### ==操作符的强制类型转换规则
```
（1）字符串和数字之间的相等比较，将字符串转换为数字之后再进行比较。

（2）其他类型和布尔类型之间的相等比较，先将布尔值转换为数字后，
再应用其他规则进行比较。

（3）null 和 undefined 之间的相等比较，结果为真。
其他值和它们进行比较都返回假值。

（4）对象和非对象之间的相等比较，对象先调用 ToPrimitive 
抽象操作后，再进行比较。

（5）如果一个操作值为 NaN ，则相等比较返回 false
（ NaN 本身也不等于 NaN ）。

（6）如果两个操作值都是对象，则比较它们是不是指向同一个对象。
如果两个操作数都指向同一个对象，则相等操作符返回 true，否则，返回 false。
```

  #### 操作符什么时候用于字符串的拼接
```
根据 ES5 规范 11.6.1 节，如果某个操作数是字符串或者
能够通过以下步骤转换为字符串的话，+ 将进行拼接操作。
如果其中一个操作数是对象（包括数组），则首先对其调用 
ToPrimitive 抽象操作，该抽象操作再调用 [[DefaultValue]]，
以数字作为上下文。如果不能转换为字符串，
则会将其转换为数字类型来进行计算。

简单来说就是，如果 + 的其中一个操作数是字符串
（或者通过以上步骤最终得到字符串），则执行字符串拼接，
否则执行数字加法。

那么对于除了加法的运算符来说，只要其中一方是数字，
那么另一方就会被转为数字。
```

  #### ~操作符的作用
```
~ 返回 2 的补码，并且 ~ 会将数字转换为 32 位整数，
因此我们可以使用 ~ 来进行取整操作。

~x 大致等同于 -(x+1)。
```


### 类和对象

  #### JavaScript如何实现一个类，怎么实例化这个类
```
构造函数法（this + prototype） -- 用 new 关键字 生成实例对象
缺点：用到了 this 和 prototype，编写复杂，可读性差
function Mobile(name, price){
  this.name = name;
  this.price = price;
}
Mobile.prototype.sell = function(){
  alert(this.name + "，售价 $" + this.price);
}
var iPhone7 = new Mobile("iPhone7", 1000);
iPhone7.sell();
Object.create 法 -- 用 Object.create() 生成实例对象
缺点：不能实现私有属性和私有方法，实例对象之间也不能共享数据
 var Person = {
     firstname: "Mark",
     lastname: "Yun",
     age: 25,
     introduce: function(){
         alert('I am ' + Person.firstname + ' ' + Person.lastname);
     }
 };

 var person = Object.create(Person);
 person.introduce();

 // Object.create 要求 IE9+，低版本浏览器可以自行部署：
 if (!Object.create) {
　   Object.create = function (o) {
　　　 function F() {}
　　　 F.prototype = o;
　　　 return new F();
　　};
　}
极简主义法（消除 this 和 prototype） -- 调用 createNew() 得到实例对象
优点：容易理解，结构清晰优雅，符合传统的"面向对象编程"的构造
 var Cat = {
   age: 3, // 共享数据 -- 定义在类对象内，createNew() 外
   createNew: function () {
     var cat = {};
     // var cat = Animal.createNew(); // 继承 Animal 类
     cat.name = "小咪";
     var sound = "喵喵喵"; // 私有属性--定义在 createNew() 内，输出对象外
     cat.makeSound = function () {
       alert(sound);  // 暴露私有属性
     };
     cat.changeAge = function(num){
       Cat.age = num; // 修改共享数据
     };
     return cat; // 输出对象
   }
 };

 var cat = Cat.createNew();
 cat.makeSound();
ES6 语法糖 class -- 用 new 关键字 生成实例对象

class Point {
  constructor(x, y) {
    this.x = x;
    this.y = y;
  }
  toString() {
    return '(' + this.x + ', ' + this.y + ')';
  }
}

var point = new Point(2, 3);
```

  #### ECMAScript6怎么写class，为什么会出现class这种东西
```
在我看来 ES6 新添加的 class 只是为了补充 js 中缺少的一些
面向对象语言的特性，但本质上来说它只是一种语法糖，
不是一个新的东西，其背后还是原型继承的思想。
通过加入 class 可以有利于我们更好的组织代码。

在 class 中添加的方法，其实是添加在类的原型上的。
```

```
这个语法糖可以让有OOP基础的人更快上手js，至少是一个官方的实现了
但对熟悉js的人来说，这个东西没啥大影响；
一个Object.creat()搞定继承，比class简洁清晰的多
```

  #### javascript创建对象的几种方式

```
我们一般使用字面量的形式直接创建对象，但是这种创建方式
对于创建大量相似对象的时候，会产生大量的重复代码。但 js
和一般的面向对象的语言不同，在 ES6 之前它没有类的概念。
但是我们可以使用函数来进行模拟，从而产生出可复用的对象
创建方式，我了解到的方式有这么几种：

（1）第一种是工厂模式，工厂模式的主要工作原理是用函数来
封装创建对象的细节，从而通过调用函数来达到复用的目的。
但是它有一个很大的问题就是创建出来的对象无法和某个类型联系起来，
它只是简单的封装了复用代码，而没有建立起对象和类型间的关系。

（2）第二种是构造函数模式。js 中每一个函数都可以作为构造函数，
只要一个函数是通过 new 来调用的，那么我们就可以把它称为构造函数。
执行构造函数首先会创建一个对象，然后将对象的原型指向构造函数的 
prototype 属性，然后将执行上下文中的 this 指向这个对象，
最后再执行整个函数，如果返回值不是对象，则返回新建的对象。
因为 this 的值指向了新建的对象，因此我们可以使用 this 给对象赋值。
构造函数模式相对于工厂模式的优点是，所创建的对象和构造函数建立起了联系，
因此我们可以通过原型来识别对象的类型。但是构造函数存在一个缺点就是，
造成了不必要的函数对象的创建，因为在 js 中函数也是一个对象，
因此如果对象属性中如果包含函数的话，那么每次我们都会新建一个函数对象，
浪费了不必要的内存空间，因为函数是所有的实例都可以通用的。

（3）第三种模式是原型模式，因为每一个函数都有一个 prototype 属性，
这个属性是一个对象，它包含了通过构造函数创建的所有实例都能共享的属
性和方法。因此我们可以使用原型对象来添加公用属性和方法，从而实现代码
的复用。这种方式相对于构造函数模式来说，解决了函数对象的复用问题。
但是这种模式也存在一些问题，一个是没有办法通过传入参数来初始化值，
另一个是如果存在一个引用类型如 Array 这样的值，那么所有的实例将
共享一个对象，一个实例对引用类型值的改变会影响所有的实例。

（4）第四种模式是组合使用构造函数模式和原型模式，这是创建自定义类型
的最常见方式。因为构造函数模式和原型模式分开使用都存在一些问题，
因此我们可以组合使用这两种模式，通过构造函数来初始化对象的属性，
通过原型对象来实现函数方法的复用。这种方法很好的解决了两种模式单独
使用时的缺点，但是有一点不足的就是，因为使用了两种不同的模式，
所以对于代码的封装性不够好。

（5）第五种模式是动态原型模式，这一种模式将原型方法赋值的创建过程移动到了
构造函数的内部，通过对属性是否存在的判断，可以实现仅在第一次调用函数时
对原型对象赋值一次的效果。这一种方式很好地对上面的混合模式进行了封装。

（6）第六种模式是寄生构造函数模式，这一种模式和工厂模式的实现基本相同，
我对这个模式的理解是，它主要是基于一个已有的类型，在实例化时对实例化的
对象进行扩展。这样既不用修改原来的构造函数，也达到了扩展对象的目的。
它的一个缺点和工厂模式一样，无法实现对象的识别。

嗯我目前了解到的就是这么几种方式。
```

```
javascript创建对象简单的说,无非就是使用内置对象或各种自定义对象，
当然还可以用JSON；但写法有很多种，也能混合使用

对象字面量的方式：
person={firstname:"Mark",lastname:"Yun",age:25,eyecolor:"black"};
：
用function来模拟无参的构造函数
function Person(){}
	var person=new Person();//定义一个function，如果使用new"实例化",该function可以看作是一个Class
        person.name="Mark";
        person.age="25";
        person.work=function(){
        alert(person.name+" hello...");
}
person.work();

用function来模拟参构造函数来实现（用this关键字定义构造的上下文属性）：
function Pet(name,age,hobby){
       this.name=name;//this作用域：当前对象
       this.age=age;
       this.hobby=hobby;
       this.eat=function(){
           alert("我叫"+this.name+",我喜欢"+this.hobby+",是个程序员");
       }
}
var maidou =new Pet("麦兜",25,"coding");//实例化、创建对象
maidou.eat();//调用eat方法

用工厂方式来创建（内置对象）：
var wcDog =new Object();
     wcDog.name="旺财";
     wcDog.age=3;
     wcDog.work=function(){
       alert("我是"+wcDog.name+",汪汪汪......");
     }
     wcDog.work();
     
用原型方式来创建：
function Dog(){}
Dog.prototype.name="旺财";
Dog.prototype.eat=function(){
	alert(this.name+"是个吃货");
}
var wangcai =new Dog();
wangcai.eat();

用混合方式来创建：
 function Car(name,price){
	this.name=name;
	this.price=price;
}
Car.prototype.sell=function(){
	alert("我是"+this.name+"，我现在卖"+this.price+"万元");
}
var camry =new Car("凯美瑞",27);
camry.sell();
```

  #### javascript有哪些方法定义对象
```
对象字面量： var obj = {};
构造函数： var obj = new Object();
Object.create(): var obj = Object.create(Object.prototype);
```

  #### 如何判断一个对象是否属于某个类
```
第一种方式是使用 instanceof 运算符来判断构造函数的 
prototype 属性是否出现在对象的原型链中的任何位置。

第二种方式可以通过对象的 constructor 属性来判断，
对象的 constructor 属性指向该对象的构造函数，但是
这种方式不是很安全，因为 constructor 属性可以被改写。

第三种方式，如果需要判断的是某个内置的引用类型的话，
可以使用 Object.prototype.toString() 方法来打印对象的
[[Class]] 属性来进行判断。
```

  #### 如何判断一个对象是否为空对象
```js
function checkNullObj(obj) {
  return Object.keys(obj).length === 0 && Object.getOwnPropertySymbols(obj).length === 0;
}
```

  #### 怎么判断两个对象相等
```
obj={
    a:1,
    b:2
}
obj2={
    a:1,
    b:2
}
obj3={
    a:1,
    b:'2'
}
可以转换为字符串来判断

JSON.stringify(obj)==JSON.stringify(obj2);//true
JSON.stringify(obj)==JSON.stringify(obj3);//false
```

  #### js有哪些内置对象
```
js 中的内置对象主要指的是在程序执行前存在全局作用域里的
由 js 定义的一些全局值属性、函数和用来实例化其他对象的
构造函数对象。一般我们经常用到的如全局变量值 NaN、undefined，
全局函数如 parseInt()、parseFloat() 用来实例化对象的
构造函数如 Date、Object 等，还有提供数学计算的单体内置对象如 Math 对象。

Object 是 JavaScript 中所有对象的父对象
数据封装类对象：Object、Array、Boolean、Number 和 String
其他对象：Function、Arguments、Math、Date、RegExp、Error
ES6新增对象：Symbol、Map、Set、Promises、Proxy、Reflect
```

```
全局的对象（ global objects ）或称标准内置对象，
不要和 "全局对象（global object）" 混淆。这里说的全局的对象是
说在全局作用域里的对象。全局作用域中的其他对象
可以由用户的脚本创建或由宿主程序提供。

标准内置对象的分类：
（1）值属性，这些全局属性返回一个简单值，这些值没有自己的属性和方法。
例如 Infinity、NaN、undefined、null 字面量

（2）函数属性，全局函数可以直接调用，不需要在调用时指定所属对象，
执行结束后会将结果直接返回给调用者。
例如 eval()、parseFloat()、parseInt() 等

（3）基本对象，基本对象是定义或使用其他对象的基础。
基本对象包括一般对象、函数对象和错误对象。

例如 Object、Function、Boolean、Symbol、Error 等

（4）数字和日期对象，用来表示数字、日期和执行数学计算的对象。
例如 Number、Math、Date

（5）字符串，用来表示和操作字符串的对象。
例如 String、RegExp

（6）可索引的集合对象，这些对象表示按照索引值来排序的数据集合，
包括数组和类型数组，以及类数组结构的对象。例如 Array

（7）使用键的集合对象，这些集合对象在存储数据时会使用到键，
支持按照插入顺序来迭代元素。
例如 Map、Set、WeakMap、WeakSet

（8）矢量集合，SIMD 矢量集合中的数据会被组织为一个数据序列。
例如 SIMD 等

（9）结构化数据，这些对象用来表示和操作结构化的缓冲区数据，
或使用 JSON 编码的数据。
例如 JSON 等

（10）控制抽象对象
例如 Promise、Generator 等

（11）反射
例如 Reflect、Proxy

（12）国际化，为了支持多语言处理而加入 ECMAScript 的对象。
例如 Intl、Intl.Collator 等

（13）WebAssembly

（14）其他
例如 arguments

```

  #### 什么是假值对象
```
浏览器在某些特定情况下，在常规 JavaScript 语法基础上自己
创建了一些外来值，这些就是“假值对象”。假值对象看起来和
普通对象并无二致（都有属性，等等），但将它们强制类型转换
为布尔值时结果为 false 最常见的例子是 document.all，
它是一个类数组对象，包含了页面上的所有元素，由 DOM
（而不是 JavaScript 引擎）提供给 JavaScript 程序使用。
```

  #### Object.is()与原来的比较操作符“===”、“==”的区别
```
使用双等号进行相等判断时，如果两边的类型不一致，
则会进行强制类型转化后再进行比较。

使用三等号进行相等判断时，如果两边的类型不一致时，
不会做强制类型准换，直接返回 false。

使用 Object.is 来进行相等判断时，一般情况下和三等号的判断相同，
它处理了一些特殊的情况，比如 -0 和 +0 不再相等，两个 NaN 认定为是相等的。
```

```
两等号判等，会在比较时进行类型转换。
三等号判等（判断严格），比较时不进行隐式类型转换，（类型不同则会返回false）。

Object.is 在三等号判等的基础上特别处理了 NaN 、-0 和 +0 ，
保证 -0 和 +0 不再相同，但 Object.is(NaN, NaN) 会返回 true.

Object.is 应被认为有其特殊的用途，而不能用它认为它比其它的相等对比更宽松或严格。
```

- == 相等运算符，比较时会自动进行数据类型转换
- === 严格相等运算符，比较时不进行隐式类型转换
- Object.is 同值相等算法，在 === 基础上对 0 和 NaN 特别处理
```
+0 === -0 //true
NaN === NaN // false

Object.is(+0, -0) // false
Object.is(NaN, NaN) // true
```

  #### Object.assign()
```
Object.assign() 方法用于将所有可枚举属性的值从一个
或多个源对象复制到目标对象。它将返回目标对象。
```

  #### 使用Object.defineProperty()来进行数据劫持有什么缺点
```
Object.defineProperty 函数一共有三个参数，第一个参数是需要
定义属性的对象，第二个参数是需要定义的属性，第三个是该属性描述符。

一个属性的描述符有四个属性，分别是 value 属性的值，writable 属性
是否可写，enumerable 属性是否可枚举，configurable 属性是否可配置修改。
```

```
有一些对属性的操作，使用这种方法无法拦截，比如说通过下标方式
修改数组数据或者给对象新增属性，vue 内部通过重写函数解决了
这个问题。在 Vue3.0 中已经不使用这种方式了，而是通过使用 
Proxy 对对象进行代理，从而实现数据劫持。使用 Proxy 的好处是
它可以完美的监听到任何方式的数据改变，唯一的缺点是兼容性的问题，
因为这是 ES6 的语法。
```


### 数组和对象

#### 数组(array)
- map: 遍历数组，返回回调返回值组成的新数组
- forEach: 无法break，可以用try/catch中throw new Error来停止
- filter: 过滤
- some: 有一项返回true，则整体为true
- every: 有一项返回false，则整体为false
- join: 通过指定连接符生成字符串
- push / pop: 末尾推入和弹出，改变原数组， 返回推入/弹出项
- unshift / shift: 头部推入和弹出，改变原数组，返回操作项
- sort(fn) / reverse: 排序与反转，改变原数组
- concat: 连接数组，不影响原数组， 浅拷贝
- slice(start, end): 返回截断后的新数组，不改变原数组
- splice(start, number, value...): 返回删除元素组成的数组，value为插入项，改变原数组
- indexOf / lastIndexOf(value, fromIndex): 查找数组项，返回对应的下标
- reduce / reduceRight(fn(prev, cur)， defaultPrev): 两两执行，prev 为上次化简函数的return值，cur为当前值(从第二项开始)

数组乱序：
```
var arr = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
arr.sort(function () {
    return Math.random() - 0.5;
});
```
数组拆解: flat: [1,[2,3]] --> [1, 2, 3]
```
Array.prototype.flat = function() {
    this.toString().split(',').map(item => +item )
}
```

  #### 数组常用方法
- Array.isArray()
```
此方法用于判断传入值是否为一个数组，代码如下：

var arr = [1,2];
var obj = {name : 'eric'};
var num = 100;
console.log(    
	Array.isArray(arr),   //true    
	Array.isArray(obj),   //false     
	Array.isArray(num)    //false
)
```

- Array.of()
```
此方法返回一个传入参数组成的数组，代码如下：

var arr = Array.of(1,2,3);
console.log(arr);//[ 1, 2, 3 ]
```

- Array.from()
```
此方法将一个数组对象转化为一个数组，不改变原数组，代码如下：

var arr = [1,2,3,4,5,1,2];
var set = new Set(arr);  //Set(5) { 1, 2, 3, 4, 5 }
var arr2 = Array.from(set);
console.log(arr2); //[ 1, 2, 3, 4, 5 ]
```

- pop()
```
此方法删除数组最后一个元素，改变原数组，返回被删除的元素，代码如下：

var arr = [1,2,3];
console.log(    
	arr.pop() //3
)
console.log(arr) //[1,2]
```

- shift()
```
此方法删除数组第一个元素，改变原数组，返回被删除的元素，代码如下：

var arr = [1,2,3];
console.log(    
	arr.shift() //1
)
console.log(arr) //[2,3]
```

- push()
```
此方法向数组末尾添加一个元素，改变原数组，
返回添加后数组的length，代码如下：

var arr = ['a', 'b'];
console.log(    
	arr.push('c') //3
)
console.log(arr) //[ 'a', 'b', 'c' ]
```

- unshift()
```
此方法向数组开头添加一个元素，改变原数组，
返回添加后数组的length，代码如下：

var arr = ['a', 'b'];
console.log(    
	arr.unshift('c') //3
)
console.log(arr) //[ 'c', 'a', 'b' ]
```

- reverse()
```
此方法会反转一个数组，改变原数组，返回反转后的数组，代码如下：

var arr = ['a', 'b' , 'c'];
console.log(    
	arr.reverse() //[ 'c', 'b', 'a' ]
)
console.log(arr) //[ 'c', 'b', 'a' ]
```

- splice()
```
此方法接收三个参数，参数作用如下：

1.第一个参数(必填)：选中数组中某一个位置，可以为负数，
  负数从数组最后一项算起
3.第二个参数(选填)：规定要删除的长度，可以为0
4.第三个参数(选填)：规定插入的元素
5.第四(n)个参数(选填)：规定插入的元素

下面是具体操作，代码如下：
var arr = [1,2,3];
console.log(    
	arr.splice(0,2)//[ 1, 2 ]
)
console.log(arr);//[3]
上述代码中第一个参数选中数组第0项的位置，第二个参数设定截取长度为2，
调用此方法返回被截取的数组，同时改变原数组。

var arr = [1,2,3];
console.log(    
	arr.splice(0,2,10,11)//[ 1, 2 ]
)
console.log(arr);//[ 10, 11, 3 ]
上述代码中第一个参数选中数组第0项位置，第二个参数设定截取长度为2，
第三个参数以及第三个参数以后代表要添加的元素，调用此方法，
返回被截取的数组，同时改变原数组，原数组再被截取之后在选中
的第0项的位置又新添加了第三个参数和第三个参数后边的参数。
```

- slice()
```
此方法用来复制数组中某一部分的元素，不改变原数组，
此方法参数作用如下：

第一个参数：复制的位置
第二个参数：复制的长度

代码如下：
var arr = [1,2,3,4];
console.log(    
	arr.slice(0,3) //[ 1, 2, 3 ]
)
console.log(arr); //[ 1, 2, 3, 4 ]
上述代码中复制起始位置为数组第0项，复制长度为3，
即复制123这三个元素。同时不改变原数组。
```

- sort()
```
此方法将数组进行排序，改变原数组。接收一个非必填参数，
此参数代表排序的规则，代码如下：

var arr = [8, 9, 2, 1, 6, 4, 0];
console.log(    
	arr.sort() //[0,1,2,4,6,8,9]
)
console.log(    
	arr.sort(function (a, b) {        
		return b - a // [9,8,6,4,2,1,0]    
	})
)
上述代码中如果没有给sort函数传递参数，则默认为升序排序，
如果传递参数即传递上述所示的函数，此函数中return b-a，
即代表降序排序，相应的如果return a-b则为升序排序。
```

- copyWithin()
```
此方法会将数组中某一个位置的数组进行复制并且在
某一个位置进行粘贴，比较难理解，先上代码：
var arr = [1,2,3,4,5];
console.log(    
	arr.copyWithin(2,0,3)//[ 1, 2, 1, 2, 3 ]
)
console.log(arr)//[ 1, 2, 1, 2, 3 ]

在此方法中接收了三个参数，先介绍一下三个参数的用途：
第一个参数：代表要粘贴的起始位置
第二个参数：复制的起始位置
第三个参数：复制的截至位置(不包含截至位置的值)即左闭右开区间

知道了参数的作用，我们来说明一下上述代码的意思。规定一个数组arr，
然后调用copyWithin方法，传入第一个参数粘贴位置为2，传入第二参数
复制起始位置0，传入第三个参数复制截至位置3，于是复制的值为1，2，
将这两个值粘贴到原数组的第二项，此时第二项位置又值，则覆盖这些值，
即3，4被覆盖。调用此方法后返回改变后的数组，同时原数组也会被改变。
```

- fill()
```
//样例1
var arr = [1,2,3];
console.log(    
	arr.fill(4) //[ 4, 4, 4 ]
)
console.log(arr) //[ 4, 4, 4 ]

//样例2
var arr2 = [1,2,3,4];
console.log(    
	arr2.fill(0,1,2) //[ 1, 0, 3, 4 ]
)
console.log(arr2) //[ 1, 0, 3, 4 ]

先来了解一下fill函数的参数：
第一个参数(必选)：用来覆盖的值
第二个参数(可选)：覆盖的起始位置  左闭右开
第三个参数(可选)：覆盖的结束位置  左闭右开

上述代码中，样例1：原数组有值，通过fill方法传入一个用来覆盖的值，
这个值会将数组中所有元素用自己覆盖。样例2：原数组有值，
fill方法传入第一个参数0代表用来覆盖的值，传入第二个值代表覆盖的
起始位置为1，传入第三个值代表覆盖的结束位置2，这个区间左闭右开，
于是得到上述中的结果。
```

- join()
```
此方法会根据所传递参数连接数组中每一个元素，
返回连接好的字符串，代码如下：

var arr = [1,2,3,4];
console.log(    
	//不传入参数    
	arr.join() //1,2,3,4
)
console.log(    
	//传入一个&符号用于连接    
	arr.join('&') //1&2&3&4
)
console.log(    
	arr //[ 1, 2, 3, 4 ]
)
上述代码中，如果不传递参数给join，则默认用逗号连接，
如果传递参数为任意值，则以这个任意值连接，不改变原数组。
```

- concat()
```
此方法可以将数组和某一个值进行连接，也可以连接一个或者
多个数组，不改变原数组，代码如下：

var arr = [1,2,3,4];
console.log(    
	arr.concat(5)//[ 1, 2, 3, 4, 5 ]
)
console.log(   
	arr.concat([6,7])//[ 1, 2, 3, 4, 6, 7 ]
)
console.log(    
	arr.concat([8,9],[10])//[1, 2,  3, 4,8, 9, 10]
)
console.log(arr)//[ 1, 2, 3, 4 ]
```

- toString()

此方法可以将一个一维或者多维数组转化为字符串，
不改变原数组，代码如下：

var arr = [1,2,3,4]; 
var arr1 = [1,2,[    
	3,4],    
	[5,6],    
	7
]
console.log(    
	arr.toString() //1,2,3,4
)
console.log(    
	arr1.toString() //1,2,3,4,5,6,7
)

- indexOf()
```
此方法用来查找数组中某一项的下标值，从左往右查找，
不改变原数组，代码如下：
var arr = [1,2,3,4]; 
console.log(    
	arr.indexOf(2) //1
)
```

- lastIndexOf()
```
此方法也是用来查找数组中某一项的下标值，从右往左查找，
不改变原数组，代码如下：

var arr = [1,2,3,4,2,8];
console.log(   
	arr.lastIndexOf(2) //4
)
```

- includes()
```
此方法用来查找数组中某一项是否存在，返回true或者false，代码如下：

var arr = [1,2,3,4]; 
console.log(    
	arr.includes(2) //true
)
```

- forEach()
```
此方法用来遍历数组，接受的参数如下：
第一个参数(必选)：便利的每一项的值
第二个参数(可选)：遍历的每一项的下标值
第三个参数(可选)：被遍历的数组
第四个参数(可选)：执行回调函数时的this代码如下：

var arr = [1,2,3,4]; 
arr.forEach((item,index)=>{    
	console.log(item)}
)//1//2//3//4
```

- some()
```
此方法用来查找数组中是否含有满足条件的值，即要遍历数组，
如果有符合条件的值，则返回true，否则为false，代码如下：

var arr = [1,2,3,4]; 
console.log(    
	arr.some((item,index)=>{        
		return item > 3    
	})
)//true
```

- every()
```
此方法用来检测数组中的元素是否全部满足条件，代码如下 ：

var arr = [1,2,3,4]; 
console.log(    
	arr.every((item)=>{        
		return item > 2    
	})
)//false
上述代码中遍历所有数组元素，判断数组元素是否都大于2，
如果是返回true，如果不是返回false
```

- filter()
```
此方法用来筛选数组中的元素，符合筛选条件的元素会被返回，
组成新的数组，不改变原数组，代码如下：

var arr = [1,2,3,4]; 
console.log(     
	arr.filter((item)=>{        
		return item>2   //[ 3, 4 ]    
	})
)
console.log(arr) //[ 1, 2, 3, 4 ]
```

- map()
```
此方法可以用来处理数组中每一个元素，并且返回新数组，
不改变原数组，代码如下：

var arr = [1,2,3,4]; 
console.log(     
	arr.map((item)=>{        
		return item*2   [ 2, 4, 6, 8 ]    
	})
)
console.log(arr) //[ 1, 2, 3, 4 ]
```

- reduce()
```
此方法可以称为数组的累加器，具体接收参数如下：

第一个参数：per，如果规定了第五个参数，则per为第五个参数的值，
如果没有规定第五个参数，则为数组中第一项

第二个参数：item，如果per为数组第一项，则item为数组第二项，
如果per为规定的第五个参数值，则item为数组第一项

第三个参数：item的索引值
第四个参数：原数组
第五个参数：初始值

此方法比较难理解，我们用代码慢慢来解释：
var arr = [1,2,3,4];//没有初始值的情况 
arr.reduce((pre,item,index,arr)=>{    
	console.log(pre) //1 2 3    
	console.log(item) //2 3 4     
	console.log(index) //1 2 3    
	return item
})
在没有传递初始值的情况下，pre第一次为数组的第0项值1，
item则为数组第1项值2，index为item的下标值1.然后return item，
这个return的值会作为pre下一次循环的值，即第二轮循环pre值为2，
item值为数组第2项值3，index为item下标值2，此时继续返回item。
第三轮循环pre值为3，item值为数组第三项值4，index值为item下标值3。
循环结束。

var arr = [1,2,3,4];
//传递初始值 
arr.reduce((pre,item,index,arr)=>{    
	console.log(pre) // [] 1 2 3    
	console.log(item) // 1 2 3 4    
	console.log(index) // 0 1 2 3    
	return item
},[])
在传递了初始值的情况下，pre即为初始值[]，
其他部分逻辑跟之前的逻辑一样，大家可以自行梳理。
```

- flat()
```
此方法会深度遍历并且展开数组，接收可选参数，
可选参数的值为区间1到无穷。常用于展开多维数组，如下边代码：

var arr = [1, [2, 3], [[4, 5], 6], [7, 8]]
console.log(    
	arr.flat() //[ 1, 2, 3, [ 4, 5 ], 6, 7, 8 ]
)
console.log(   
	arr.flat(Infinity) //[1, 2, 3, 4, 5, 6, 7, 8]
)
上述代码中如果不给flat传递参数，默认参数值为1，
即展开一层的数组，如上述代码，展开一层之后，数组返回值如上。
如果要展开多维数组，但是你也不知道是几维(就是懒得数了)，
就直接传递Infinity，不管有几维都统统展开。
```

  #### 如何实现数组的随机排序
```js
// （1）使用数组 sort 方法对数组元素随机排序，让 Math.random() 
出来的数与 0.5 比较，如果大于就返回 1 交换位置，
如果小于就返回 -1，不交换位置。

function randomSort(a, b) {
  return Math.random() > 0.5 ? -1 : 1;
}

//  缺点：每个元素被派到新数组的位置不是随机的，
原因是 sort() 方法是依次比较的。

// （2）随机从原数组抽取一个元素，加入到新数组

function randomSort(arr) {
  var result = [];

  while (arr.length > 0) {
    var randomIndex = Math.floor(Math.random() * arr.length);
    result.push(arr[randomIndex]);
    arr.splice(randomIndex, 1);
  }

  return result;
}

// （3）随机交换数组内的元素（洗牌算法类似）

function randomSort(arr) {
  var index,
    randomIndex,
    temp,
    len = arr.length;

  for (index = 0; index < len; index++) {
    randomIndex = Math.floor(Math.random() * (len - index)) + index;

    temp = arr[index];
    arr[index] = arr[randomIndex];
    arr[randomIndex] = temp;
  }

  return arr;
}

// es6
function randomSort(array) {
  let length = array.length;

  if (!Array.isArray(array) || length <= 1) return;

  for (let index = 0; index < length - 1; index++) {
    let randomIndex = Math.floor(Math.random() * (length - index)) + index;

    [array[index], array[randomIndex]] = [array[randomIndex], array[index]];
  }

  return array;
}
```

  #### 快速的让一个数组乱序
```
var arr = [1,2,3,4,5,6,7,8,9,10];
arr.sort(function(){
    return Math.random() - 0.5;
})
console.log(arr);
```

  #### 数组去重方法总结
```
(1)方法一、利用ES6 Set去重（ES6中最常用）
function unique (arr) {
  return Array.from(new Set(arr))
}
var arr = [1,1,'true','true',true,true,15,15,false,false, undefined,undefined, null,null, NaN, NaN,'NaN', 0, 0, 'a', 'a',{},{}];
console.log(unique(arr))
 //[1, "true", true, 15, false, undefined, null, NaN, "NaN", 0, "a", {}, {}]
 
(2)方法二、利用for嵌套for，然后splice去重（ES5中最常用）
function unique(arr){            
        for(var i=0; i<arr.length; i++){
            for(var j=i+1; j<arr.length; j++){
                if(arr[i]==arr[j]){         //第一个等同于第二个，splice方法删除第二个
                    arr.splice(j,1);
                    j--;
                }
            }
        }
	return arr;
}
var arr = [1,1,'true','true',true,true,15,15,false,false, undefined,undefined, null,null, NaN, NaN,'NaN', 0, 0, 'a', 'a',{},{}];
console.log(unique(arr))
    //[1, "true", 15, false, undefined, NaN, NaN, "NaN", "a", {…}, {…}]     //NaN和{}没有去重，两个null直接消失了
双层循环，外层循环元素，内层循环时比较值。值相同时，则删去这个值。

(3)方法三、利用indexOf去重
function unique(arr) {
    if (!Array.isArray(arr)) {
        console.log('type error!')
        return
    }
    var array = [];
    for (var i = 0; i < arr.length; i++) {
        if (array .indexOf(arr[i]) === -1) {
            array .push(arr[i])
        }
    }
    return array;
}
var arr = [1,1,'true','true',true,true,15,15,false,false, undefined,undefined, null,null, NaN, NaN,'NaN', 0, 0, 'a', 'a',{},{}];
console.log(unique(arr))
   // [1, "true", true, 15, false, undefined, null, NaN, NaN, "NaN", 0, "a", {…}, {…}]  //NaN、{}没有去重
新建一个空的结果数组，for 循环原数组，判断结果数组是否
存在当前元素，如果有相同的值则跳过，不相同则push进数组

(4)方法四、利用sort()
function unique(arr) {
    if (!Array.isArray(arr)) {
        console.log('type error!')
        return;
    }
    arr = arr.sort()
    var arrry= [arr[0]];
    for (var i = 1; i < arr.length; i++) {
        if (arr[i] !== arr[i-1]) {
            arrry.push(arr[i]);
        }
    }
    return arrry;
}
var arr = [1,1,'true','true',true,true,15,15,false,false, undefined,undefined, null,null, NaN, NaN,'NaN', 0, 0, 'a', 'a',{},{}];
console.log(unique(arr))
// [0, 1, 15, "NaN", NaN, NaN, {…}, {…}, "a", false, null, true, "true", undefined]      //NaN、{}没有去重
利用sort()排序方法，然后根据排序后的结果进行遍历及相邻元素比对

(5)方法五、利用对象的属性不能相同的特点进行去重
function unique(arr) {
    if (!Array.isArray(arr)) {
        console.log('type error!')
        return
    }
    var arrry= [];
     var  obj = {};
    for (var i = 0; i < arr.length; i++) {
        if (!obj[arr[i]]) {
            arrry.push(arr[i])
            obj[arr[i]] = 1
        } else {
            obj[arr[i]]++
        }
    }
    return arrry;
}
var arr = [1,1,'true','true',true,true,15,15,false,false, undefined,undefined, null,null, NaN, NaN,'NaN', 0, 0, 'a', 'a',{},{}];
console.log(unique(arr))
//[1, "true", 15, false, undefined, null, NaN, 0, "a", {…}]    //两个true直接去掉了，NaN和{}去重

(6)方法六、利用includes
function unique(arr) {
    if (!Array.isArray(arr)) {
        console.log('type error!')
        return
    }
    var array =[];
    for(var i = 0; i < arr.length; i++) {
            if( !array.includes( arr[i]) ) {//includes 检测数组是否有某个值
                    array.push(arr[i]);
              }
    }
    return array
}
var arr = [1,1,'true','true',true,true,15,15,false,false, undefined,undefined, null,null, NaN, NaN,'NaN', 0, 0, 'a', 'a',{},{}];
console.log(unique(arr))
    //[1, "true", true, 15, false, undefined, null, NaN, "NaN", 0, "a", {…}, {…}]     //{}没有去重

(7)方法七、利用hasOwnProperty
function unique(arr) {
    var obj = {};
    return arr.filter(function(item, index, arr){
        return obj.hasOwnProperty(typeof item + item) ? false : (obj[typeof item + item] = true)
    })
}
    var arr = [1,1,'true','true',true,true,15,15,false,false, undefined,undefined, null,null, NaN, NaN,'NaN', 0, 0, 'a', 'a',{},{}];
        console.log(unique(arr))
//[1, "true", true, 15, false, undefined, null, NaN, "NaN", 0, "a", {…}]   //所有的都去重了
利用hasOwnProperty 判断是否存在对象属性

(8)方法八、利用filter
function unique(arr) {
  return arr.filter(function(item, index, arr) {
    //当前元素，在原始数组中的第一个索引==当前索引值，否则返回当前元素
    return arr.indexOf(item, 0) === index;
  });
}
var arr = [1,1,'true','true',true,true,15,15,false,false, undefined,undefined, null,null, NaN, NaN,'NaN', 0, 0, 'a', 'a',{},{}];
console.log(unique(arr))
//[1, "true", true, 15, false, undefined, null, "NaN", 0, "a", {…}, {…}]

(9)方法九、利用递归去重
function unique(arr) {
    var array= arr;
    var len = array.length;

	array.sort(function(a,b){   //排序后更加方便去重
		return a - b;
	})

	function loop(index){
        if(index >= 1){
            if(array[index] === array[index-1]){
            array.splice(index,1);
            }
            loop(index - 1);    //递归loop，然后数组去重
        }
	}
	loop(len-1);
	return array;
}
var arr = [1,1,'true','true',true,true,15,15,false,false, undefined,undefined, null,null, NaN, NaN,'NaN', 0, 0, 'a', 'a',{},{}];
console.log(unique(arr))
//[1, "a", "true", true, 15, false, 1, {…}, null, NaN, NaN, "NaN", 0, "a", {…}, undefined]

(10)方法十、利用Map数据结构去重
function arrayNonRepeatfy(arr) {
	let map = new Map();
		let array = new Array();  // 数组用于返回结果
		for (let i = 0; i < arr.length; i++) {
			if(map .has(arr[i])) {  // 如果有该key值
			map .set(arr[i], true);
		} else {
			map .set(arr[i], false);   // 如果没有该key值
			array .push(arr[i]);
		}
	}
	return array ;
}
 var arr = [1,1,'true','true',true,true,15,15,false,false, undefined,undefined, null,null, NaN, NaN,'NaN', 0, 0, 'a', 'a',{},{}];
    console.log(unique(arr))
//[1, "a", "true", true, 15, false, 1, {…}, null, NaN, NaN, "NaN", 0, "a", {…}, undefined]
创建一个空Map数据结构，遍历需要去重的数组，把数组的每一个
元素作为key存到Map中。由于Map中不会出现相同的key值，
所以最终得到的就是去重后的结果

(11)方法十一、利用reduce+includes
function unique(arr){
    return arr.reduce((prev,cur) => prev.includes(cur) ? prev : [...prev,cur],[]);
}
var arr = [1,1,'true','true',true,true,15,15,false,false, undefined,undefined, null,null, NaN, NaN,'NaN', 0, 0, 'a', 'a',{},{}];
console.log(unique(arr));
// [1, "true", true, 15, false, undefined, null, NaN, "NaN", 0, "a", {…}, {…}]

(12)方法十二、[...new Set(arr)]
[...new Set(arr)]
//代码就是这么少----（其实，严格来说并不算是一种，相对于第一种方法来说只是简化了代码）
```

  #### 数组扁平化
数组扁平化即将多维数组转化为一维数组，如下例所示：
```
//多维数组var arr = [
	[1, 2],    
	[3, 4],    
	[        
		[5,6],        
		[7,8]    
	],    
	9
]
//转化为一维数组结果[1,2,3,4,5,6,7,8,9]
```

- reduce实现
```
var arr = [    
	[1, 2],    
	[3, 4],    
	[        
		[5,6],        
		[7,8]    
	],   
	9
]
function flatten(arr) {     
	return arr.reduce((result, item)=> {        
		return result.concat(Array.isArray(item) ? flatten(item) : item);    
	}, []);
}
console.log(    
	flatten(arr)
)

上述代码中实现了一个扁平化方法，方法内部返回使用reduce方法处理后的
扁平化数组。原理如下：使用reduce方法遍历数组，result初始值为[ ]，
使用Array.isArray方法判断当前item是否为数组，如果不是数组则将item
跟result连接，如果item是数组，则将item传入flatten方法中进行递归。
本题涉及reduce方法和concat方法以及递归的概念，解题之前请了解这些内容。
```

- toString&split
```
将一个多维数组通过toString转化为字符串(可以自行打印预览，
结果惊呆你)，之后调用split方法将字符串分割为数组，
最后将分割好的数组转化格式即可，代码如下：

var arr = [    
	[1, 2],    
	[3, 4],    
	[        
		[5,6],        
		[7,8]    
	],    
	9
]
这个就行’多维也行
function flatten(arr) {    
	console.log(arr.toString())    
	return arr.toString().split(',').map(function(item) {        
		return Number(item);    
	})
} 
console.log(    
	flatten(arr)
)
```

- join & split
```
此方法和上述方法原理类似，通过join将数组转化为字符串，
再用split转化为数组即可，代码如下：

var arr = [    
	[1, 2],    
	[3, 4],    
	[        
		[5,6],        
		[7,8]    
	],    
	9
]
function flatten(arr) {    
	return arr.join(',').split(',').map(function(item) {        
		return parseInt(item);    
	})
}
console.log(    
	flatten(arr)
)
```

- 递归
```
这种方法是reduce的更好理解版本，原理和reduce实现的原理一样，代码如下：
var arr = [    
	[1, 2],    
	[3, 4],    
	[        
		[5,6],        
		[7,8]    
	],    
	9
]
function flatten(arr) {    
	var res = [];    
	arr.map(item => {        
		if(Array.isArray(item)) {            
			res = res.concat(flatten(item));        
		} else {            
			res.push(item);        
		}    
	});    
	return res;
}
console.log(    
	flatten(arr)
)
```

```
首先让我们思考一个这样的题目；假如有一个数组 var arr = [1, [2, 3, [4]]] ，
我们怎么能把arr变成[1, 2, 3, 4]呢？即让多维数组降维，
转换为只有一层的数组；如果用过lodash的话，
我们知道 flatten 和 flattenDeep 方法都可以实现.

flatten用法：

概念：可以理解为将嵌套数组的维数减少，flattened（平坦）. 
如果 isDeep 值为 true 时，嵌套数组将递归为一维数组, 
否则只减少嵌套数组一个级别的维数.

代码如下：
参数： array (Array): 需要flattened（减少维数）的嵌套数组
[isDeep] (boolean): 是否深递归

返回值： (Array): 返回处理后的数组

// using `isDeep`
_.flatten([1, [2, 3, [4]]], true);
// => [1, 2, 3, 4]

flattenDeep用法：
概念：递归地平坦一个嵌套的数组.相当于_.flatten(array, true)
**参数：**array (Array): 需要

返回值：(Array): 返回处理后的数组.

flattenDeep: 递归地平坦一个嵌套的数组.相当于_.flatten(array, true).
_.flattenDeep([1, [2, 3, [4]]]);
// => [1, 2, 3, 4]

那么如果我们自己写该如何实现呢？下面列举几种实现方式：

1. 循环数组+递归
实现思路：循环数组，如果数据中还有数组的话，
递归调用flatten扁平函数（利用for循环扁平），
用concat连接，最终返回result;

 function flatten(arr){
     var result = [];
     for(var i = 0, len = arr.length; i < len; i++){
         if(Array.isArray(arr[i])){
             result = result.concat(flatten(arr[i]));
         }else{
             result.push(arr[i]);
         }
     }
     return result;
 }

flatten(arr)   // [1,2,3,4]

2. 利用apply
可以使用apply的原因如下：

var arr = [1, [2, 3, [4]]];
[].concat.apply([],arr);
// [1,2,3,[4]]

实现思路：利用arr.some判断当数组中还有数组的话，
递归调用flatten扁平函数(利用apply扁平), 用concat连接，最终返回arr;

 function flatten(arr){
    while(arr.some(item => Array.isArray(item))){
          arr =  [].concat.apply([],arr);
    }
    return arr;
}

flatten(arr)   // [1,2,3,4]

3. reduce方法
reduce() 方法对累加器和数组中的每个元素（从左到右）
应用一个函数，将其减少为单个值。
能使用reduce原因如下：

var flattened = arr.reduce(function(prev, cur){
    return prev.concat(cur)
},[])

console.log(flattened);
//  [1,2,3,[4]]

实现思路：使用reduce, 当数组中还有数组的话，递归调用
flatten扁平函数(利用reduce扁平), 用concat连接，
最终返回arr.reduce的返回值;

function flatten(arr){
    return arr.reduce(function(prev, cur){
        return prev.concat(Array.isArray(cur) ? flatten(cur) : cur)
    },[])
}

flatten(arr)   // [1,2,3,4]

4. es6 展开运算符
可以使用es6 展开运算符的原因如下：

var arr = [1, [2, 3, [4]]];

console.log(...arr);
// 1,[2,3,[4]]

实现思路：利用arr.some判断当数组中还有数组的话，
递归调用flatten扁平函数(利用es6展开运算符扁平),
用concat连接，最终返回arr;

function flatten(arr){
  while(arr.some(item => Array.isArray(item))){
      arr = [].concat(...arr);
  }
  return arr;
}

flatten(arr)   // [1,2,3,4]

5. toString方法（数组元素为数字）
如果数组的元素是数字，那么我们可以考虑toString()方法，
其他情况不适用。原因如下：

[1, [2, 3, [4]]].toString()
// "1,2,3,4"

实现思路：数组适用toString()方法后变成以逗号分割的字符串，
然后map遍历数组把每一项再变回整数并返回map后的结果。

function flatten(arr){
    return arr.toString().split(',').map(function(item){
         return parseInt(item);
     })
}    

flatten(arr)   // [1,2,3,4]
```

#### JS中flat---数组扁平化
- 对于前端项目开发过程中，偶尔会出现层叠数据结构的数组，我们需要将多层级数组转化为一级数组（即提取嵌套数组元素最终合并为一个数组），使其内容合并且展开。那么该如何去实现呢？

需求:多维数组=>一维数组
```
let ary = [1, [2, [3, [4, 5]]], 6];// -> [1, 2, 3, 4, 5, 6]
let str = JSON.stringify(ary);
```

调用ES6中的flat方法
```
ary = ary.flat(Infinity);
```

replace + split
```
ary = str.replace(/(\[|\])/g, '').split(',')
```

replace + JSON.parse
```
str = str.replace(/(\[|\])/g, '');
str = '[' + str + ']';
ary = JSON.parse(str);
```

普通递归
```
let result = [];
let fn = function(ary) {
  for(let i = 0; i < ary.length; i++) {
    let item = ary[i];
    if (Array.isArray(ary[i])){
      fn(item);
    } else {
      result.push(item);
    }
  }
}
```

利用reduce函数迭代
```
function flatten(ary) {
    return ary.reduce((pre, cur) => {
        return pre.concat(Array.isArray(cur) ? flatten(cur) : cur);
    }, []);
}
let ary = [1, 2, [3, 4], [5, [6, 7]]]
console.log(flatten(ary))
```

扩展运算符
```
//只要有一个元素有数组，那么循环继续
while (ary.some(Array.isArray)) {
  ary = [].concat(...ary);
}
```

  #### 判断是否是数组
```
Array.isArray(arr
Object.prototype.toString.call(arr) === '[Object Array]'
arr instanceof Array
array.constructor === Array
```

  #### 数组的fill方法
```
fill() 方法用一个固定值填充一个数组中从起始索引到
终止索引内的全部元素。不包括终止索引。

fill 方法接受三个参数 value，start 以及 end，start 和 end 
参数是可选的，其默认值分别为 0 和 this 对象的 length 属性值。
```

  #### 数组和对象有哪些原生方法
```
数组和字符串的转换方法：toString()、toLocalString()、join() 
其中 join() 方法可以指定转换为字符串时的分隔符。

数组尾部操作的方法 pop() 和 push()，push 方法可以传入多个参数。

数组首部操作的方法 shift() 和 unshift() 重排序的方法 reverse() 
和 sort()，sort() 方法可以传入一个函数来进行比较，
传入前后两个值，如果返回值为正数，则交换两个参数的位置。

数组连接的方法 concat() ，返回的是拼接好的数组，不影响原数组。

数组截取办法 slice()，用于截取数组中的一部分返回，不影响原数组。

数组插入方法 splice()，影响原数组查找特定项的索引的方法，indexOf() 和 
lastIndexOf() 迭代方法 every()、some()、filter()、map() 和 forEach() 方法

数组归并方法 reduce() 和 reduceRight() 方法
```

  #### JS数组和对象的遍历方式，以及几种方式的比较
```
通常我们会用循环的方式来遍历数组。但是循环是 导致js 性能
问题的原因之一。一般我们会采用下几种方式来进行数组的遍历：

(1)for in循环
for-in需要分析出array的每个属性，这个操作性能开销很大。
用在 key 已知的数组上是非常不划算的。所以尽量不要用for-in，
除非你不清楚要处理哪些属性，例如 JSON对象这样的情况

(2)for循环
循环每进行一次，就要检查一下数组长度。读取属性（数组长度）要比
读局部变量慢，尤其是当 array 里存放的都是 DOM 元素，
因为每次读取都会扫描一遍页面上的选择器相关元素，速度会大大降低

(3)forEach
这里的 forEach回调中两个参数分别为 value，index
forEach 无法遍历对象
IE不支持该方法；Firefox 和 chrome 支持
forEach 无法使用 break，continue 跳出循环，
且使用 return 是跳过本次循环
```

  #### JavaScript类数组对象的定义
```
一个拥有 length 属性和若干索引属性的对象就可以被称为
类数组对象，类数组对象和数组类似，但是不能调用数组的方法。

常见的类数组对象有 arguments 和 DOM 方法的返回结果，
还有一个函数也可以被看作是类数组对象，因为它含有 
length属性值，代表可接收的参数个数。
```

常见的类数组转换为数组的方法有这样几种：
（1）通过 call 调用数组的 slice 方法来实现转换
```js
Array.prototype.slice.call(arrayLike);
```

（2）通过 call 调用数组的 splice 方法来实现转换
```js
Array.prototype.splice.call(arrayLike, 0);
```

（3）通过 apply 调用数组的 concat 方法来实现转换
```js
Array.prototype.concat.apply([], arrayLike);
```

（4）通过 Array.from 方法来实现转换
```js
Array.from(arrayLike);
```

  #### Array构造函数只有一个参数值时的表现
```
Array 构造函数只带一个数字参数的时候，该参数会被作为
数组的预设长度（length），而非只充当数组中的一个元素。这样
创建出来的只是一个空数组，只不过它的 length 属性被设置成了指定的值。

构造函数 Array(..) 不要求必须带 new 关键字。不带时，它会被自动补上。
```

  #### Array.splice()与Array.splice()的区别
```
slice
“读取”数组指定的元素，不会对原数组进行修改

语法：arr.slice(start, end)
start 指定选取开始位置（含）
end 指定选取结束位置（不含）

splice
“操作”数组指定的元素，会修改原数组，返回被删除的元素

语法：arr.splice(index, count, [insert Elements])
index 是操作的起始位置
count = 0 插入元素，count > 0 删除元素
[insert Elements] 向数组新插入的元素
```

  #### [].forEach.call(\$\$("<em>"),function(a){a.style.outline="1px solid#"(~~(Math.random()</em>(1&lt;&lt;24))).toString(16)})能解释一下这段代码的意思吗
```
（1）选取页面所有 DOM 元素。在浏览器的控制台中可以使用$$()方法
来获取页面中相应的元素，这是现代浏览器提供的一个命令行 API 
相当于 document.querySelectorAll 方法。

（2）循环遍历 DOM 元素

（3）给元素添加 outline 。由于渲染的 outline 是不在 CSS 盒模型
中的，所以为元素添加 outline 并不会影响元素的大小和页面的布局。

（4）生成随机颜色函数。Math.random()*(1<<24) 可以得到 0~2^24 - 1 
之间的随机数，因为得到的是一个浮点数，但我们只需要整数部分，
使用取反操作符 ~ 连续两次取反获得整数部分，
然后再用 toString(16) 的方式，转换为一个十六进制的字符串。
```

```
  [].forEach.call($$("*"), function(el){
      el.style.outline = "1px solid #" + (~~(Math.random()*(1<<24))).toString(16);
  })
解释：获取页面所有的元素，遍历这些元素，
为它们添加1像素随机颜色的轮廓(outline)
(1)$$(sel) // $$函数被许多现代浏览器命令行支持，
等价于 document.querySelectorAll(sel)
(2)[].forEach.call(NodeLists) // 使用 call 函数
将数组遍历函数 forEach 应到节点元素列表
(3)el.style.outline = "1px solid #333" // 
样式 outline 位于盒模型之外，不影响元素布局位置
(4)(1<<24) // parseInt("ffffff", 16) == 16777215 == 2^24 - 1 // 1<<24 == 2^24 == 16777216
(5)Math.random()*(1<<24) // 表示一个位于 0 到 
16777216 之间的随机浮点数
(6)~~Math.random()*(1<<24) // ~~ 作用相当于 parseInt 取整
(7)(~~(Math.random()*(1<<24))).toString(16) 
// 转换为一个十六进制
```

  #### ["1","2","3"].map(parseInt)答案是多少
```
parseInt() 函数能解析一个字符串，并返回一个整数，需要两个参数
(val, radix)，其中 radix 表示要解析的数字的基数。（该值介于 2 ~ 36 
之间，并且字符串中的数字不能大于 radix 才能正确返回数字结果值）。


此处 map 传了 3 个参数 (element, index, array)，默认第三个参数
被忽略掉，因此三次传入的参数分别为 "1-0", "2-1", "3-2"

因为字符串的值不能大于基数，因此后面两次调用均失败，
返回 NaN ，第一次基数为 0 ，按十进制解析返回 1。
```

```
[1, NaN, NaN]因为 parseInt 需要两个参数 (val, radix)，
其中radix 表示解析时用的基数。
map传了 3个(element, index, array)，对应的 radix 不合法导致解析失败。
```

  #### map与forEach的区别
```
forEach方法，是最基本的方法，就是遍历与循环，默认有3个传参：
分别是遍历的数组内容item、数组索引index、和当前遍历数组Array map方法，
基本用法与forEach一致，但是不同的，它会返回一个新的数组，
所以在callback需要有return值，如果没有，会返回undefined
```

  #### Map和WeakMap结构
```
1.Map 数据结构。它类似于对象，也是键值对的集合，但是“键”的
范围不限于字符串，各种类型的值（包括对象）都可以当作键。
2.WeakMap 结构与 Map 结构类似，也是用于生成键值对的集合。
但是 WeakMap 只接受对象作为键名（ null 除外），
不接受其他类型的值作为键名。
而且 WeakMap 的键名所指向的对象，不计入垃圾回收机制。
```

  #### Set和WeakSet结构
```
1.ES6 提供了新的数据结构 Set。它类似于数组，
但是成员的值都是唯一的，没有重复的值。
2.WeakSet 结构与 Set 类似，也是不重复的值的集合。但是 
WeakSet 的成员只能是对象，而不能是其他类型的值。WeakSet 
中的对象都是弱引用，即垃圾回收机制不考虑 WeakSet 对该对象的引用，
```

  #### {}和[]的valueOf和toString的结果是什么
```
{} 的 valueOf 结果为 {} ，toString 的结果为 "[object Object]"

[] 的 valueOf 结果为 [] ，toString 的结果为 ""
```

#### 如何转化类数组成数组
```
因为arguments本身并不能调用数组方法，它是一个另外一种对象类型，
只不过属性从0开始排，依次为0，1，2...最后还有callee和length属性。
我们也把这样的对象称为类数组
```

常见的类数组还有：
- 用getElementsByTagName/ClassName()获得的HTMLCollection
- 用querySelector获得的nodeList
```
那这导致很多数组的方法就不能用了，必要时需要我们将它们转换成数组，
有哪些方法呢？
```

Array.prototype.slice.call()
```
function sum(a, b) {
  let args = Array.prototype.slice.call(arguments);
  console.log(args.reduce((sum, cur) => sum + cur));//args可以调用数组原生的方法啦
}
sum(1, 2);//3
```
Array.from()
```
function sum(a, b) {
  let args = Array.from(arguments);
  console.log(args.reduce((sum, cur) => sum + cur));//args可以调用数组原生的方法啦
}
sum(1, 2);//3
```
这种方法也可以用来转换Set和Map哦！

ES6展开运算符
```
function sum(a, b) {
  let args = [...arguments];
  console.log(args.reduce((sum, cur) => sum + cur));//args可以调用数组原生的方法啦
}
sum(1, 2);//3
```
利用concat+apply
```
function sum(a, b) {
  let args = Array.prototype.concat.apply([], arguments);//apply方法会把第二个参数展开
  console.log(args.reduce((sum, cur) => sum + cur));//args可以调用数组原生的方法啦
}
sum(1, 2);//3
```

#### forEach中return有效果吗？如何中断forEach循环
在forEach中用return不会返回，函数会继续执行。
```
let nums = [1, 2, 3];
nums.forEach((item, index) => {
  return;//无效
})
```
中断方法：
- 使用try监视代码块，在需要中断的地方抛出异常。
- 官方推荐方法（替换方法）：用every和some替代forEach函数。every在碰到return false的时候，中止循环。some在碰到return true的时候，中止循环

#### JS判断数组中是否包含某个值
方法一：array.indexOf
- 此方法判断数组中是否存在某个值，如果存在，则返回数组元素的下标，否则返回-1。
```
var arr=[1,2,3,4];
var index=arr.indexOf(3);
console.log(index);
```

方法二：array.includes(searcElement[,fromIndex])
- 此方法判断数组中是否存在某个值，如果存在返回true，否则返回false
```
var arr=[1,2,3,4];
if(arr.includes(3))
    console.log("存在");
else
    console.log("不存在");
```

方法三：array.find(callback[,thisArg])
- 返回数组中满足条件的第一个元素的值，如果没有，返回undefined
```
var arr=[1,2,3,4];
var result = arr.find(item =>{
    return item > 3
});
console.log(result);
```

方法四：array.findeIndex(callback[,thisArg])
- 返回数组中满足条件的第一个元素的下标，如果没有找到，返回-1
```
var arr=[1,2,3,4];
var result = arr.findIndex(item =>{
    return item > 3
});
console.log(result);
```

#### Array(3)和Array(3,4)的区别
```
console.log(Array(3)) // [empty x 3]
console.log(Array(3, 4)) // [3, 4]
```

#### 请创建一个长度为100，值都为1的数组
```
new Array(100).fill(1)
```

#### 请创建一个长度为100，值为对应下标的数组
```
// cool的写法：
[...Array(100).keys()]

// 其他方法：
Array(100).join(",").split(",").map((v, i) => i)
Array(100).fill().map((v, i) => i)
```


### 函数

  #### JavaScript中，调用函数有哪几种方式
```
方法调用模式 Foo.foo(arg1, arg2);
函数调用模式 foo(arg1, arg2);
构造器调用模式 (new Foo())(arg1, arg2);
call/applay调用模式 Foo.foo.call(that, arg1, arg2);
bind调用模式 Foo.foo.bind(that)(arg1, arg2)();
```

  #### 函数式编程
```
简单说，"函数式编程"是一种"编程范式"（programming paradigm），
也就是如何编写程序的方法论。

它具有以下特性：闭包和高阶函数、惰性计算、递归、函数
是"第一等公民"、只用"表达式"。
```

  #### 箭头函数与普通函数的区别
```
函数体内的this对象，就是定义时所在的对象，而不是使用时所在的对象
不可以当作构造函数，也就是说，不可以使用new命令，否则会抛出一个错误
不可以使用arguments对象，该对象在函数体内不存在。如果要用，可以用Rest参数代替
不可以使用yield命令，因此箭头函数不能用作Generator函数
```

  #### 封装一个函数，参数是定时器的时间，.then执行回调函数
```
function sleep (time) {
    return new Promise((resolve) => setTimeout(resolve, time));
}
```

  #### 函数节流，应用场景和原理
```
函数节流(throttle)是指阻止一个函数在很短时间间隔内连续调用。 
只有当上一次函数执行后达到规定的时间间隔，才能进行下一次调用。 
但要保证一个累计最小调用间隔（否则拖拽类的节流都将无连续效果）

函数节流用于 onresize, onscroll 等短时间内会多次触发的事件

函数节流的原理：使用定时器做时间节流。 当触发一个事件时，
先用 setTimout 让这个事件延迟一小段时间再执行。 如果在这个
时间间隔内又触发了事件，就 clearTimeout 原来的定时器， 
再 setTimeout 一个新的定时器重复以上流程。

函数节流简单实现：
function throttle(method, context) {
     clearTimeout(methor.tId);
     method.tId = setTimeout(function(){
         method.call(context);
     }， 100); // 两次调用至少间隔 100ms
}
// 调用
window.onresize = function(){
  throttle(myFunc, window);
}
```

  #### isNaN和Number.isNaN函数的区别
```
函数 isNaN 接收参数后，会尝试将这个参数转换为数值，任何不能被转换为数值的的值都会返回 true，因此非数字值传入也会
返回 true ，会影响 NaN 的判断。

函数 Number.isNaN 会首先判断传入参数是否为数字，如果是数字再继续判断是否为 NaN ，这种方法对于 NaN 的判断更为
准确。
```

  #### Javascript全局函数和全局变量
```
全局变量
Infinity 代表正的无穷大的数值。
NaN 指示某个值是不是数字值。
undefined 指示未定义的值。

全局函数
decodeURI() 解码某个编码的 URI。
decodeURIComponent() 解码一个编码的 URI 组件。
encodeURI() 把字符串编码为 URI。
encodeURIComponent() 把字符串编码为 URI 组件。
escape() 对字符串进行编码。
eval() 计算 JavaScript 字符串，并把它作为脚本代码来执行。
isFinite() 检查某个值是否为有穷大的数。
isNaN() 检查某个值是否是数字。
Number() 把对象的值转换为数字。
parseFloat() 解析一个字符串并返回一个浮点数。
parseInt() 解析一个字符串并返回一个整数。
String() 把对象的值转换为字符串。
unescape() 对由escape() 编码的字符串进行解码
```

  #### 什么是闭包，为什么要用它
```
闭包是指有权访问另一个函数作用域中变量的函数，
创建闭包的最常见的方式就是在一个函数内创建另一个函数，
创建的函数可以访问到当前函数的局部变量。

闭包有两个常用的用途。
闭包的第一个用途是使我们在函数外部能够访问到函数内部的变量。
通过使用闭包，我们可以通过在外部调用闭包函数，从而在外部
访问到函数内部的变量，可以使用这种方法来创建私有变量。

函数的另一个用途是使已经运行结束的函数上下文中的
变量对象继续留在内存中，因为闭包函数保留了这个
变量对象的引用，所以这个变量对象不会被回收。

其实闭包的本质就是作用域链的一个特殊的应用，
只要了解了作用域链的创建过程，就能够理解闭包的实现原理。
```

```
闭包的特性：
函数内再嵌套函数
内部函数可以引用外层的参数和变量
参数和变量不会被垃圾回收机制回收

使用闭包主要是为了设计私有的方法和变量。闭包的优点是可以避免
全局变量的污染，缺点是闭包会常驻内存，会增大内存使用量，
使用不当很容易造成内存泄露。
在js中，函数即闭包，只有函数才会产生作用域的概念

闭包的最大用处有两个，一个是可以读取函数内部的变量，
另一个就是让这些变量始终保持在内存中

闭包的另一个用处，是封装对象的私有属性和私有方法

好处：能够实现封装和缓存等；
坏处：就是消耗内存、不正当使用会造成内存溢出的问题

使用闭包的注意点
由于闭包会使得函数中的变量都被保存在内存中，内存消耗很大，
所以不能滥用闭包，否则会造成网页的性能问题，在IE中可能导致内存泄露
解决方法是，在退出函数之前，将不使用的局部变量全部删除
```

```
闭包是指有权访问另一个函数作用域中的变量的函数
function a() {
    var name = "edward"
    return function b() {
        console.log(name) ; //edward
    }
}
a()()
上述代码中b函数可以访问a函数内部变量name，则称b为闭包函数。
下面是闭包常见的定时器的问题：
for (var i = 0; i < 5; i++) {
    setTimeout(() => {
        console.log(i);  //5 5 5 5 5
    }, 1000)
}
上述代码执行1s后，打印五个5，原因是因为再这1s中内，
for循环已经执行完毕，i变成了5，所以五次打印的结果都是5。
那么如何将打印结果变为 0 1 2 3 4这样输出呢？在闭包中，
闭包函数能够保存父作用域的值，那么结合这个题，
只需要用一个函数将setTimeOut包裹起来，
这个函数作为闭包函数即可，如下代码：
for (var i = 0; i < 5; i++) {
    (function(j) {
        setTimeout(function() {
            console.log(j);
        },1000)
    })(i)
}
其中，每一个遍历，都会有一个闭包函数将此时的i
保存下来，传递给延时器，
这样每一个延时器到时间后打印的就是0 1 2 3 4。
```

- 闭包是指有权访问另外一个函数作用域中的变量的函数，
- 闭包是指那些能够访问自由变量的函数。
  - （其中自由变量，指在函数中使用的，但既不是函数参数arguments也不是函数的局部变量的变量，其实就是另外一个函数作用域中的变量。）

#### 闭包产生的原因
- 首先要明白作用域链的概念，其实很简单，在ES5中只存在两种作用域————全局作用域和函数作用域，当访问一个变量时，解释器会首先在当前作用域查找标示符，如果没有找到，就去父作用域找，直到找到该变量的标示符或者不在父作用域中，这就是作用域链，值得注意的是，每一个子函数都会拷贝上级的作用域，形成一个作用域的链条。 比如:
```
var a = 1;
function f1() {
  var a = 2
  function f2() {
    var a = 3;
    console.log(a);//3
  }
}
```
- 在这段代码中，f1的作用域指向有全局作用域(window)和它本身，而f2的作用域指向全局作用域(window)、f1和它本身。而且作用域是从最底层向上找，直到找到全局作用域window为止，如果全局还没有的话就会报错。就这么简单一件事情

- 闭包产生的本质就是，当前环境中存在指向父级作用域的引用。还是举上面的例子:
```
function f1() {
  var a = 2
  function f2() {
    console.log(a);//2
  }
  return f2;
}
var x = f1();
x();
```
- 这里x会拿到父级作用域中的变量，输出2。因为在当前环境中，含有对f2的引用，f2恰恰引用了window、f1和f2的作用域。因此f2可以访问到f1的作用域的变量。

- 那是不是只有返回函数才算是产生了闭包呢？
- 回到闭包的本质，我们只需要让父级作用域的引用存在即可，因此我们还可以这么做：
```
var f3;
function f1() {
  var a = 2
  f3 = function() {
    console.log(a);
  }
}
f1();
f3();
```
- 让f1执行，给f3赋值后，等于说现在f3拥有了window、f1和f3本身这几个作用域的访问权限，还是自底向上查找，最近是在f1中找到了a,因此输出2。
- 在这里是外面的变量f3存在着父级作用域的引用，因此产生了闭包，形式变了，本质没有改变

#### 闭包有哪些表现形式
明白了本质之后，我们就来看看，在真实的场景中，
究竟在哪些地方能体现闭包的存在？

- 返回一个函数。刚刚已经举例。
- 作为函数参数传递
```
var a = 1;
function foo(){
  var a = 2;
  function baz(){
    console.log(a);
  }
  bar(baz);
}
function bar(fn){
  // 这就是闭包
  fn();
}
// 输出2，而不是1
foo();
```
- 在定时器、事件监听、Ajax请求、跨窗口通信、Web Workers或者任何异步中，只要使用了回调函数，实际上就是在使用闭包

以下的闭包保存的仅仅是window和当前作用域。
```
// 定时器
setTimeout(function timeHandler(){
  console.log('111');
}，100)

// 事件监听
$('#app').click(function(){
  console.log('DOM Listener');
})
```
- IIFE(立即执行函数表达式)创建闭包, 保存了全局作用域window和当前函数的作用域，因此可以访问全局的变量
```
var a = 2;
(function IIFE(){
  // 输出2
  console.log(a);
})();
```

#### 如何解决下面的循环输出问题
```
for(var i = 1; i <= 5; i ++){
  setTimeout(function timer(){
    console.log(i)
  }, 0)
}
```
- 为什么会全部输出6？如何改进，让它输出1，2，3，4，5？(方法越多越好) 因为setTimeout为宏任务，由于JS中单线程eventLoop机制，在主线程同步任务执行完后才去执行宏任务，因此循环结束后setTimeout中的回调才依次执行，但输出i的时候当前作用域没有，往上一级再找，发现了i,此时循环已经结束，i变成了6。因此会全部输出6。

解决方法：
- 利用IIFE(立即执行函数表达式)当每次for循环时，把此时的i变量传递到定时器中
```
for(var i = 1;i <= 5;i++){
  (function(j){
    setTimeout(function timer(){
      console.log(j)
    }, 0)
  })(i)
}
```
- 给定时器传入第三个参数, 作为timer函数的第一个函数参数
```
for(var i=1;i<=5;i++){
  setTimeout(function timer(j){
    console.log(j)
  }, 0, i)
}
```
- 使用ES6中的let
```
for(let i = 1; i <= 5; i++){
  setTimeout(function timer(){
    console.log(i)
  },0)
}
```
- let使JS发生革命性的变化，让JS有函数作用域变为了块级作用域，用let后作用域链不复存在。代码的作用域以块级为单位，以上面代码为例:
```
// i = 1
{
  setTimeout(function timer(){
    console.log(1)
  },0)
}
// i = 2
{
  setTimeout(function timer(){
    console.log(2)
  },0)
}
// i = 3
```

  #### 使用闭包实现每隔一秒打印1,2,3,4
```js
// 使用闭包实现
for (var i = 0; i < 5; i++) {
  (function(i) {
    setTimeout(function() {
      console.log(i);
    }, i * 1000);
  })(i);
}

// 使用 let 块级作用域
for (let i = 0; i < 5; i++) {
  setTimeout(function() {
    console.log(i);
  }, i * 1000);
}
```

  #### eval是做什么的
```
它的功能是把对应的字符串解析成 JS 代码并运行。

应该避免使用 eval，不安全，非常耗性能（2次，一次解析成 js 语句，一次执行）。
```

```
它的功能是把对应的字符串解析成JS代码并运行
应该避免使用eval，不安全，非常耗性能（2次，一次解析成js语句，一次执行）
由JSON字符串转换为JSON对象的时候可以用eval，var obj =eval('('+ str +')')
```


### js原型和原型链
```
原型：在 js 中我们是使用构造函数来新建一个对象的，
每一个构造函数的内部都有一个 prototype 属性值，
这个属性值是一个对象，这个对象包含了可以由该构造函数的
所有实例共享的属性和方法。当我们使用构造函数新建一个对象后，
在这个对象的内部将包含一个指针，这个指针指向构造函数的
prototype 属性对应的值，在 ES5 中这个指针被称为对象的原型（prototype）。

一般来说我们是不应该能够获取到这个值的，但是现在浏览器中
都实现了 __proto__ 属性来让我们访问这个属性，但是我们最好
不要使用这个属性，因为它不是规范中规定的。
ES5 中新增了一个 Object.getPrototypeOf() 方法，
我们可以通过这个方法来获取对象的原型。

原型链：当我们访问一个对象的属性时，如果这个对象内部不存在这个属性，
那么它就会去它的原型对象里找这个属性，这个原型对象又会有自己的原型，
于是就这样一直找下去，也就是原型链的概念。

原型链的尽头一般来说都是 Object.prototype ，所以这就是
我们新建的对象为什么能够使用 toString() 等方法的原因。

特点：
JavaScript 对象是通过引用来传递的，我们创建的每个新对象实体中并没有一份
属于自己的原型副本。当我们修改原型时，与之相关的对象也会继承这一改变。

关系：instance.constructor.prototype = instance.__proto__
```

#### 原型/构造函数/实例
- 原型(prototype): 一个简单的对象，用于实现对象的 属性继承。可以简单的理解成对象的爹。在 Firefox 和 Chrome 中，每个JavaScript对象中都包含一个__proto__(非标准)的属性指向它爹(该对象的原型)，可obj.__proto__进行访问。
- 构造函数: 可以通过new来 新建一个对象 的函数。
- 实例: 通过构造函数和new创建出来的对象，便是实例。 实例通过__proto__指向原型，通过constructor指向构造函数。
```
以Object为例，我们常用的Object便是一个构造函数，
因此我们可以通过它构建实例。
```
```
// 实例
const instance = new Object()
```
```
则此时， 实例为instance, 构造函数为Object，我们知道，
构造函数拥有一个prototype的属性指向原型，因此原型为:
```
```
// 原型
const prototype = Object.prototype
```
这里我们可以来看出三者的关系:
- 实例.__proto__ === 原型
- 原型.constructor === 构造函数
- 构造函数.prototype === 原型
```
// 这条线其实是是基于原型进行获取的，可以理解成一条基于原型的映射线
// 例如: 
// const o = new Object()
// o.constructor === Object   --> true
// o.__proto__ = null;
// o.constructor === Object   --> false
实例.constructor === 构造函数
```

#### 原型对象和构造函数有何关系
- 在JavaScript中，每当定义一个函数数据类型(普通函数、类)时候，都会天生自带一个prototype属性，这个属性指向函数的原型对象。
- 当函数经过new调用时，这个函数就成为了构造函数，返回一个全新的实例对象，这个实例对象有一个__proto__属性，指向构造函数的原型对象。

#### 能不能描述一下原型链
- JavaScript对象通过__proto__ 指向父类对象，直到指向Object对象为止，这样就形成了一个原型指向的链条, 即原型链

- 对象的 hasOwnProperty() 来检查对象自身中是否含有该属性
- 使用 in 检查对象中是否含有某个属性时，如果对象中没有但是原型链中有，也会返回 true

  #### js获取原型的方法
```
p.__proto__
p.constructor.prototype
Object.getPrototypeOf(p)
```

  #### Javascript中，有一个函数，执行时对象查找时，永远不会去查找原型，这个函数是
```
hasOwnProperty

所有继承了 Object 的对象都会继承到 hasOwnProperty 方法。
这个方法可以用来检测一个对象是否含有特定的自身属性，
和in 运算符不同，该方法会忽略掉那些从原型链上继承到的属性。
```

### js继承
```
javascript继承的7种方法：
(1)原型链继承：将父类的实例作为子类的原型。
(2)构造函数继承（使用call）：使用父类的构造函数来增强子类实例，
等于是复制父类的实例属性给子类。
(3)实例继承：为父类实例添加新特性，作为子类实例返回。
(4)拷贝继承：把父类实例对象上的方法拷贝到子类的原型上。
(5)组合继承：通过调用父类构造函数，继承父类的属性并保留传参的优点，
然后通过将父类实例作为子类原型，实现函数复用。
(6)寄生组合继承：通过寄生方式，砍掉父类的实例属性，这样，
在调用两次父类的构造的时候，就不会初始化两次实例方法/属性，
避免的组合继承的缺点。
(7)使用extends关键字扩展一个类并继承它的行为（es6）。
```

```
我了解的 js 中实现继承的几种方式有：
（1）第一种是以原型链的方式来实现继承，但是这种实现方式存在的缺点是，
在包含有引用类型的数据时，会被所有的实例对象所共享，
容易造成修改的混乱。还有就是在创建子类型的时候不能向超类型传递参数。

（2）第二种方式是使用借用构造函数的方式，这种方式是通过在
子类型的函数中调用超类型的构造函数来实现的，这一种方法解决了
不能向超类型传递参数的缺点，但是它存在的一个问题就是无法实现
函数方法的复用，并且超类型原型定义的方法子类型也没有办法访问到。

（3）第三种方式是组合继承，组合继承是将原型链和借用构造函数
组合起来使用的一种方式。通过借用构造函数的方式来实现类型的属性
的继承，通过将子类型的原型设置为超类型的实例来实现方法的继承。
这种方式解决了上面的两种模式单独使用时的问题，但是由于我们
是以超类型的实例来作为子类型的原型，所以调用了两次超类的
构造函数，造成了子类型的原型中多了很多不必要的属性。

（4）第四种方式是原型式继承，原型式继承的主要思路就是基于
已有的对象来创建新的对象，实现的原理是，向函数中传入一个对象，
然后返回一个以这个对象为原型的对象。这种继承的思路主要不是
为了实现创造一种新的类型，只是对某个对象实现一种简单继承，
ES5 中定义的 Object.create() 方法就是原型式继承的实现。
缺点与原型链方式相同。

（5）第五种方式是寄生式继承，寄生式继承的思路是创建一个
用于封装继承过程的函数，通过传入一个对象，然后复制一个对象的副本，
然后对象进行扩展，最后返回这个对象。这个扩展的过程就可以理解是一种继承。
这种继承的优点就是对一个简单对象实现继承，如果这个对象
不是我们的自定义类型时。缺点是没有办法实现函数的复用。

（6）第六种方式是寄生式组合继承，组合继承的缺点就是使用
超类型的实例做为子类型的原型，导致添加了不必要的原型属性。
寄生式组合继承的方式是使用超类型的原型的副本来作为
子类型的原型，这样就避免了创建不必要的属性。
```

js继承实现方式：既然要实现继承，那么首先我们得有一个父类，代码如下：
```
// 定义一个动物类
function Animal (name) {
  // 属性
  this.name = name || 'Animal';
  // 实例方法
  this.sleep = function(){
    console.log(this.name + '正在睡觉！');
  }
}
// 原型方法
Animal.prototype.eat = function(food) {
  console.log(this.name + '正在吃：' + food);
};
```

#### 借助call
```
 function Parent1(){
    this.name = 'parent1';
  }
  function Child1(){
    Parent1.call(this);
    this.type = 'child1'
  }
  console.log(new Child1);
```
- 这样写的时候子类虽然能够拿到父类的属性值，但是问题是父类原型对象中一旦存在方法那么子类无法继承。那么引出下面的方法。

  #### 原型链继承
```
核心：将父类的实例作为子类的原型
function Cat() {
}
Cat.prototype = new Animal();
Cat.prototype.name = 'cat';

// Test Code
var cat = new Cat();
console.log(cat.name);
cat.eat('fish');    //cat正在吃fish
cat.sleep();    //cat正在睡觉。。。
console.log(cat instanceof Animal); //true
console.log(cat instanceof Cat);    //true

特点：
1.纯粹的继承关系，实例是子类的实例，也是父类的实例
2.父类新增方法属性，子类都能访问到
3.简单易于实现
缺点：
1.可以在Cat构造函数中，为Cat实例增加实例属性。如果要新增原型属性和方法，则必须放在Cat.prototype = new Animal();这样的语句之后执行。
2.无法实现多继承
3.来自原型对象的引用属性是所有实例共享的
4.创建子类的实例时，无法向父类构造函数传参
```

```
 function Parent2() {
    this.name = 'parent2';
    this.play = [1, 2, 3]
  }
  function Child2() {
    this.type = 'child2';
  }
  Child2.prototype = new Parent2();

  console.log(new Child2());
```
- 看似没有问题，父类的方法和属性都能够访问，但实际上有一个潜在的不足。举个例子：
```
var s1 = new Child2();
var s2 = new Child2();
s1.play.push(4);
console.log(s1.play, s2.play);
```
- 明明我只改变了s1的play属性，为什么s2也跟着变了呢？很简单，因为两个实例使用的是同一个原型对象。

那么还有更好的方式么？

#### 将call和原型链组合
```
  function Parent3 () {
    this.name = 'parent3';
    this.play = [1, 2, 3];
  }
  function Child3() {
    Parent3.call(this);
    this.type = 'child3';
  }
  Child3.prototype = new Parent3();
  var s3 = new Child3();
  var s4 = new Child3();
  s3.play.push(4);
  console.log(s3.play, s4.play);
```
- 之前的问题都得以解决。但是这里又徒增了一个新问题，那就是Parent3的构造函数会多执行了一次（Child3.prototype = new Parent3();）。这是我们不愿看到的。那么如何解决这个问题？

#### 组合继承的优化1
```
  function Parent4 () {
    this.name = 'parent4';
    this.play = [1, 2, 3];
  }
  function Child4() {
    Parent4.call(this);
    this.type = 'child4';
  }
  Child4.prototype = Parent4.prototype;
```
- 这里让将父类原型对象直接给到子类，父类构造函数只执行一次，而且父类属性和方法均能访问，但是我们来测试一下：
```
var s3 = new Child4();
var s4 = new Child4();
console.log(s3)
```
- 子类实例的构造函数是Parent4，显然这是不对的，应该是Child4。

#### (最推荐使用):组合继承的优化2
```
 function Parent5 () {
    this.name = 'parent5';
    this.play = [1, 2, 3];
  }
  function Child5() {
    Parent5.call(this);
    this.type = 'child5';
  }
  Child5.prototype = Object.create(Parent5.prototype);
  Child5.prototype.constructor = Child5;
```
- 这是最推荐的一种方式，接近完美的继承，它的名字也叫做寄生组合继承。

  #### 构造函数继承
```
使用call
核心：使用父类的构造函数来增强子类实例，
等于是复制父类的实例属性给子类（没用到原型）

function Cat2(name) {
    Animal.call(this);
    this.name = name || 'Tom';
}
// Test Code
var cat2 = new Cat2();
console.log(cat2.name); //Tom
cat2.sleep()    //Tom正在睡觉。。。
console.log(cat2 instanceof Cat2); //true
console.log(cat2 instanceof Animal); //false

特点：
1.解决了1中，子类实例共享父类引用属性的问题
2.创建子类实例时，可以向父类传递参数
3.可以实现多继承（call多个父类对象）
缺点：
1.实例并不是父类的实例，只是子类的实例
2.只能继承父类的实例属性和方法，不能继承原型属性/方法
3.无法实现函数复用，每个子类都有父类实例函数的副本，影响性能
```

  #### 实例继承
```
核心：为父类实例添加新特性，作为子类实例返回
function Cat3(name) {
    var instance = new Animal();
    instance.name = name || 'Tom';
    return instance;
}

// Test Code
var cat3 = new Cat3();
console.log(cat3.name);
cat3.sleep();
cat3.eat('meat');
console.log(cat3 instanceof Cat3); //false
console.log(cat3 instanceof Animal); //true

特点：
1.不限制调用方式，不管是 new 子类() 还是 子类()，
返回的对象具有相同的效果
缺点：
1.实例是父类的实例，不是子类的实例
2.不支持多继承
```

  #### 拷贝继承
```
function Cat(name) {
    var animal = new Animal();
    for (var p in animal) {
        Cat.prototype[p] = animal[p];
    }
    Cat.prototype.name = name || 'Tom';
}

// Test Code
var cat = new Cat();
console.log(cat.name);
cat.sleep();
cat.eat('bread');
console.log(cat instanceof Cat); //true
console.log(cat instanceof Animal); //false

特点：
支持多继承
缺点：
1.效率较低，占用内存高
2.无法获取父类不可枚举的方法（不可枚举方法，不能使用for-in访问到）
```

  #### 组合继承
```
核心：通过调用父类构造函数，继承父类的属性并保留传参的优点，
然后通过将父类实例作为子类原型，实现函数复用。

function Cat(name) {
    Animal.call(this);
    this.name = name || "Tom";
}
Cat.prototype = new Animal();
Cat.prototype.constructor = Cat;

// Test Code
var cat = new Cat();
console.log(cat.name);
cat.sleep();
cat.eat('bread');
console.log(cat instanceof Cat); //true
console.log(cat instanceof Animal); //true

特点：
1.弥补了方式二的缺陷，可以继承实例属性/方法，也可以继承原型属性/方法
2.即是子类的实例，也是父类的实例
3.不存在引用属性共享问题
4.可传参
5.函数可复用
缺点：
1.调用了两次父构造函数，生成了两份实例
（子类实例将子类原型上的那份屏蔽掉了），消耗内存较少
```

  #### 寄生组合继承
```
核心：通过寄生方式，砍掉父类的实例属性，这样，在调用两次父类的构造的时候，就不会初始化两次实例方法/属性，避免的组合继承的缺点。
function Cat(name) {
    Animal.call(this);
    this.name = name || "Tom";
}
(function () {
    // 创建一个没有实例方法的类
    var Super = function () {
    }
    Super.prototype = Animal.prototype;
    // 将实例作为子类的原型
    Cat.prototype = new Super();
})();
// 修复构造函数
Cat.prototype.constructor = Cat;

// Test Code
var cat = new Cat();
console.log(cat.name);
cat.sleep();
cat.eat('bread');
console.log(cat instanceof Cat); //true
console.log(cat instanceof Animal); //true

特点：
堪称完美
缺点：
1.实现较为复杂
```

   #### 寄生式组合继承的实现
```js
function Person(name) {
  this.name = name;
}

Person.prototype.sayName = function() {
  console.log("My name is " + this.name + ".");
};

function Student(name, grade) {
  Person.call(this, name);
  this.grade = grade;
}

Student.prototype = Object.create(Person.prototype);
Student.prototype.constructor = Student;

Student.prototype.sayMyGrade = function() {
  console.log("My grade is " + this.grade + ".");
};
```

  #### es6使用extends关键字扩展一个类并继承它的行为
```
首先使用es6语法把代码简化如下：
class Animal2 {
    constructor (name, food) {
        this.name = name || "Animal";
        this.food = food;
        this.sleep = () => console.log(this.name + '正在睡觉。。。');
    }
    eat(){
        // console.log(this.name + '正在吃' + this.food);
        return this.name + '正在吃' + this.food;
    }
}

然后让Reptile类继承Animal2

class Reptile extends Animal2 {
    constructor (name, food, habit){
        super(name, food);
        this.habit = habit;
    }
    printHabit() {
        console.log(this.habit);
    }
}

// Test Code
let cat = new Reptile('cat', 'fish', 'sleep');
cat.printHabit(); //sleep
console.log(cat.eat()); //cat正在吃fish
console.log(cat instanceof Reptile); //true
console.log(cat instanceof Animal2); //true
```

#### ES6的extends被编译后的JavaScript代码
- ES6的代码最后都是要在浏览器上能够跑起来的，这中间就利用了babel这个编译工具，将ES6的代码编译成ES5让一些不支持新语法的浏览器也能运行。

那最后编译成了什么样子呢？
```
function _possibleConstructorReturn(self, call) {
    // ...
    return call && (typeof call === 'object' || typeof call === 'function') ? call : self;
}

function _inherits(subClass, superClass) {
    // ...
    //看到没有
    subClass.prototype = Object.create(superClass && superClass.prototype, {
        constructor: {
            value: subClass,
            enumerable: false,
            writable: true,
            configurable: true
        }
    });
    if (superClass) Object.setPrototypeOf ? Object.setPrototypeOf(subClass, superClass) : subClass.__proto__ = superClass;
}


var Parent = function Parent() {
    // 验证是否是 Parent 构造出来的 this
    _classCallCheck(this, Parent);
};

var Child = (function (_Parent) {
    _inherits(Child, _Parent);

    function Child() {
        _classCallCheck(this, Child);

        return _possibleConstructorReturn(this, (Child.__proto__ || Object.getPrototypeOf(Child)).apply(this, arguments));
    }

    return Child;
}(Parent));
```
- 核心是_inherits函数，可以看到它采用的依然也是第五种方式————寄生组合继承方式，同时证明了这种方式的成功。不过这里加了一个Object.setPrototypeOf(subClass, superClass)，这是用来干啥的呢？

- 答案是用来继承父类的静态方法。这也是原来的继承方式疏忽掉的地方。

- 追问: 面向对象的设计一定是好的设计吗？
  - 不一定。从继承的角度说，这一设计是存在巨大隐患的。

#### 从设计思想上谈谈继承本身的问题
- 假如现在有不同品牌的车，每辆车都有drive、music、addOil这三个方法。
```
class Car{
  constructor(id) {
    this.id = id;
  }
  drive(){
    console.log("wuwuwu!");
  }
  music(){
    console.log("lalala!")
  }
  addOil(){
    console.log("哦哟！")
  }
}
class otherCar extends Car{}
```

```
现在可以实现车的功能，并且以此去扩展不同的车。

但是问题来了，新能源汽车也是车，但是它并不需要addOil(加油)。

如果让新能源汽车的类继承Car的话，也是有问题的，
俗称"大猩猩和香蕉"的问题。大猩猩手里有香蕉，但是我现在明明只
需要香蕉，却拿到了一只大猩猩。也就是说加油这个方法，
我现在是不需要的，但是由于继承的原因，也给到子类了。

```
继承的最大问题在于：无法决定继承哪些属性，所有属性都得继承。
```
当然你可能会说，可以再创建一个父类啊，把加油的方法给去掉，
但是这也是有问题的，一方面父类是无法描述所有子类的细节情况的，
为了不同的子类特性去增加不同的父类，代码势必会大量重复，另一方面一旦
子类有所变动，父类也要进行相应的更新，代码的耦合性太高，维护性不好。
```

那如何来解决继承的诸多问题呢？
- 用组合，这也是当今编程语法发展的趋势，比如golang完全采用的是面向组合的设计方式。
```
顾名思义，面向组合就是先设计一系列零件，然后将这些零件进行拼装，
来形成不同的实例或者类。
```
```
function drive(){
  console.log("wuwuwu!");
}
function music(){
  console.log("lalala!")
}
function addOil(){
  console.log("哦哟！")
}

let car = compose(drive, music, addOil);
let newEnergyCar = compose(drive, music);
```
代码干净，复用性也很好。这就是面向组合的设计方式。

#### 继承-简版
在 ES5 中，我们可以使用如下方式解决继承的问题
```
function Super() {}
Super.prototype.getNumber = function() {
  return 1
}

function Sub() {}
let s = new Sub()
Sub.prototype = Object.create(Super.prototype, {
  constructor: {
    value: Sub,
    enumerable: false,
    writable: true,
    configurable: true
  }
})
```
- 以上继承实现思路就是将子类的原型设置为父类的原型
- 在 ES6 中，我们可以通过 class 语法轻松解决这个问题
```
class MyDate extends Date {
  test() {
    return this.getTime()
  }
}
let myDate = new MyDate()
myDate.test()
```
- 但是 ES6 不是所有浏览器都兼容，所以我们需要使用 Babel 来编译这段代码。
- 如果你使用编译过得代码调用 myDate.test()你会惊奇地发现出现了报错
```
因为在 JS 底层有限制，如果不是由 Date构造出来的实例的话，
是不能调用 Date 里的函数的。所以这也侧面的说明了：
ES6 中的 class 继承与 ES5 中的一般继承写法是不同的。
```
- 既然底层限制了实例必须由 Date 构造出来，那么我们可以改变下思路实现继承
```
function MyData() {

}
MyData.prototype.test = function () {
  return this.getTime()
}
let d = new Date()
Object.setPrototypeOf(d, MyData.prototype)
Object.setPrototypeOf(MyData.prototype, Date.prototype)
```
- 以上继承实现思路：先创建父类实例 => 改变实例原先的 _proto__转而连接到子类的 prototype=> 子类的 prototype 的 __proto__ 改为父类的 prototype。
- 通过以上方法实现的继承就可以完美解决 JS 底层的这个限制

### this对象
```
this 是执行上下文中的一个属性，它指向最后一次调用这个方法的对象。
在实际开发中，this 的指向可以通过四种调用模式来判断。

第一种是函数调用模式，当一个函数不是一个对象的属性时，
直接作为函数来调用时，this 指向全局对象。

第二种是方法调用模式，如果一个函数作为一个对象的方法
来调用时，this 指向这个对象。

第三种是构造器调用模式，如果一个函数用 new 调用时，
函数执行前会新创建一个对象，this 指向这个新创建的对象。

第四种是 apply 、 call 和 bind 调用模式，这三个方法都
可以显示的指定调用函数的 this 指向。其中 apply 方法接收
两个参数：一个是 this 绑定的对象，一个是参数数组。
call 方法接收的参数，第一个是 this 绑定的对象，后面的
其余参数是传入函数执行的参数。也就是说，在使用 call() 方法时，
传递给函数的参数必须逐个列举出来。bind 方法通过传入一个对象，
返回一个 this 绑定了传入对象的新函数。这个函数的 this 
指向除了使用 new 时会被改变，其他情况下都不会改变。

这四种方式，使用构造器调用模式的优先级最高，然后是 apply 、
call 和 bind 调用模式，然后是方法调用模式，然后是函数调用模式。
```

```
this总是指向函数的直接调用者（而非间接调用者）
如果有new关键字，this指向new出来的那个对象
在事件中，this指向触发这个事件的对象，特殊的是，
IE中的attachEvent中的this总是指向全局对象Window
```

#### this
我们先来看几个函数调用的场景
```
function foo() {
  console.log(this.a)
}
var a = 1
foo()

const obj = {
  a: 2,
  foo: foo
}
obj.foo()

const c = new foo()
```
- 对于直接调用 foo 来说，不管 foo 函数被放在了什么地方，this 一定是window
- 对于 obj.foo() 来说，我们只需要记住，谁调用了函数，谁就是 this，所以在这个场景下 foo 函数中的 this 就是 obj 对象
- 对于 new 的方式来说，this 被永远绑定在了 c 上面，不会被任何方式改变 this
```
说完了以上几种情况，其实很多代码中的 this 应该就没什么问题了，
下面让我们看看箭头函数中的 this
```
```
function a() {
  return () => {
    return () => {
      console.log(this)
    }
  }
}
console.log(a()()())
```
- 首先箭头函数其实是没有 this 的，箭头函数中的 this 只取决包裹箭头函数的第一个普通函数的 this。在这个例子中，因为包裹箭头函数的第一个普通函数是 a，所以此时的 this 是 window。另外对箭头函数使用 bind这类函数是无效的。
- 最后种情况也就是 bind 这些改变上下文的 API 了，对于这些函数来说，this 取决于第一个参数，如果第一个参数为空，那么就是 window。
- 那么说到 bind，不知道大家是否考虑过，如果对一个函数进行多次 bind，那么上下文会是什么呢？
```
let a = {}
let fn = function () { console.log(this) }
fn.bind().bind(a)() // => ?
```
- 如果你认为输出结果是 a，那么你就错了，其实我们可以把上述代码转换成另一种形式
```
// fn.bind().bind(a) 等于
let fn2 = function fn1() {
  return function() {
    return fn.apply()
  }.apply(a)
}
fn2()
```
- 可以从上述代码中发现，不管我们给函数 bind 几次，fn 中的 this 永远由第一次 bind 决定，所以结果永远是 window
```
let a = { name: 'poetries' }
function foo() {
  console.log(this.name)
}
foo.bind(a)() // => 'poetries'
```
- 以上就是 this 的规则了，但是可能会发生多个规则同时出现的情况，这时候不同的规则之间会根据优先级最高的来决定 this 最终指向哪里。
- 首先，new 的方式优先级最高，接下来是 bind 这些函数，然后是 obj.foo() 这种调用方式，最后是 foo 这种调用方式，同时，箭头函数的 this 一旦被绑定，就不会再被任何方式所改变。

总结
```
this执行主体，谁把它执行的和在哪创建的在哪执行的都没有必然的关系
```
- 函数执行，看方法前面是否有点，没有点this是window(严格模式下是undefined)，有点，点前面是谁·this·就是谁
- 给当前元素的某个事件行为绑定方法，当事件行为触发，方法中的this是当前元素本身（排除attachEvent）
- 构造函数体中this是当前类的实例
- 箭头函数中没有执行主体，所用到的this都是所处上下文中的this
- 可以基于Function.prototype上的call/apply/bind改变this指向

  #### this指向
```
this的指向在函数定义的时候是确定不了的，只有函数执行的时候才能
确定this到底指向谁，实际上this的最终指向的是那个调用它的对象

《javascript语言精髓》中大概概括了4种调用方式：
方法调用模式

函数调用模式

构造器调用模式
graph LR
A-->B

apply/call调用模式
```

```
默认绑定：全局环境中，this默认绑定到window

隐式绑定：一般地，被直接对象所包含的函数调用时，
也称为方法调用，this隐式绑定到该直接对象

隐式丢失：隐式丢失是指被隐式绑定的函数丢失绑定对象，
从而默认绑定到window。显式绑定：通过call()、apply()、
bind()方法把对象绑定到this上，叫做显式绑定

new绑定：如果函数或者方法调用之前带有关键字new，
它就构成构造函数调用。对于this绑定来说，称为new绑定

构造函数通常不使用return关键字，它们通常初始化新对象，
当构造函数的函数体执行完毕时，它会显式返回。在这种情况下，
构造函数调用表达式的计算结果就是这个新对象的值

如果构造函数使用return语句但没有指定返回值，或者返回一个原始值，
那么这时将忽略返回值，同时使用这个新对象作为调用结果

如果构造函数显式地使用return语句返回一个对象，
那么调用表达式的值就是这个对象
```

  #### call、apply、bind
- call基本使用
```
var person = {
    name : "edward"
}
var obj = {
    print : function(age){
        console.log(this.name , age)
    }
}
obj.print.call(person , 30);//edward 30

每一个函数都有call属性用来改变一个函数的this指向，
上述代码中调用print函数的call属性，将print函数的
this从obj变为person。同时call函数可以接收参数，
每个参数用逗号隔开，call中传递的参数，
能够在print函数中接收到。
```

- apply基本使用
```
var person = {
    name : "edward"
}
var obj = {
    print : function(age){
        console.log(this.name , age)
    }
}
obj.print.apply(person , [30]);//edward 30

apply函数跟call原理一样，区别在于apply函数
接收的参数用数组表示，数组中每一个参数用逗号隔开。
```

- bind基本使用
```
一个函数也可以调用bind属性来改变这个函数的this指向。代码如下：
var person = {
    name : "edward"
}
var obj = {
    print : function(age){
        console.log(this.name , age)
    }
}
obj.print.bind(person , 30)();//edward 30

bind函数接收参数的方式跟call一样，bind函数运行之后会
返回一个函数，所以上述代码中需要在bind运行之后再写一对括号。
```

  #### .call()和.apply()的区别
```
它们的作用一模一样，区别仅在于传入参数的形式的不同。

apply 接受两个参数，第一个参数指定了函数体内 this 对象的指向，
第二个参数为一个带下标的集合，这个集合可以为数组，也可以为类数组，
apply 方法把这个集合中的元素作为参数传递给被调用的函数。

call 传入的参数数量不固定，跟 apply 相同的是，
第一个参数也是代表函数体内的 this 指向，
从第二个参数开始往后，每个参数被依次传入函数。
```

  #### 手写call、apply及bind函数
call 函数的实现步骤：
```
判断调用对象是否为函数，即使我们是定义在函数的
原型上的，但是可能出现使用 call 等方式调用的情况。

判断传入上下文对象是否存在，如果不存在，则设置为 window 。

处理传入的参数，截取第一个参数后的所有参数。

将函数作为上下文对象的一个属性。

使用上下文对象来调用这个方法，并保存返回结果。

删除刚才新增的属性。

返回结果。
```

apply 函数的实现步骤：
```
判断调用对象是否为函数，即使我们是定义在函数的原型上的，
但是可能出现使用 call 等方式调用的情况。

判断传入上下文对象是否存在，如果不存在，则设置为 window 。

将函数作为上下文对象的一个属性。

判断参数值是否传入

使用上下文对象来调用这个方法，并保存返回结果。

删除刚才新增的属性

返回结果
```

bind 函数的实现步骤：
```
判断调用对象是否为函数，即使我们是定义在函数的
原型上的，但是可能出现使用 call 等方式调用的情况。

保存当前函数的引用，获取其余传入参数值。

创建一个函数返回

函数内部使用 apply 来绑定函数调用，需要判断函数作为
构造函数的情况，这个时候需要传入当前函数的 this 给 
apply 调用，其余情况都传入指定的上下文对象。
```

```js
// call函数实现
Function.prototype.myCall = function(context) {
  // 判断调用对象
  if (typeof this !== "function") {
    console.error("type error");
  }

  // 获取参数
  let args = [...arguments].slice(1),
    result = null;

  // 判断 context 是否传入，如果未传入则设置为 window
  context = context || window;

  // 将调用函数设为对象的方法
  context.fn = this;

  // 调用函数
  result = context.fn(...args);

  // 将属性删除
  delete context.fn;

  return result;
};

// apply 函数实现
Function.prototype.myApply = function(context) {
  // 判断调用对象是否为函数
  if (typeof this !== "function") {
    throw new TypeError("Error");
  }

  let result = null;

  // 判断 context 是否存在，如果未传入则为 window
  context = context || window;

  // 将函数设为对象的方法
  context.fn = this;

  // 调用方法
  if (arguments[1]) {
    result = context.fn(...arguments[1]);
  } else {
    result = context.fn();
  }

  // 将属性删除
  delete context.fn;

  return result;
};

// bind 函数实现
Function.prototype.myBind = function(context) {
  // 判断调用对象是否为函数
  if (typeof this !== "function") {
    throw new TypeError("Error");
  }

  // 获取参数
  var args = [...arguments].slice(1),
    fn = this;

  return function Fn() {
    // 根据调用方式，传入不同绑定值
    return fn.apply(
      this instanceof Fn ? this : context,
      args.concat(...arguments)
    );
  };
};
```

  #### 简单实现Function.bind函数
```
 if (!Function.prototype.bind) {
    Function.prototype.bind = function(that) {
      var func = this, args = arguments;
      return function() {
        return func.apply(that, Array.prototype.slice.call(args, 1));
      }
    }
  }
  // 只支持 bind 阶段的默认参数：
  func.bind(that, arg1, arg2)();

  // 不支持以下调用阶段传入的参数：
  func.bind(that)(arg1, arg2);
```

  #### new操作符具体干了什么呢？如何实现
```js
（1）首先创建了一个新的空对象
（2）设置原型，将对象的原型设置为函数的 prototype 对象。
（3）让函数的 this 指向这个对象，执行构造函数的代码（为这个新对象添加属性）
（4）判断函数的返回值类型，如果是值类型，返回创建的对象。如果是引用类型，就返回这个引用类型的对象。

创建一个空对象，并且 this 变量引用该对象，同时还继承了该函数的原型
属性和方法被加入到 this 引用的对象中
新创建的对象由 this 所引用，并且最后隐式的返回 this

实现:
function objectFactory() {
  let newObject = null,
    constructor = Array.prototype.shift.call(arguments),
    result = null;

  // 参数判断
  if (typeof constructor !== "function") {
    console.error("type error");
    return;
  }

  // 新建一个空对象，对象的原型为构造函数的 prototype 对象
  newObject = Object.create(constructor.prototype);

  // 将 this 指向新建对象，并执行函数
  result = constructor.apply(newObject, arguments);

  // 判断返回对象
  let flag =
    result && (typeof result === "object" || typeof result === "function");

  // 判断返回结果
  return flag ? result : newObject;
}

// 使用方法
// objectFactory(构造函数, 初始化参数);
```

  #### Javascript的作用域链
```
作用域链的作用是保证对执行环境有权访问的所有变量和函数的
有序访问，通过作用域链，我们可以访问到外层环境的变量和函数。

作用域链的本质上是一个指向变量对象的指针列表。变量对象是
一个包含了执行环境中所有变量和函数的对象。作用域链的前
端始终都是当前执行上下文的变量对象。全局执行上下文的
变量对象（也就是全局对象）始终是作用域链的最后一个对象。

当我们查找一个变量时，如果当前执行环境中没有找到，
我们可以沿着作用域链向后查找。

作用域链的创建过程跟执行上下文的建立有关
```

```
作用域链的作用是保证执行环境里有权访问的变量和函数是有序的，
作用域链的变量只能向上访问，变量访问到window对象即被终止，
作用域链向下访问变量是不被允许的简单的说，
作用域就是变量与函数的可访问范围，
即作用域控制着变量与函数的可见性和生命周期

全局函数无法查看局部函数的内部细节，但局部函数可以查看
其上层的函数细节，直至全局细节
如果当前作用域没有找到属性或方法，会向上层作用域查找，
直至全局函数，这种形式就是作用域链
```

  #### JavaScript中的作用域与变量声明提升
```
变量提升的表现是，无论我们在函数中何处位置声明的变量，
好像都被提升到了函数的首部，
我们可以在变量声明前访问到而不会报错。

造成变量声明提升的本质原因是 js 引擎在代码执行前有
一个解析的过程，创建了执行上下文，初始化了一些代码
执行时需要用到的对象。当我们访问一个变量时，我们会到
当前执行上下文中的作用域链中去查找，而作用域链的首端
指向的是当前执行上下文的变量对象，这个变量对象是执行
上下文的一个属性，它包含了函数的形参、所有的函数和
变量声明，这个对象的是在代码解析的时候创建的。
这就是会出现变量声明提升的根本原因。
```

```
JavaScript作用域：
在Java、C等语言中，作用域为for语句、if语句或{}内的一块区域，
为作用域；
而在 JavaScript 中，作用域为function(){}内的区域，
称为函数作用域。

JavaScript变量声明提升：
在JavaScript中，函数声明与变量声明经常被JavaScript引擎
隐式地提升到当前作用域的顶部。
声明语句中的赋值部分并不会被提升，只有名称被提升函数声明的
优先级高于变量，如果变量名跟函数名相同且未赋值，
则函数声明会覆盖变量声明
如果函数有多个同名参数，
那么最后一个参数（即使没有定义）会覆盖前面的同名参数
```

```
当执行 JS 代码时，会生成执行环境，只要代码不是写在函数中的，
就是在全局执行环境中，函数中的代码会产生函数执行环境，只此两种执行环境

接下来让我们看一个老生常谈的例子，var
b() // call b
console.log(a) // undefined

var a = 'Hello world'

function b() {
    console.log('call b')
}

变量提升
这是因为函数和变量提升的原因。通常提升的解释是说将声明的代码移动到了顶部，
这其实没有什么错误，便于大家理解。但是更准确的解释应该是：
在生成执行环境时，会有两个阶段。第一个阶段是创建的阶段，
JS 解释器会找出需要提升的变量和函数，并且给他们提前在内存中开辟好空间，
函数的话会将整个函数存入内存中，变量只声明并且赋值为 undefined，
所以在第二个阶段，也就是代码执行阶段，我们可以直接提前使用

在提升的过程中，相同的函数会覆盖上一个函数，并且函数优先于变量提升

b() // call b second

function b() {
    console.log('call b fist')
}
function b() {
    console.log('call b second')
}
var b = 'Hello world'
复制代码var 会产生很多错误，所以在 ES6中引入了 let。let 不能在声明前使用，
但是这并不是常说的 let 不会提升，let 提升了，在第一阶段内存也已经为
他开辟好了空间，但是因为这个声明的特性导致了并不能在声明前使用
```

#### 变量提升
- 当执行 JS 代码时，会生成执行环境，只要代码不是写在函数中的，就是在全局执行环境中，函数中的代码会产生函数执行环境，只此两种执行环境。
```
b() // call b
console.log(a) // undefined

var a = 'Hello world'

function b() {
    console.log('call b')
}
```
- 想必以上的输出大家肯定都已经明白了，这是因为函数和变量提升的原因。通常提升的解释是说将声明的代码移动到了顶部，这其实没有什么错误，便于大家理解。但是更准确的解释应该是：在生成执行环境时，会有两个阶段。第一个阶段是创建的阶段，JS 解释器会找出需要提升的变量和函数，并且给他们提前在内存中开辟好空间，函数的话会将整个函数存入内存中，变量只声明并且赋值为 undefined，所以在第二个阶段，也就是代码执行阶段，我们可以直接提前使用
- 在提升的过程中，相同的函数会覆盖上一个函数，并且函数优先于变量提升
```
b() // call b second

function b() {
    console.log('call b fist')
}
function b() {
    console.log('call b second')
}
var b = 'Hello world'
```
- var 会产生很多错误，所以在 ES6中引入了 let。let不能在声明前使用，但是这并不是常说的 let 不会提升，let提升了，在第一阶段内存也已经为他开辟好了空间，但是因为这个声明的特性导致了并不能在声明前使用


### 事件

  #### 事件是什么？IE与火狐的事件机制有什么区别？如何阻止冒泡
```
事件是用户操作网页时发生的交互动作，比如 click/move， 
事件除了用户触发的动作外，还可以是文档加载，窗口滚动和大小调整。
事件被封装成一个 event 对象，包含了该事件发生时的所有相关信息
（ event 的属性）以及可以对事件进行的操作（ event 的方法）。

事件处理机制：IE 支持事件冒泡、Firefox 同时支持两种事件模型，
也就是：事件冒泡和事件捕获。

event.stopPropagation() 或者 ie 下的方法 event.cancelBubble = true;
```

  #### 事件的各个阶段
```
1：捕获阶段 ---> 2：目标阶段 ---> 3：冒泡阶段

document ---> target目标 ----> document

由此，addEventListener的第三个参数设置为true和false的区别已经非常清晰了

true表示该元素在事件的“捕获阶段”（由外往内传递时）响应事件
false表示该元素在事件的“冒泡阶段”（由内向外传递时）响应事件
```

- 事件冒泡
如下代码：
```
<!DOCTYPE html>
<html lang="en">
<head>    
	<meta charset="UTF-8">    
	<meta http-equiv="X-UA-Compatible" content="IE=edge">    
	<meta name="viewport" content="width=device-width, initial-scale=1.0">    
	<title>Document</title>    
	<style>        
		#div1 {            
			height: 300px;            
			width: 300px;            
			background-color: red;        
		}        
		#div2 {            
			height: 200px;            
			width: 200px;            
			background-color: black;        
		}    
	</style>
</head>
<body>    
	<div id="div1">        
		<div id="div2"></div>    
	</div>    
	<script>        
		var div1 = document.getElementById('div1');        
		var div2 = document.getElementById('div2');        
		div1.addEventListener('click', function () {            
			console.log('div1')        
		}, false);        
		div2.addEventListener('click', function () {           
			console.log('div2')        
		}, false);    
	</script>
</body>
</html>

将上述代码在浏览器打开，当点击div2(黑色)元素，会执行其
回调函数打印文字div2，同时也会触发元素div1的回调函数，
打印文字div1。即在冒泡状态下子元素的点击状态会传递给父元素，
一直传递到document对象，这就是事件冒泡。因此上述的点击状态
传递过程为：
div2->div1->body->html->document   由内而外传播
在addEventListener中，第一个参数时事件，第二个
参数时回调函数，第三个参数是决定回调函数执行的环境，
默认为false(在事件冒泡时执行回调函数)。
```

- 事件捕捉
```
事件捕捉与事件冒泡正好相反，只需要将上述事件冒泡代码
两个监听器中第三个参数改为true即可，true代表回调函数
在事件捕捉时执行。改为true之后，点击状态的传递变为如下：
div1->div2    由外而内传播
```

- 事件代理(事件委托)
```
事件代理其实就是利用事件冒泡的原理，
进行一些复杂操作的简化。如下代码：
<ul> 
	<li>1</li>        
	<li>2</li>        
	<li>3</li>        
	<li>4</li>    
</ul>
如果要对ul列表中所有li挂载事件，你可以手动写多个监听器
去监听每一个li。当你在点击某一个li的时候，他的点击状态
也会根据事件冒泡原理传递到ul中，我们可以根据这个原理，
将所有li的事件都委托给ul，即将所有li的监听器只需要挂载
在ul一个元素上即可，这样也能实现相同的效果。如下代码：
<body>    
	<ul>        
		<li>1</li>        
		<li>2</li>        
		<li>3</li>        
		<li>4</li>    
	</ul>    
	<script>        
		var ul = document.getElementsByTagName('ul')[0];        
		ul.addEventListener('click' , function(){            
			console.log('点击了')        
		})    
	</script>
</body>
```

- 阻止事件冒泡和默认事件
```
先看没有阻止事件冒泡和默认事件的代码：
<body>    
	<ul id="ul1">        
		<li id="li1">1</li>    
	</ul>    
	<a href="http://www.baidu.com" id="a">百度</a>    
	<script>        
		var ul = document.getElementById('ul1')        
		var li = document.getElementById('li1');        
		var a = document.getElementById('a');        
		a.addEventListener('click' , function(){            
			console.log('a被点击了')        
		})        
		ul.addEventListener('click' , function(){            
			console.log('ul被点击了')        
		})        
		li.addEventListener('click' ,function(){            
			console.log('li被点击了');        
		})    
	</script>
</body>
此代码大家可以运行一下查看效果，完全点击li会触发
li和ul的回调函数，点击a标签会发生跳转。下面我们来看
一下设置阻止事件冒泡和阻止默认事件的代码：
<body>    
	<ul id="ul1">        
		<li id="li1">1</li>    
	</ul>    
	<a href="http://www.baidu.com" id="a">百度</a>    
	<script>        
		var ul = document.getElementById('ul1')        
		var li = document.getElementById('li1');        
		var a = document.getElementById('a');        
		a.addEventListener('click' , function(e){            
			e.preventDefault()            
			console.log('a被点击了')        
		})        
		ul.addEventListener('click' , function(){            
			console.log('ul被点击了')        
		})        
		li.addEventListener('click' ,function(e){            
			console.log('li被点击了');            
			e.stopPropagation()        
		})    
	</script>
</body>
其中我们在a标签的回调函数中接收事件回调函数并且
获取事件参数e，调用e的preventDefault方法可以将
a标签的调转行为取消。其中我们在li标签的回调函数中
接收事件回调函数并且获取事件参数e，调用e的
stopPropagation函数可以将li的点击冒泡状态取消。
综上，做以下总结：
preventDefault()  取消默认事件  比如a标签、submit按钮
stopPropagation()  取消事件冒泡
```

#### 事件冒泡
1. 事件
- 在浏览器客户端应用平台，基本生都是以事件驱动的，即某个事件发生，然后做出相应的动作。
- 浏览器的事件表示的是某些事情发生的信号。事件的阐述不是本文的重点，尚未了解的朋友，可以访问W3school教程 进行了解，这将有助于更好地理解以下的内容 。

2.冒泡机制
什么是冒泡呢？
- 气泡从水底开始往上升，由深到浅，升到最上面。在上升的过程中，气泡会经过不同深度层次的水。
- 相对应地：这个气泡就相当于我们这里的事件，而水则相当于我们的整个dom树；事件从dom 树的底层 层层往上传递，直至传递到dom的根节点。

简单案例分析
下面通过一个简单的例案例来阐述冒泡原理：
- 定义一个html, 里面有三个简单的dom 元素：div1,div2, span，div2包含span，div1 包含div2；而它们都在body 下： 
```
<body id="body">
	<div id="box1" class="box1">
		<div id="box2" class="box2">
			<span id="span">This is a span.</span>
		</div>
	</div>
</body>
```

在这个基础上，我们实现下面的功能：
- a.body添加 click 事件监听，当body捕获到event事件时，打印出事件发生的时间和 触发事件的节点信息：
```
<script type="text/javascript">
	window.onload = function() {
		document.getElementById("body").addEventListener("click",eventHandler);
	}
	function eventHandler(event) {
		console.log("时间："+new Date(event.timeStamp)+" 产生事件的节点：" + event.target.id +"  当前节点："+event.currentTarget.id);
	}
</script>
```
当我们依次点击"This is span"，div2，div1，body后，输出以下信息：
分析以上的结果：
- 无论是body，body 的子元素div1，还是 div的子元素div2，还有 span, 当这些元素被点击click时，都会产生click事件，并且body都会捕获到，然后调用相应的事件处理函数。就像水中的气泡从底往上冒一样，事件也会往上传递。
- 一般地，事件在传递过程中会有一些信息，这些是事件的组成部分：事件发生的时间+事件发生的地点+ 事件的类型+事件的当前处理者+其他信息，               

完整的html代码如下：
```
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<script type="text/javascript" src="js/jquery-1.11.0.js"></script>
<title>Insert title here</title>
<style type="text/css">
.box1 {
	border: green 40px solid;
	width: 300px;
	height: 300px;
	margin: auto;
}
 
.box2 {
	border: yellow 40px solid;
	width: 220px;
	height: 220px;
	margin: auto;
}
 
span {
	position: relative;
	left: 50px;
	top: 50px;
	background-color: rgba(128, 128, 128, 0.22);
}
</style>
 
<script type="text/javascript">
	window.onload = function() {
		document.getElementById("body").addEventListener("click",eventHandler);
	}
	function eventHandler(event) {
		console.log("时间："+new Date(event.timeStamp)+" 产生事件的节点：" + event.target.id +"  当前节点："+event.currentTarget.id);
	}
</script>
 
</head>
<body id="body">
	<div id="box1" class="box1">
		<div id="box2" class="box2">
			<span id="span">This is a span.</span>
		</div>
	</div>
</body>
</html>
```

  b.终止事件的冒泡
- 我们现在想实现这样的功能，在div1 点击的时候，弹出 "你好，我是最外层div。"，点击div2 的时候，弹出 "你好，我是第二层div"；点击span 的时候，弹出"您好，我是span。"。

由此我们会有下面的javascript片段：
```
<script type="text/javascript">
	window.onload = function() {
		document.getElementById("box1").addEventListener("click",function(event){
			alert("您好，我是最外层div。");
		});
		document.getElementById("box2").addEventListener("click",function(event){
			alert("您好，我是第二层div。");
		});
		document.getElementById("span").addEventListener("click",function(event){
			alert("您好，我是span。");
		});
	}
</script>
```
- 预期上述代码会单击span 的时候，会出来一个弹出框 "您好，我是span。" 是的，确实弹出了这样的对话框：
                                                      
- 然而，不仅仅会产生这个对话框，当点击确定后，会依次弹出下列对话框：

- 这显然不是我们想要的！ 我们希望的是点谁显示谁的信息而已。为什么会出现上述的情况呢？ 原因就在于事件的冒泡，点击span的时候，span 会把产生的事件往上冒泡，作为父节点的div2 和 祖父节点的div1也会收到此事件，于是会做出事件响应，执行响应函数。现在问题是发现了，但是怎么解决呢？

- 方法一：我们来考虑一个形象一点的情况：水中的一个气泡正在从底部往上冒，而你现在在水中，不想让这个气泡往上冒，怎么办呢？——把它扎破！没了气泡，自然不会往上冒了。类似地，对某一个节点而言，如果不想它现在处理的事件继续往上冒泡的话，我们可以终止冒泡：

- 在相应的处理函数内，加入  event.stopPropagation()   ,终止事件的广播分发，这样事件停留在本节点，不会再往外传播了。修改上述的script片段：
```
<script type="text/javascript">
	window.onload = function() {
		document.getElementById("box1").addEventListener("click",function(event){
			alert("您好，我是最外层div。");
			event.stopPropagation();
		});
		document.getElementById("box2").addEventListener("click",function(event){
			alert("您好，我是第二层div。");
			event.stopPropagation();
		});
		document.getElementById("span").addEventListener("click",function(event){
			alert("您好，我是span。");
			event.stopPropagation();
		});
	}
</script>
```
经过这样一段代码，点击不同元素会有不同的提示，不会出现弹出多个框的情况了。

- 方法二：事件包含最初触发事件的节点引用 和 当前处理事件节点的引用，那如果节点只处理自己触发的事件即可,不是自己产生的事件不处理。event.target 引用了产生此event对象的dom 节点，而event.currrentTarget 则引用了当前处理节点，我们可以通过这 两个target 是否相等。

- 比如span 点击事件，产生一个event 事件对象，event.target 指向了span元素，span处理此事件时，event.currentTarget 指向的也是span元素，这时判断两者相等，则执行相应的处理函数。而事件传递给 div2 的时候，event.currentTarget变成 div2，这时候判断二者不相等，即事件不是div2 本身产生的，就不作响应处理逻辑。               
```
<script type="text/javascript">
    window.onload = function() {
        document.getElementById("box1").addEventListener("click",function(event){
            if(event.target == event.currentTarget)
            {
                alert("您好，我是最外层div。");
            }
        });
        document.getElementById("box2").addEventListener("click",function(event){
            if(event.target == event.currentTarget)
            {
                alert("您好，我是第二层div。");
            }
        });
        document.getElementById("span").addEventListener("click",function(event){
            if(event.target == event.currentTarget)
            {
                alert("您好，我是span。");
                
            }
        });
    }
</script>
```

比较：
- 从事件传递上看：方法一在于取消事件冒泡，即当某些节点取消冒泡后，事件不会再传递；方法二在于不阻止冒泡，过滤需要处理的事件，事件处理后还会继续传递；

优缺点：
- 方法一缺点：为了实现点击特定的元素显示对应的信息，方法一要求每个元素的子元素也必须终止事件的冒泡传递，即跟别的元素功能上强关联，这样的方法会很脆弱。比如，如果span 元素的处理函数没有执行冒泡终止，则事件会传到div2 上，这样会造成div2 的提示信息；

- 方法二缺点：方法二为每一个元素都增加了事件监听处理函数，事件的处理逻辑都很相似，即都有判断 if(event.target == event.currentTarget)，这样存在了很大的代码冗余，现在是三个元素还好，当有10几个，上百个又该怎么办呢？

- 还有就是为每一个元素都有处理函数，在一定程度上增加逻辑和代码的复杂度。

- 我们再来分析一下方法二：方法二的原理是 元素收到事件后，判断事件是否符合要求，然后做相应的处理，然后事件继续冒泡往上传递；

- 既然事件是冒泡传递的，那可不可以让某个父节点统一处理事件，通过判断事件的发生地（即事件产生的节点），然后做出相应的处理呢？答案是可以的，下面通过给body 元素添加事件监听，然后通过判断event.target 然后对不同的target产生不同的行为。

将方法二的代码重构一下：
```
<script type="text/javascript">
    window.onload = function() {
        document.getElementById("body").addEventListener("click",eventPerformed);
    }
    function eventPerformed(event) {
        var target = event.target;
        switch (target.id) {
        case "span": 
            alert("您好，我是span。");
            break;
        case "div1":
            alert("您好，我是第二层div。");
            break;
        case "div2":
             alert("您好，我是最外层div。");
            break;
        }
    }
</script>
```
结果会是点击不同的元素，只弹出相符合的提示，不会有多余的提示。

- 通过以上方式，我们把本来每个元素都要有的处理函数，都交给了其祖父节点body 元素来完成了，也就是说，span,div2,div1 将自己的响应逻辑委托给body，让它来完成相应逻辑，自己不实现相应逻辑，这个模式，就是所谓的事件委托。


- 事件冒泡 字如其名 就是会逐层向上的触发，与之相对的是 事件捕获 

首先我们要知道什么是 DOM
- DOM可以理解为是一个树形结构，在DOM模型中，HTML元素是有层次的。当一个HTML元素上产生一个事件时，该事件会在DOM树中元素节点与根节点之间按特定的顺序传播，路径所经过的节点都会收到该事件，这整个传播过程就是DOM事件流。

DOM事件流存在三个阶段：事件捕获阶段、处于目标阶段、事件冒泡阶段。
- 1，事件捕获：当鼠标点击或者触发DOM元素时，浏览器会从根节点由外而内的进行事件传播
- 2，事件冒泡：与事件捕获相反，事件冒泡是由内到外进行事件传播，直到根节点。
- DOM标准事件流的触发的先后顺序为：先捕获再冒泡，即当触发dom事件时，会先进行事件捕获，捕获到事件源之后通过事件传播进行事件冒泡。

常用的冒泡事件的API :
- 1，addEventListener(event, function, useCapture)  设定一个事件监听器，当某一事件发生通过设定的参数执行操作
  - 参数 event 是必须的，表示监听的事件，例如 click, touchstart 等，就是之前不加前缀 on 的事件。
  - 参数 function 是必须的，表示事件触发后调用的函数，可以是外部定义函数，也可以是匿名函数。
  - 参数 useCapture 是选填的，填true或者false，用于描述事件是冒泡还是捕获，true表示捕获，默认的false表示冒泡。

- 2，removeEventListener(event, function, useCapture)  移除 addEventListener() 添加的事件监听
  - 具体参数和  addEventListener(event, function, useCapture)  相同

- 3.stopPropagation() 阻止事件的冒泡  
  - 该函数只阻止事件向祖辈元素的传播，不会阻止该元素自身绑定的其他事件处理函数的函数。

- 4.preventDefault()  取消事件的默认动作

 

事件委托：
- e.target表示在事件冒泡中触发事件的源元素
- event.target.nodeName 　　-- 获取事件触发元素标签name（li,p…）
- event.target.id　　　　　　--  获取事件触发元素id
- event.target.className　　-- 获取事件触发元素classname
- event.target.innerHTML　　-- 获取事件触发元素的内容（li）



  #### 事件“捕获”和“冒泡”执行顺序和事件的执行次数
```
按照W3C标准的事件：首是进入捕获阶段，直到达到目标元素，再进入冒泡阶段

事件执行次数（DOM2-addEventListener）：元素上绑定事件的个数
    注意1：前提是事件被确实触发
    注意2：事件绑定几次就算几个事件，即使类型和功能完全一样也不会“覆盖”
   
事件执行顺序：判断的关键是否目标元素
    1.非目标元素：根据W3C的标准执行：捕获->目标元素->冒泡
    （不依据事件绑定顺序）
    2.目标元素：依据事件绑定顺序：先绑定的事件先执行（不依据捕获冒泡标准）
    3.最终顺序：父元素捕获->目标元素事件1->目标元素事件2->子元素捕获->
    子元素冒泡->父元素冒泡
    
    注意：子元素事件执行前提 事件确实“落”到子元素布局区域上，
    而不是简单的具有嵌套关系
```

  #### 在一个DOM上同时绑定两个点击事件：一个用捕获，一个用冒泡。事件会执行几次，先执行冒泡还是捕获
```
该DOM上的事件如果被触发，会执行两次（执行次数等于绑定次数）
如果该DOM是目标元素，则按事件绑定顺序执行，不区分冒泡/捕获
如果该DOM是处于事件流中的非目标元素，则先执行捕获，后执行冒泡
```

  #### 如何派发事件(dispatchEvent)？（如何进行事件广播？）
```
W3C: 使用 dispatchEvent 方法
IE: 使用 fireEvent 方法
var fireEvent = function(element, event){
    if (document.createEventObject){
        var mockEvent = document.createEventObject();
        return element.fireEvent('on' + event, mockEvent)
    }else{
        var mockEvent = document.createEvent('HTMLEvents');
        mockEvent.initEvent(event, true, true);
        return !element.dispatchEvent(mockEvent);
    }
}
```

  #### 事件代理
```
事件代理（Event Delegation），又称之为事件委托。是 JavaScript 中常用
绑定事件的常用技巧。顾名思义，“事件代理”即是把原本需要绑定的事件委托给
父元素，让父元素担当事件监听的职务。事件代理的原理是DOM元素的事件冒泡。
使用事件代理的好处是可以提高性能

可以大量节省内存占用，减少事件注册，
比如在table上代理所有td的click事件就非常棒

可以实现当新增子对象时无需再次对其绑定
```

  #### 三种事件模型是什么
```
事件是用户操作网页时发生的交互动作或者网页本身的一些操作，
现代浏览器一共有三种事件模型。

第一种事件模型是最早的 DOM0 级模型，这种模型不会传播，
所以没有事件流的概念，但是现在有的浏览器支持以冒泡的方式实现，
它可以在网页中直接定义监听函数，也可以通过 js 属性来指定监听函数。
这种方式是所有浏览器都兼容的。

第二种事件模型是 IE 事件模型，在该事件模型中，一次事件共有两个过程，
事件处理阶段，和事件冒泡阶段。事件处理阶段会首先执行目标元素绑定的
监听事件。然后是事件冒泡阶段，冒泡指的是事件从目标元素冒泡到 document，
依次检查经过的节点是否绑定了事件监听函数，如果有则执行。这种模型通过 attachEvent 来添加监听函数，可以添加多个监听函数，会按顺序依次执行。

第三种是 DOM2 级事件模型，在该事件模型中，一次事件共有三个过程，
第一个过程是事件捕获阶段。捕获指的是事件从 document 一直向下传播到
目标元素，依次检查经过的节点是否绑定了事件监听函数，如果有则执行。
后面两个阶段和 IE 事件模型的两个阶段相同。这种事件模型，
事件绑定的函数是 addEventListener，其中第三个参数可以指定事件
是否在捕获阶段执行。
```

```
W3C中定义事件的发生经历三个阶段：捕获阶段（capturing）、
目标阶段（targetin）、冒泡阶段（bubbling）

冒泡型事件：当你使用事件冒泡时，子级元素先触发，父级元素后触发

捕获型事件：当你使用事件捕获时，父级元素先触发，子级元素后触发

DOM事件流：同时支持两种事件模型：捕获型事件和冒泡型事件

阻止冒泡：在W3c中，使用stopPropagation()方法；
在IE下设置cancelBubble = true

阻止捕获：阻止事件的默认行为，例如click - <a>后的跳转。
在W3c中，使用preventDefault()方法，
在IE下设置window.event.returnValue = false
```

  #### 事件委托
```
事件委托本质上是利用了浏览器事件冒泡的机制。因为事件在冒泡过程中会
上传到父节点，并且父节点可以通过事件对象获取到
目标节点，因此可以把子节点的监听函数定义在父节点上，由父节点的
监听函数统一处理多个子元素的事件，这种方式称为事件代理。

使用事件代理我们可以不必要为每一个子元素都绑定一个监听事件，这样减少了
内存上的消耗。并且使用事件代理我们还可以实现事件的动态绑定，比如说
新增了一个子节点，我们并不需要单独地为它添加一个监听事件，
它所发生的事件会交给父元素中的监听函数来处理。
```

  #### js的事件循环是什么
```
事件队列是一个存储着待执行任务的队列，其中的任务严格按照时间先后顺序
执行，排在队头的任务将会率先执行，而排在队尾的任务会最后执行。
事件队列每次仅执行一个任务，在该任务执行完毕之后，再执行下一个任务。
执行栈则是一个类似于函数调用栈的运行容器，当执行栈为空时，
JS 引擎便检查事件队列，如果不为空的话，
事件队列便将第一个任务压入执行栈中运行。
```

```
因为 js 是单线程运行的，在代码执行的时候，通过将不同函数的执行上下文
压入执行栈中来保证代码的有序执行。在执行同步代码的时候，如果遇到了
异步事件，js 引擎并不会一直等待其返回结果，而是会将这个事件挂起，
继续执行执行栈中的其他任务。当异步事件执行完毕后，再将异步事件对应的
回调加入到与当前执行栈中不同的另一个任务队列中等待执行。任务队列可以
分为宏任务对列和微任务对列，当当前执行栈中的事件执行完毕后，js 引擎
首先会判断微任务对列中是否有任务可以执行，如果有就将微任务队首的事件
压入栈中执行。当微任务对列中的任务都执行完成后再去判断宏任务对列中的任务。

微任务包括了 promise 的回调、node 中的 process.nextTick 、
对 Dom 变化监听的 MutationObserver。

宏任务包括了 script 脚本的执行、setTimeout ，setInterval ，
setImmediate 一类的定时事件，还有如 I/O 操作、UI 渲染等。
```

  #### 事件流
```
事件流分为两种，捕获事件流和冒泡事件流

捕获事件流从根节点开始执行，一直往子节点查找执行，直到查找执行到目标节点

冒泡事件流从目标节点开始执行，一直往父节点冒泡查找执行，直到查到到根节点

事件流分为三个阶段，一个是捕获节点，
一个是处于目标节点阶段，一个是冒泡阶段
```

  #### JS事件轮询机制
```
js是单线程语言，所以在同一时间，执行栈里边只能有
一个代码运行，而在我们的js文件中有同步代码，
也会有异步代码。执行栈会首先执行全部的同步代码，
等同步代码执行完毕执行栈空了，才回去执行异步代码。
在异步代码执行的时候，也会产生一部分同步代码，
那么优先也会执行这一部分同步代码，再去执行
其他异步代码。所以我们的执行栈总是在同步代码与
异步代码之间进行切换，这就是js事件轮询机制的理解。

同步代码执行的顺序就是他们在js文件中写的位置先后，
但是异步代码却不一定，比如在异步队列中有两个
延时器，第一个延时器延迟为2s，第二个延时器延迟
为1s，虽然在异步队列中第一个延时器排名靠前，
但是由于他的等待时间常，所以它要在第二个延时器的
回调函数执行完，才能执行自己的回调函数。关于异步队列
如何执行的问题，js引入了宏微任务的机制，下面我们
先看一下在浏览器异步代码中，哪些是宏任务，哪些是微任务。
```

  #### 写一个通用的事件侦听器函数
```js
const EventUtils = {
  // 视能力分别使用dom0||dom2||IE方式 来绑定事件
  // 添加事件
  addEvent: function(element, type, handler) {
    if (element.addEventListener) {
      element.addEventListener(type, handler, false);
    } else if (element.attachEvent) {
      element.attachEvent("on" + type, handler);
    } else {
      element["on" + type] = handler;
    }
  },

  // 移除事件
  removeEvent: function(element, type, handler) {
    if (element.removeEventListener) {
      element.removeEventListener(type, handler, false);
    } else if (element.detachEvent) {
      element.detachEvent("on" + type, handler);
    } else {
      element["on" + type] = null;
    }
  },

  // 获取事件目标
  getTarget: function(event) {
    return event.target || event.srcElement;
  },

  // 获取 event 对象的引用，取到事件的所有信息，确保随时能使用 event
  getEvent: function(event) {
    return event || window.event;
  },

  // 阻止事件（主要是事件冒泡，因为 IE 不支持事件捕获）
  stopPropagation: function(event) {
    if (event.stopPropagation) {
      event.stopPropagation();
    } else {
      event.cancelBubble = true;
    }
  },

  // 取消事件的默认行为
  preventDefault: function(event) {
    if (event.preventDefault) {
      event.preventDefault();
    } else {
      event.returnValue = false;
    }
  }
};
```

  #### 移动端的点击事件的有延迟，时间是多久，为什么会有？怎么解决这个延时
```
移动端点击有 300ms 的延迟是因为移动端会有双击缩放的这个操作，
因此浏览器在 click 之后要等待 300ms，看用户有没有下一次点击，
来判断这次操作是不是双击。

有三种办法来解决这个问题：
1.通过 meta 标签禁用网页的缩放。
2.通过 meta 标签将网页的 viewport 设置为 ideal viewport。
3.调用一些 js 库，比如 FastClick

click 延时问题还可能引起点击穿透的问题，就是如果我们在一个元素上
注册了 touchStart 的监听事件，这个事件会将这个元素隐藏掉，
我们发现当这个元素隐藏后，触发了这个元素下的一个元素的点击事件，
这就是点击穿透。
```


### 浏览器

  #### 从输入URL到看到页面发生的全过程
```
首先浏览器主进程接管，开了一个下载线程。

然后进行HTTP请求（DNS查询、IP寻址等等），中间会有三次捂手，
等待响应，开始下载响应报文。

将下载完的内容转交给Renderer进程管理。

Renderer进程开始解析css rule tree和dom tree，
这两个过程是并行的，所以一般我会把link标签放在页面顶部。

解析绘制过程中，当浏览器遇到link标签或者script、
img等标签，浏览器会去下载这些内容，遇到时候缓存的使用缓存，
不适用缓存的重新下载资源。

css rule tree和dom tree生成完了之后，开始合成render tree，
这个时候浏览器会进行layout，开始计算每一个节点的位置，然后进行绘制。

绘制结束后，关闭TCP连接，过程有四次挥手
```

基础版本
```
浏览器根据请求的URL交给DNS域名解析，找到真实IP，向服务器发起请求；
服务器交给后台处理完成后返回数据，浏览器接收文件（HTML、JS、CSS、图象等）；
浏览器对加载到的资源（HTML、JS、CSS等）进行语法解析，建立相应的内部数据结构（如HTML的DOM）；
载入解析到的资源文件，渲染页面，完成。
```

详细版
```
1.在浏览器地址栏输入URL
2.浏览器查看缓存，如果请求资源在缓存中并且新鲜，跳转到转码步骤
  (1)如果资源未缓存，发起新请求
  (2)如果已缓存，检验是否足够新鲜，足够新鲜直接提供给客户端，否则与服务器进行验证。
  (3)检验新鲜通常有两个HTTP头进行控制Expires和Cache-Control：
      HTTP1.0提供Expires，值为一个绝对时间表示缓存新鲜日期
      HTTP1.1增加了Cache-Control: max-age=,值为以秒为单位的最大新鲜时间
3.浏览器解析URL获取协议，主机，端口，path
4.浏览器组装一个HTTP（GET）请求报文
5.浏览器获取主机ip地址，过程如下：
  (1)浏览器缓存
  (2)本机缓存
  (3)hosts文件
  (4)路由器缓存
  (5)ISP DNS缓存
  (6)DNS递归查询（可能存在负载均衡导致每次IP不一样）
6.打开一个socket与目标IP地址，端口建立TCP链接，三次握手如下：
  (1)客户端发送一个TCP的SYN=1，Seq=X的包到服务器端口
  (2)服务器发回SYN=1， ACK=X+1， Seq=Y的响应包
  (3)客户端发送ACK=Y+1， Seq=Z
7.TCP链接建立后发送HTTP请求
8.服务器接受请求并解析，将请求转发到服务程序，如虚拟主机使用HTTP Host头部判断请求的服务程序
9.服务器检查HTTP请求头是否包含缓存验证信息如果验证缓存新鲜，返回304等对应状态码
10.处理程序读取完整请求并准备HTTP响应，可能需要查询数据库等操作
11.服务器将响应报文通过TCP连接发送回浏览器
12.浏览器接收HTTP响应，然后根据情况选择关闭TCP连接或者保留重用，关闭TCP连接的四次握手如下：
  (1)主动方发送Fin=1， Ack=Z， Seq= X报文
  (2)被动方发送ACK=X+1， Seq=Z报文
  (3)被动方发送Fin=1， ACK=X， Seq=Y报文
  (4)主动方发送ACK=Y， Seq=X报文
13.浏览器检查响应状态吗：是否为1XX，3XX， 4XX， 5XX，这些情况处理与2XX不同
14.如果资源可缓存，进行缓存
15.对响应进行解码（例如gzip压缩）
16.根据资源类型决定如何处理（假设资源为HTML文档）
17.解析HTML文档，构件DOM树，下载资源，构造CSSOM树，执行js脚本，这些操作没有严格的先后顺序，以下分别解释
18.构建DOM树：
  (1)Tokenizing：根据HTML规范将字符流解析为标记
  (2)Lexing：词法分析将标记转换为对象并定义属性和规则
  (3)DOM construction：根据HTML标记关系将对象组成DOM树
19.解析过程中遇到图片、样式表、js文件，启动下载
20.构建CSSOM树：
  (1)Tokenizing：字符流转换为标记流
  (2)Node：根据标记创建节点
  (3)CSSOM：节点创建CSSOM树
21.根据DOM树和CSSOM树构建渲染树 (opens new window):
  (1)从DOM树的根节点遍历所有可见节点，不可见节点包括：1）script,meta这样本身不可见的标签。2)被css隐藏的节点，如display: none
  (2)对每一个可见节点，找到恰当的CSSOM规则并应用
  (3)发布可视节点的内容和计算样式
22.js解析如下：
  (1)浏览器创建Document对象并解析HTML，将解析到的元素和文本节点添加到文档中，此时document.readystate为loading
  (2)HTML解析器遇到没有async和defer的script时，将他们添加到文档中，然后执行行内或外部脚本。
  这些脚本会同步执行，并且在脚本下载和执行时解析器会暂停。这样就可以用document.write()把文本插入到输入流中。
  同步脚本经常简单定义函数和注册事件处理程序，他们可以遍历和操作script和他们之前的文档内容
  (3)当解析器遇到设置了async属性的script时，开始下载脚本并继续解析文档。脚本会在它下载完成后尽快执行，
  但是解析器不会停下来等它下载。异步脚本禁止使用document.write()，它们可以访问自己script和之前的文档元素
  (4)当文档完成解析，document.readState变成interactive
  (5)所有defer脚本会按照在文档出现的顺序执行，延迟脚本能访问完整文档树，禁止使用document.write()
  (6)浏览器在Document对象上触发DOMContentLoaded事件
  (7)此时文档完全解析完成，浏览器可能还在等待如图片等内容加载，等这些内容完成载入并且
  所有异步脚本完成载入和执行，document.readState变为complete，window触发load事件
23.显示页面（HTML解析过程中会逐步显示页面）
```

详细简版
```
1.从浏览器接收url到开启网络请求线程（这一部分可以展开浏览器的机制以及进程与线程之间的关系）
2.开启网络线程到发出一个完整的HTTP请求（这一部分涉及到dns查询，TCP/IP请求，五层因特网协议栈等知识）
3.从服务器接收到请求到对应后台接收到请求（这一部分可能涉及到负载均衡，安全拦截以及后台内部的处理等等）
4.后台和前台的HTTP交互（这一部分包括HTTP头部、响应码、报文结构、cookie等知识，可以提下静态资源的cookie优化，以及编码解码，如gzip压缩等）
5.单独拎出来的缓存问题，HTTP的缓存（这部分包括http缓存头部，ETag，catch-control等）
6.浏览器接收到HTTP数据包后的解析流程（解析html-词法分析然后解析成dom树、解析css生成css规则树、合并成render树，
  然后layout、painting渲染、复合图层的合成、GPU绘制、外链资源的处理、loaded和DOMContentLoaded等）
7.CSS的可视化格式模型（元素的渲染规则，如包含块，控制框，BFC，IFC等概念）
8.JS引擎解析过程（JS的解释阶段，预处理阶段，执行阶段生成执行上下文，VO，作用域链、回收机制等等）
9.其它（可以拓展不同的知识模块，如跨域，web安全，hybrid模式等等内容）
```


  #### 浏览器的渲染过程，DOM树和渲染树的区别
```
浏览器的渲染过程：

解析HTML构建 DOM(DOM树)，并行请求 css/image/js
CSS 文件下载完成，开始构建 CSSOM(CSS树)
CSSOM 构建结束后，和 DOM 一起生成 Render Tree(渲染树)
布局(Layout)：计算出每个节点在屏幕中的位置
显示(Painting)：通过显卡把页面画到屏幕上
DOM树 和 渲染树 的区别：

DOM树与HTML标签一一对应，包括head和隐藏元素
渲染树不包括head和隐藏元素，大段文本的每一个行都是独立节点，
每一个节点都有对应的css属性
```

  #### 浏览器的缓存机制
```
浏览器的缓存机制指的是通过在一段时间内保留已接收到的 web 资源
的一个副本，如果在资源的有效时间内，发起了对这个资源的再一次请求，
那么浏览器会直接使用缓存的副本，而不是向服务器发起请求。使用 
web 缓存可以有效地提高页面的打开速度，减少不必要的网络带宽的消耗。

web 资源的缓存策略一般由服务器来指定，可以分为两种，
分别是强缓存策略和协商缓存策略。

使用强缓存策略时，如果缓存资源有效，则直接使用缓存资源，
不必再向服务器发起请求。强缓存策略可以通过两种方式来设置，
分别是 http 头信息中的 Expires 属性和 Cache-Control 属性。

服务器通过在响应头中添加 Expires 属性，来指定资源的过期时间。
在过期时间以内，该资源可以被缓存使用，不必再向服务器发送请求。
这个时间是一个绝对时间，它是服务器的时间，因此可能存在这样的问题，
就是客户端的时间和服务器端的时间不一致，或者用户可以对客户端
时间进行修改的情况，这样就可能会影响缓存命中的结果。

Expires 是 http1.0 中的方式，因为它的一些缺点，在 http 1.1 
中提出了一个新的头部属性就是 Cache-Control 属性，
它提供了对资源的缓存的更精确的控制。它有很多不同的值，
常用的比如我们可以通过设置 max-age 来指定资源能够被缓存的时间
的大小，这是一个相对的时间，它会根据这个时间的大小和资源第一次
请求时的时间来计算出资源过期的时间，因此相对于 Expires来说，
这种方式更加有效一些。常用的还有比如 private ，用来规定资源
只能被客户端缓存，不能够代理服务器所缓存。还有如 no-store ，
用来指定资源不能够被缓存，no-cache 代表该资源能够被缓存，
但是立即失效，每次都需要向服务器发起请求。

一般来说只需要设置其中一种方式就可以实现强缓存策略，
当两种方式一起使用时，Cache-Control 的优先级要高于 Expires 。

使用协商缓存策略时，会先向服务器发送一个请求，如果资源
没有发生修改，则返回一个 304 状态，让浏览器使用本地的缓存副本。
如果资源发生了修改，则返回修改后的资源。协商缓存也可以通过两种
方式来设置，分别是 http 头信息中的 Etag 和 Last-Modified 属性。

服务器通过在响应头中添加 Last-Modified 属性来指出资源最后一次
修改的时间，当浏览器下一次发起请求时，会在请求头中添加一个 
If-Modified-Since 的属性，属性值为上一次资源返回时的 Last-Modified 
的值。当请求发送到服务器后服务器会通过这个属性来和资源的最后一次
的修改时间来进行比较，以此来判断资源是否做了修改。如果资源没有修改，
那么返回 304 状态，让客户端使用本地的缓存。如果资源已经被修改了，
则返回修改后的资源。使用这种方法有一个缺点，就是 Last-Modified 
标注的最后修改时间只能精确到秒级，如果某些文件在1秒钟以内，
被修改多次的话，那么文件已将改变了但是 Last-Modified 却没有改变，
这样会造成缓存命中的不准确。

因为 Last-Modified 的这种可能发生的不准确性，http 中提供了
另外一种方式，那就是 Etag 属性。服务器在返回资源的时候，
在头信息中添加了 Etag 属性，这个属性是资源生成的唯一标识符，
当资源发生改变的时候，这个值也会发生改变。在下一次资源请求时，
浏览器会在请求头中添加一个 If-None-Match 属性，这个属性的值
就是上次返回的资源的 Etag 的值。服务接收到请求后会根据这个值
来和资源当前的 Etag 的值来进行比较，以此来判断资源是否发生改变，
是否需要返回资源。通过这种方式，比 Last-Modified 的方式更加精确。

当 Last-Modified 和 Etag 属性同时出现的时候，Etag 的优先级更高。
使用协商缓存的时候，服务器需要考虑负载平衡的问题，因此多个服务器上
资源的 Last-Modified 应该保持一致，因为每个服务器上 Etag 的值
都不一样，因此在考虑负载平衡时，最好不要设置 Etag 属性。

强缓存策略和协商缓存策略在缓存命中时都会直接使用本地的缓存副本，
区别只在于协商缓存会向服务器发送一次请求。它们缓存不命中时，
都会向服务器发送请求来获取资源。在实际的缓存机制中，强缓存策略
和协商缓存策略是一起合作使用的。浏览器首先会根据请求的信息判断，
强缓存是否命中，如果命中则直接使用资源。如果不命中则根据头信息
向服务器发起请求，使用协商缓存，如果协商缓存命中的话，则服务器
不返回资源，浏览器直接使用本地资源的副本，如果协商缓存不命中，
则浏览器返回最新的资源给浏览器。
```

```
浏览器缓存分为强缓存和协商缓存。当客户端请求某个资源时，
获取缓存的流程如下：

(1)先根据这个资源的一些 http header 判断它是否命中强缓存，
如果命中，则直接从本地获取缓存资源，不会发请求到服务器；
(2)当强缓存没有命中时，客户端会发送请求到服务器，服务器通过另一些
request header验证这个资源是否命中协商缓存，称为http再验证，
如果命中，服务器将请求返回，但不返回资源，而是告诉客户端直接
从缓存中获取，客户端收到返回后就会从缓存中获取资源；
(3)强缓存和协商缓存共同之处在于，如果命中缓存，服务器都不会返回资源；
区别是，强缓存不对发送请求到服务器，但协商缓存会。
(4)当协商缓存也没命中时，服务器就会将资源发送回客户端。
(5)当 ctrl+f5 强制刷新网页时，直接从服务器加载，跳过强缓存和协商缓存；
(6)当 f5刷新网页时，跳过强缓存，但是会检查协商缓存；

强缓存：
(1)Expires（该字段是 http1.0 时的规范，值为一个绝对时间的 GMT 
格式的时间字符串，代表缓存资源的过期时间）
(2)Cache-Control:max-age（该字段是 http1.1的规范，强缓存利用其 
max-age 值来判断缓存资源的最大生命周期，它的值单位为秒）

协商缓存：
(1)Last-Modified（值为资源最后更新时间，随服务器response返回）
(2)If-Modified-Since（通过比较两个时间来判断资源在两次请求期间
是否有过修改，如果没有修改，则命中协商缓存）
(3)ETag（表示资源内容的唯一标识，随服务器response返回）
(4)If-None-Match（服务器通过比较请求头部的If-None-Match
与当前资源的ETag是否一致来判断资源是否在两次请求之间有过修改，
如果没有修改，则命中协商缓存）
```

```
浏览器缓存机制有两种，一种为强缓存，一种为协商缓存

(1)对于强缓存，浏览器在第一次请求的时候，会直接下载资源，
然后缓存在本地，第二次请求的时候，直接使用缓存。
(2)对于协商缓存，第一次请求缓存且保存缓存标识与时间，
重复请求向服务器发送缓存标识和最后缓存时间，
服务端进行校验，如果失效则使用缓存

协商缓存相关设置：
Exprires：服务端的响应头，第一次请求的时候，告诉客户端，
该资源什么时候会过期。Exprires的缺陷是必须保证服务端时间和
客户端时间严格同步。

Cache-control：max-age：表示该资源多少时间后过期，
解决了客户端和服务端时间必须同步的问题，

If-None-Match/ETag：缓存标识，对比缓存时使用它来标识一个缓存，
第一次请求的时候，服务端会返回该标识给客户端，客户端在第二次请求
的时候会带上该标识与服务端进行对比并返回If-None-Match标识是否表示匹配。

Last-modified/If-Modified-Since：第一次请求的时候服务端返回
Last-modified表明请求的资源上次的修改时间，第二次请求的时候客户端
带上请求头If-Modified-Since，表示资源上次的修改时间，
服务端拿到这两个字段进行对比
```

  #### Ajax解决浏览器缓存问题
```
在 ajax 发送请求前加上 
anyAjaxObj.setRequestHeader("If-Modified-Since","0")。

在 ajax 发送请求前加上 
anyAjaxObj.setRequestHeader("Cache-Control","no-cache")。

在 URL 后面加上一个随机数： "fresh=" + Math.random();。

在 URL 后面加上时间戳："nowtime=" + new Date().getTime();。

如果是使用 jQuery，直接这样就可以了\$.ajaxSetup({cache:false})。
这样页面的所有 ajax 都会执行这条语句就是不需要保存缓存记录。
```

  #### 常见兼容性问题
```
png24位的图片在iE6浏览器上出现背景，解决方案是做成PNG8

浏览器默认的margin和padding不同。解决方案是加一个全局的*
{margin:0;padding:0;}来统一,，但是全局效率很低，一般是如下这样解决：
body,ul,li,ol,dl,dt,dd,form,input,h1,h2,h3,h4,h5,h6,p{
margin:0;
padding:0;
}

IE下,event对象有x,y属性,但是没有pageX,pageY属性

Firefox下,event对象有pageX,pageY属性,但是没有x,y属性.
```

  #### 请求方式

   #### get和post请求在缓存方面的区别
```
缓存一般只适用于那些不会更新服务端数据的请求。一般 get 请求都是
查找请求，不会对服务器资源数据造成修改，而 post 请求一般都会对
服务器数据造成修改，所以，一般会对 get 请求进行缓存，
很少会对 post 请求进行缓存。
```

```
get 请求类似于查找的过程，用户获取数据，可以不用每次都与
数据库连接，所以可以使用缓存。

post 不同，post 做的一般是修改和删除的工作，所以必须与
数据库交互，所以不能使用缓存。因此 get 请求适合于请求缓存。
```

   #### get请求传参长度的误区
```
误区：我们经常说 get 请求参数的大小存在限制，
而 post 请求的参数大小是无限制的。

实际上 HTTP 协议从未规定 GET/POST 的请求长度限制是多少。
对 get 请求参数的限制是来源与浏览器或web 服务器，
浏览器或 web 服务器限制了 url 的长度。
为了明确这个概念，我们必须再次强调下面几点:

1.HTTP 协议未规定 GET 和 POST 的长度限制
2.GET 的最大长度显示是因为浏览器和 web 服务器限制了 URI 的长度
3.不同的浏览器和 WEB 服务器，限制的最大长度不一样
4.要支持 IE，则最大长度为 2083byte，若只支持 Chrome，
则最大长度 8182byte
```

  #### 检测浏览器版本版本有哪些方式
```
检测浏览器版本一共有两种方式：

一种是检测 window.navigator.userAgent 的值，但这种方式很不可靠，
因为 userAgent 可以被改写，并且早期的浏览器如 ie，
会通过伪装自己的 userAgent 的值为 Mozilla 来躲过服务器的检测。

第二种方式是功能检测，根据每个浏览器独有的特性来进行判断，
如 ie 下独有的 ActiveXObject。
```

```
根据 navigator.userAgent UA.toLowerCase().indexOf('chrome')
根据 window 对象的成员 'ActiveXObject' in window
```

  #### 把script标签放在页面的最底部的body封闭之前和封闭之后有什么区别？浏览器会如何解析它们
```
按照HTML标准，在</body>结束后出现<script>或任何元素的
开始标签，都是解析错误

虽然不符合HTML标准，但浏览器会自动容错，使实际效果与写在
</body>之前没有区别

浏览器的容错机制会忽略<script>之前的</body>，视作<script>
仍在 body 体内。省略</body>和</html>闭合标签符合HTML标准，
服务器可以利用这一标准尽可能少输出内容
```

  #### script的位置是否会影响首屏显示时间
```
在解析 HTML 生成 DOM 过程中，js 文件的下载是并行的，
不需要 DOM 处理到 script 节点。因此，script的位置
不影响首屏显示的开始时间。

浏览器解析 HTML 是自上而下的线性过程，
script作为 HTML 的一部分同样遵循这个原则

因此，script 会延迟 DomContentLoad，只显示其上部分首屏内容，
从而影响首屏显示的完成时间
```

  #### 实现一个页面操作不会整页刷新的网站，并且能在浏览器前进、后退时正确响应。给出你的技术实现方案
```
通过使用 pushState + ajax 实现浏览器无刷新前进后退，当一次 ajax 
调用成功后我们将一条 state 记录加入到 history对象中。一条 state 
记录包含了 url、title 和 content 属性，在 popstate 事件中可以
获取到这个 state 对象，我们可以使用 content 来传递数据。最后我们
通过对 window.onpopstate 事件监听来响应浏览器的前进后退操作。

使用 pushState 来实现有两个问题，一个是打开首页时没有记录，我们可以
使用 replaceState 来将首页的记录替换，另一个问题是当一个页面刷新
的时候，仍然会向服务器端请求数据，因此如果请求的 url 需要后端的配合
将其重定向到一个页面。
```

  #### 如何检测浏览器所支持的最小字体大小
```
用 JS 设置 DOM 的字体为某一个值，然后再取出来，
如果值设置成功，就说明支持。
```

  #### 开发中常用的几种Content-Type
```
（1）application/x-www-form-urlencoded
浏览器的原生 form 表单，如果不设置 enctype 属性，那么最终就会以 application/x-www-form-urlencoded 方式提交数据。该种方式提交的
数据放在 body 里面，数据按照 key1=val1&key2=val2 的方式进行编码，
key 和 val 都进行了 URL转码。

（2）multipart/form-data
该种方式也是一个常见的 POST 提交方式，通常表单上传文件时使用该种方式。

（3）application/json
告诉服务器消息主体是序列化后的 JSON 字符串。

（4）text/xml
该种方式主要用来提交 XML 格式的数据。
```

  #### 如何判断当前脚本运行在浏览器还是node环境中？（阿里）
```
this === window ? 'browser' : 'node';

通过判断 Global 对象是否为 window，如果不为 window，
当前脚本没有运行在浏览器中。
```

  #### V8引擎的垃圾回收机制
```
v8 的垃圾回收机制基于分代回收机制，这个机制又基于世代假说，
这个假说有两个特点，一是新生的对象容易早死，另一个是不死的对象
会活得更久。基于这个假说，v8 引擎将内存分为了新生代和老生代。

新创建的对象或者只经历过一次的垃圾回收的对象被称为新生代。
经历过多次垃圾回收的对象被称为老生代。

新生代被分为 From 和 To 两个空间，To 一般是闲置的。当 From 空间
满了的时候会执行 Scavenge 算法进行垃圾回收。当我们执行垃圾回收算法
的时候应用逻辑将会停止，等垃圾回收结束后再继续执行。这个算法分为三步：
（1）首先检查 From 空间的存活对象，如果对象存活则判断对象
是否满足晋升到老生代的条件，如果满足条件则晋升到老生代。
如果不满足条件则移动 To 空间。

（2）如果对象不存活，则释放对象的空间。

（3）最后将 From 空间和 To 空间角色进行交换。

新生代对象晋升到老生代有两个条件：
（1）第一个是判断是对象否已经经过一次 Scavenge 回收。
若经历过，则将对象从 From 空间复制到老生代中；若没有经历，
则复制到 To 空间。

（2）第二个是 To 空间的内存使用占比是否超过限制。当对象从 From 
空间复制到 To 空间时，若 To 空间使用超过 25%，则对象直接晋升到
老生代中。设置 25% 的原因主要是因为算法结束后，两个空间结束后会
交换位置，如果 To 空间的内存太小，会影响后续的内存分配。

老生代采用了标记清除法和标记压缩法。标记清除法首先会对内存中存活的
对象进行标记，标记结束后清除掉那些没有标记的对象。由于标记清除后
会造成很多的内存碎片，不便于后面的内存分配。所以了解决内存碎片
的问题引入了标记压缩法。

由于在进行垃圾回收的时候会暂停应用的逻辑，对于新生代方法由于内存小，
每次停顿的时间不会太长，但对于老生代来说每次垃圾回收的时间长，
停顿会造成很大的影响。 为了解决这个问题 V8 引入了增量标记的方法，
将一次停顿进行的过程分为了多步，每次执行完一小步就让运行逻辑
执行一会，就这样交替运行。
```

  #### 垃圾回收
```
找出那些不再继续使用的变 量，然后释放其占用的内存。为此，
垃圾收集器会按照固定的时间间隔(或代码执行中预定的收集时间)， 
周期性地执行这一操作。

标记清除：
先所有都加上标记，再把环境中引用到的变量去除标记。剩下的就是没用的了

引用计数：
跟踪记录每 个值被引用的次数。清除引用次数为0的变量会有循环引用问题 。
循环引用如果大量存在就会导致内存泄露。
```

  #### Javascript垃圾回收方法
```
标记清除（mark and sweep）：
这是JavaScript最常见的垃圾回收方式，当变量进入执行环境的时候，
比如函数中声明一个变量，垃圾回收器将其标记为“进入环境”，
当变量离开环境的时候（函数执行结束）将其标记为“离开环境”

垃圾回收器会在运行的时候给存储在内存中的所有变量加上标记，
然后去掉环境中的变量以及被环境中变量所引用的变量（闭包），
在这些完成之后仍存在标记的就是要删除的变量了

引用计数(reference counting)：
在低版本IE中经常会出现内存泄露，很多时候就是因为其采用引用
计数方式进行垃圾回收。引用计数的策略是跟踪记录每个值被使用的次数，
当声明了一个 变量并将一个引用类型赋值给该变量的时候这个值的
引用次数就加1，如果该变量的值变成了另外一个，则这个值得引用次数减1，
当这个值的引用次数变为0的时 候，说明没有变量在使用，这个值没法
被访问了，因此可以将其占用的空间回收，这样垃圾回收器会在运行的
时候清理掉引用次数为0的值占用的空间
```

JavaScript垃圾回收机制的了解
- 对于在JavaScript中的字符串，对象，数组是没有固定大小的，只有当对他们进行动态分配存储时，解释器就会分配内存来存储这些数据，当JavaScript的解释器消耗完系统中所有可用的内存时，就会造成系统崩溃。
- 内存泄漏，在某些情况下，不再使用到的变量所占用内存没有及时释放，导致程序运行中，内存越占越大，极端情况下可以导致系统崩溃，服务器宕机。
- JavaScript有自己的一套垃圾回收机制，JavaScript的解释器可以检测到什么时候程序不再使用这个对象了（数据），就会把它所占用的内存释放掉。
- 针对JavaScript的来及回收机制有以下两种方法（常用）：标记清除，引用计数
- 标记清除

  #### URL和URI的区别
```
URI: Uniform Resource Identifier      指的是统一资源标识符
URL: Uniform Resource Location        指的是统一资源定位符
URN: Universal Resource Name          指的是统一资源名称

URI 指的是统一资源标识符，用唯一的标识来确定一个资源，
它是一种抽象的定义，也就是说，不管使用什么方法来定义，
只要能唯一的标识一个资源，就可以称为 URI。

URL 指的是统一资源定位符，URN 指的是统一资源名称。
URL 和 URN 是 URI 的子集，URL 可以理解为使用地址来
标识资源，URN 可以理解为使用名称来标识资源。
```

  #### 在输入框中如何判断输入的是一个正确的网址
```
function isUrl(url) {
       try {
           new URL(url);
           return true;
       }catch(err){
     return false;
}}
```

  #### 页面编码和被请求的资源编码如果不一致如何处理
```
后端响应头设置 charset
前端页面<meta>设置 charset
```

  #### WEB应用从服务器主动推送Data到客户端有那些方式
```
AJAX 轮询
html5 服务器推送事件 (new EventSource(SERVER_URL)).addEventListener("message", func);
html5 Websocket
(new WebSocket(SERVER_URL)).addEventListener("message", func);
```


### cookie

  #### 如何删除一个cookie
```
将时间设为当前时间往前一点：
	var date = new Date();
	date.setDate(date.getDate() - 1);//真正的删除

setDate()方法用于设置一个月的某一天

expires的设置：
document.cookie = 'user='+ encodeURIComponent('name')  + ';expires = ' + new Date(0)
```

  #### 服务器代理转发时，该如何处理cookie
```

```

  #### 什么是Samesite Cookie属性
```
Samesite Cookie 表示同站 cookie，避免 cookie 被第三方所利用。

将 Samesite 设为 strict ，这种称为严格模式，表示这个 cookie 
在任何情况下都不可能作为第三方 cookie。

将 Samesite 设为 Lax ，这种模式称为宽松模式，如果这个请求是个 
GET 请求，并且这个请求改变了当前页面或者打开了新的页面，那么这个 
cookie 可以作为第三方 cookie，其余情况下都不能作为第三方 cookie。

使用这种方法的缺点是，因为它不支持子域，所以子域没有办法与
主域共享登录信息，每次转入子域的网站，都回重新登录。
还有一个问题就是它的兼容性不够好。
```


### 面向对象

  #### 什么是面向对象编程及面向过程编程，它们的异同和优缺点
```
面向过程就是分析出解决问题所需要的步骤，然后用函数把这些步骤
一步一步实现，使用的时候一个一个依次调用就可以了

面向对象是把构成问题事务分解成各个对象，建立对象的目的不是为了
完成一个步骤，而是为了描叙某个事物在整个解决问题的步骤中的行为

面向对象是以功能来划分问题，而不是步骤
```

面向对象编程思想：
```
基本思想是使用对象，类，继承，封装等基本概念来进行程序设计
优点
易维护
采用面向对象思想设计的结构，可读性高，由于继承的存在，即使改变需求，那么维护也只是在局部模块，所以维护起来是非常方便和较低成本的
易扩展
开发工作的重用性、继承性高，降低重复工作量。
缩短了开发周期
```


### 同步和异步

  #### 同步和异步的区别
```
同步指的是当一个进程在执行某个请求的时候，如果这个请求需要等待一段时间
才能返回，那么这个进程会一直等待下去，直到消息返回为止再继续向下执行。

异步指的是当一个进程在执行某个请求的时候，如果这个请求需要
等待一段时间才能返回，这个时候进程会继续往下执行，
不会阻塞等待消息的返回，当消息返回时系统再通知进程进行处理。
```

```
同步，可以理解为在执行完一个函数或方法之后，一直等待系统返回值或消息，
这时程序是处于阻塞的，只有接收到返回的值或消息后才往下执行其他的命令。  

异步，执行完函数或方法后，不必阻塞性地等待返回值或消息，
只需要向系统委托一个异步过程，那么当系统接收到返回值或消息时，
系统会自动触发委托的异步过程，从而完成一个完整的流程。 
```

```
同步：浏览器访问服务器请求，用户看得到页面刷新，重新发请求,
等请求完，页面刷新，新内容出现，用户看到新内容,进行下一步操作

异步：浏览器访问服务器请求，用户正常操作，浏览器后端进行请求。
等请求完，页面不刷新，新内容也会出现，用户看到新内容
```

  #### 异步加载JS的方式有哪些
```
设置<script>属性 async="async" （一旦脚本可用，则会异步执行）
动态创建 script DOM：document.createElement('script');
XmlHttpRequest 脚本注入
异步加载库 LABjs
模块加载器 Sea.js
```

```
defer：只支持IE如果您的脚本不会改变文档的内容，可将 defer 属性加入
到<script>标签中，以便加快处理文档的速度。因为浏览器知道它将能够
安全地读取文档的剩余部分而不用执行脚本，它将推迟对脚本的解释，
直到文档已经显示给用户为止

async：HTML5 属性，仅适用于外部脚本；并且如果在IE中，同时存在
defer和async，那么defer的优先级比较高；脚本将在页面完成时执行
```

  #### 异步编程的实现方式
```
js 中的异步机制可以分为以下几种：

第一种最常见的是使用回调函数的方式，使用回调函数的方式有一个缺点是，多个回调函数嵌套的时候会造成回调函数地狱，上下两层的回调函数间的代码耦合度太高，不利于代码的可维护。

第二种是 Promise 的方式，使用 Promise 的方式可以将嵌套的回调函数作为链式调用。但是使用这种方法，有时会造成多个 then 的链式调用，可能会造成代码的语义不够明确。

第三种是使用 generator 的方式，它可以在函数的执行过程中，将函数的执行权转移出去，在函数外部我们还可以将执行权转移回来。当我们遇到异步函数执行的时候，将函数执行权转移出去，当异步函数执行完毕的时候我们再将执行权给转移回来。因此我们在 generator 内部对于异步操作的方式，可以以同步的顺序来书写。使用这种方式我们需要考虑的问题是何时将函数的控制权转移回来，因此我们需要有一个自动执行 generator 的机制，比如说 co 模块等方式来实现 generator 的自动执行。

第四种是使用 async 函数的形式，async 函数是 generator 和 promise 实现的一个自动执行的语法糖，它内部自带执行器，当函数内部执行到一个 await 语句的时候，如果语句返回一个 promise 对象，那么函数将会等待 promise 对象的状态变为 resolve 后再继续向下执行。因此我们可以将异步逻辑，转化为同步的顺序来书写，并且这个函数可以自动执行。
```

```
回调函数
优点：简单、容易理解
缺点：不利于维护，代码耦合高

事件监听（采用时间驱动模式，取决于某个事件是否发生）：
优点：容易理解，可以绑定多个事件，每个事件可以指定多个回调函数
缺点：事件驱动型，流程不够清晰

发布/订阅（观察者模式）
类似于事件监听，但是可以通过‘消息中心’，了解现在有多少发布者，多少订阅者

Promise 对象
优点：可以利用 then 方法，进行链式写法；可以书写错误时的回调函数；
缺点：编写和理解，相对比较难

Generator 函数
优点：函数体内外的数据交换、错误处理机制
缺点：流程管理不方便

async 函数
优点：内置执行器、更好的语义、更广的适用性、返回的是 Promise、结构清晰。
缺点：错误处理机制
```

  #### 什么是单线程，和异步的关系
```
单线程 - 只有一个线程，只能做一件事

原因 - 避免 DOM 渲染的冲突

浏览器需要渲染 DOM
	JS 可以修改 DOM 结构
	JS 执行的时候，浏览器 DOM 渲染会暂停
	两段 JS 也不能同时执行（都修改 DOM 就冲突了）
	webworker 支持多线程，但是不能访问 DOM

解决方案 - 异步
```

  #### 什么是Promise对象，什么是Promises/A+规范
```
Promise 对象是异步编程的一种解决方案，最早由社区提出。Promises/A+ 规范是 JavaScript Promise 的标准，规定了一个 Promise 所必须具有的特性。

Promise 是一个构造函数，接收一个函数作为参数，返回一个 Promise 实例。一个 Promise 实例有三种状态，分别是 pending、resolved 和 rejected，分别代表了进行中、已成功和已失败。实例的状态只能由 pending 转变 resolved 或者 rejected 状态，并且状态一经改变，就凝固了，无法再被改变了。状态的改变是通过 resolve() 和 reject() 函数来实现的，我们
可以在异步操作结束后调用这两个函数改变 Promise 实例的状态，它的原型上定义了一个 then 方法，使用这个 then 方法可以为两个状态的改变注册回调函数。这个回调函数属于微任务，会在本轮事件循环的末尾执行。
```

```
依照 Promise/A+ 的定义，Promise 有四种状态：

pending: 初始状态, 非 fulfilled 或 rejected.

fulfilled: 成功的操作.

rejected: 失败的操作.

settled: Promise已被fulfilled或rejected，且不是pending

另外， fulfilled与 rejected一起合称 settled

Promise 对象用来进行延迟(deferred) 和异步(asynchronous) 计算

Promise 的构造函数

构造一个 Promise，最基本的用法如下：
var promise = new Promise(function(resolve, reject) {

        if (...) {  // succeed

            resolve(result);

        } else {   // fails

            reject(Error(errMessage));

        }
    });
Promise 实例拥有 then 方法（具有 then 方法的对象，通常被称为thenable）。它的使用方法如下：
promise.then(onFulfilled, onRejected)
接收两个函数作为参数，一个在 fulfilled 的时候被调用，一个在rejected的时候被调用，接收参数就是 future，onFulfilled 对应resolve, onRejected对应 reject
```

  #### 手写一个Promise
```js
const PENDING = "pending";
const RESOLVED = "resolved";
const REJECTED = "rejected";

function MyPromise(fn) {
  // 保存初始化状态
  var self = this;

  // 初始化状态
  this.state = PENDING;

  // 用于保存 resolve 或者 rejected 传入的值
  this.value = null;

  // 用于保存 resolve 的回调函数
  this.resolvedCallbacks = [];

  // 用于保存 reject 的回调函数
  this.rejectedCallbacks = [];

  // 状态转变为 resolved 方法
  function resolve(value) {
    // 判断传入元素是否为 Promise 值，如果是，则状态改变必须等待前一个状态改变后再进行改变
    if (value instanceof MyPromise) {
      return value.then(resolve, reject);
    }

    // 保证代码的执行顺序为本轮事件循环的末尾
    setTimeout(() => {
      // 只有状态为 pending 时才能转变，
      if (self.state === PENDING) {
        // 修改状态
        self.state = RESOLVED;

        // 设置传入的值
        self.value = value;

        // 执行回调函数
        self.resolvedCallbacks.forEach(callback => {
          callback(value);
        });
      }
    }, 0);
  }

  // 状态转变为 rejected 方法
  function reject(value) {
    // 保证代码的执行顺序为本轮事件循环的末尾
    setTimeout(() => {
      // 只有状态为 pending 时才能转变
      if (self.state === PENDING) {
        // 修改状态
        self.state = REJECTED;

        // 设置传入的值
        self.value = value;

        // 执行回调函数
        self.rejectedCallbacks.forEach(callback => {
          callback(value);
        });
      }
    }, 0);
  }

  // 将两个方法传入函数执行
  try {
    fn(resolve, reject);
  } catch (e) {
    // 遇到错误时，捕获错误，执行 reject 函数
    reject(e);
  }
}

MyPromise.prototype.then = function(onResolved, onRejected) {
  // 首先判断两个参数是否为函数类型，因为这两个参数是可选参数
  onResolved =
    typeof onResolved === "function"
      ? onResolved
      : function(value) {
          return value;
        };

  onRejected =
    typeof onRejected === "function"
      ? onRejected
      : function(error) {
          throw error;
        };

  // 如果是等待状态，则将函数加入对应列表中
  if (this.state === PENDING) {
    this.resolvedCallbacks.push(onResolved);
    this.rejectedCallbacks.push(onRejected);
  }

  // 如果状态已经凝固，则直接执行对应状态的函数

  if (this.state === RESOLVED) {
    onResolved(this.value);
  }

  if (this.state === REJECTED) {
    onRejected(this.value);
  }
};
```

  #### js中的callback和promise区别
js中的callback与promise的区别实际就是宽度和深度的区别
```
两者之间的主要区别在于，使用回调方法时，我们通常只是将
回调传递给一个函数，该函数将在完成时被调用以获取某些结果。
但是，在Promise中，您将回调附加在返回的Promise对象上。
```
- 1.callback
```
回调函数本身是我们约定俗成的一种叫法，我们定义它，
但是并不会自己去执行它，它最终被其他人执行了。

优点：比较容易理解；
缺点：1.高耦合，维护困难，回调地狱;2.每个任务只能指定
一个回调函数;3.如果几个异步操作之间并没有顺序之分，
同样也要等待上一个操作执行结束再进行下一个操作。
```

- 2.Promise
```
ES6给我们提供了一个原生的构造函数Promise，Promise代表了
一个异步操作，可以将异步对象和回调函数脱离开来，通过.then方法
在这个异步操作上绑定回调函数，Promise可以让我们通过链式调用
的方法去解决回调嵌套的问题，而且由于promise.all这样的方法存在，
可以让同时执行多个操作变得简单。

promise对象存在三种状态：
1)Fulfilled:成功状态
2)Rejected：失败状态
3)Pending：既不是成功也不是失败状态，可以理解为进行中状态

Promise的缺点：
1.当处于未完成状态时，无法确定目前处于哪一阶段。
2.如果不设置回调函数，Promise内部的错误不会反映到外部。
3.无法取消Promise，一旦新建它就会立即执行，无法中途取消。
```

```
说起回调（callback），那可以说是JS最基础的异步调用方式

Promise：是一个返回对象,异步编程的一种解决方案（es6）
可取代callback,解决多层嵌套,分离异步获取数据与业务逻辑,

可以链式调用，每次返回的是一个Promise对象
```
 
promise状态：
```
pending(进行中)--> resolve(成功) reject(失败)  ，状态一旦设定，不可改变

      pending-->resolve 进行中-->成功

      pending-->reject 进行中-->失败
```

```
Promise.all // 所有的完成

Promise.all([p1,p2,p3])

Promise.race

Promise.all([a, b ,c]).then(res=> {
// 全部分会成功时调用

// 只要有一个失败，就返回失败的reject，其余取消

// res是一个数组，按照顺序分别储存a, b, c的返回结果 })

Promise.race([a, b ,c]).then(res=> {
// 某一个成功即可调用

// 常用于异步操作与定时器配合，制作网络超时

// res是首个返回的结果

})
```

  #### defer和async
```
defer并行加载js文件，会按照页面上script标签的顺序执行

async并行加载js文件，下载完成立即执行，
不会按照页面上script标签的顺序执行
```

```
此处的async和defer是对于页面中的script标签来说的。
如果一个页面正常的引入script脚本的话，如果脚本出现问题，
会直接影响DOM的渲染，导致页面白屏。解决这个问题
只需要给script标签添加defer或者async属性即可。

普通引入脚本的执行流程就是
1.DOM渲染
2.脚本加载
3.脚本执行
4.根据脚本渲染DOM
5.DOMContentLoaded
6.加载图片等外部资源
7.onload
```

- defer
```
如果script标签使用了defer属性，则script脚本会异步加载，
不影响DOM渲染，如果引入多个script且都使用defer属性，
则会根据引入的顺序加载。defer脚本文件会在DOM渲染完成后执行。

引入defer脚本的执行流程：
1.DOM渲染  defer脚本全部加载完毕
2.全部defer脚本执行
3.DOMContentLoaded
4.加载图片等外部资源
5.onload

对于defer脚本来说，他的使用场景就是一个脚本
如果需要依赖页面中的dom元素，则使用这种脚本。
```

- async
```
async脚本会在脚本加载完后立即执行，
不会管其他脚本加没加载完。
对于async脚本来说，他的使用场景就是一个脚本
如果不需要依赖页面中的dom元素，则使用这种脚本。
```

#### js脚本加载问题，async、defer问题
- 如果依赖其他脚本和 DOM 结果，使用 defer
- 如果与 DOM 和其他脚本依赖不强时，使用 async

script 引入方式
- html 静态<script>引入
- js 动态插入<script>
- <script defer>: 异步加载，元素解析完成后执行
- <script async>: 异步加载，但执行时会阻塞元素渲染

#### async原理
async/await语法糖就是使用Generator函数+自动执行器来运作的
```
// 定义了一个promise，用来模拟异步请求，作用是传入参数++
function getNum(num){
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            resolve(num+1)
        }, 1000)
    })
}

//自动执行器，如果一个Generator函数没有执行完，则递归调用
function asyncFun(func){
  var gen = func();

  function next(data){
    var result = gen.next(data);
    if (result.done) return result.value;
    result.value.then(function(data){
      next(data);
    });
  }

  next();
}

// 所需要执行的Generator函数，内部的数据在执行完成一步的promise之后，再调用下一步
var func = function* (){
  var f1 = yield getNum(1);
  var f2 = yield getNum(f1);
  console.log(f2) ;
};
asyncFun(func);
```
- 在执行的过程中，判断一个函数的promise是否完成，如果已经完成，将结果传入下一个函数，继续重复此步骤
- 每一个 next() 方法返回值的 value 属性为一个 Promise 对象，所以我们为其添加 then 方法， 在 then 方法里面接着运行 next 方法挪移遍历器指针，直到 Generator函数运行完成

### 模式

  #### 用过哪些设计模式
```
工厂模式：
工厂模式解决了重复实例化的问题，但还有一个问题,
那就是识别问题，因为根本无法

主要好处就是可以消除对象间的耦合，通过使用工程方法
而不是new关键字

构造函数模式：
使用构造函数的方法，即解决了重复实例化的问题，又解决了
对象识别的问题，该模式与工厂模式的不同之处在于

直接将属性和方法赋值给 this对象;
```

  #### 单例模式模式
```
单例模式保证了全局只有一个实例来被访问。
比如说常用的如弹框组件的实现和全局状态的实现。
```

  #### 策略模式
```
策略模式主要是用来将方法的实现和方法的调用分离开，外部通过
不同的参数可以调用不同的策略。我主要在 MVP 模式解耦的时候
用来将视图层的方法定义和方法调用分离。
```

  #### 代理模式
```
 代理模式是为一个对象提供一个代用品或占位符，
 以便控制对它的访问。比如说常见的事件代理。
```

  #### 中介者模式
```
中介者模式指的是，多个对象通过一个中介者进行交流，
而不是直接进行交流，这样能够将通信的各个对象解耦。
```

  #### 适配器模式
```
适配器用来解决两个接口不兼容的情况，不需要改变已有的接口，
通过包装一层的方式实现两个接口的正常协作。假如我们需要一种
新的接口返回方式，但是老的接口由于在太多地方已经使用了，
不能随意更改，这个时候就可以使用适配器模式。比如我们需要一种
自定义的时间返回格式，但是我们又不能对 js 时间格式化的接口
进行修改，这个时候就可以使用适配器模式。
```

  #### 观察者模式和发布订阅模式有什么不同
```
发布订阅模式其实属于广义上的观察者模式

在观察者模式中，观察者需要直接订阅目标事件。
在目标发出内容改变的事件后，直接接收事件并作出响应。

而在发布订阅模式中，发布者和订阅者之间多了一个调度中心。
调度中心一方面从发布者接收事件，另一方面向订阅者发布事件，
订阅者需要在调度中心中订阅事件。通过调度中心实现了发布者和
订阅者关系的解耦。使用发布订阅者模式更利于我们代码的可维护性。
```

- 观察者模式（Observer Pattern）
```
观察者模式定义了对象间的一种一对多的依赖关系，当一个
对象的状态发生改变时，所有依赖于它的对象都将得到通知，
并自动更新。
比如旧时一个村子的人都预定了第二天张三家的牛奶，
当到第二天张三提着牛奶桶在街上大声喊牛奶到了牛奶到了，
然后预定了牛奶的人家就会陆续出来打牛奶。
```

- 发布订阅模式（Pub-Sub Pattern）
```
发布订阅模式是观察者模式的一个分支，但是现在慢慢独立
出来。这一模式中发布者的消息发送者不会将消息直接发送给
订阅者，这意味着发布者和订阅者不知道彼此的存在。
在发布者和订阅者之间存在第三个组件，称为消息代理或
调度中心或中间件，它维持着发布者和订阅者之间的联系，
过滤所有发布者传入的消息并相应地分发它们给订阅者。
拿上边牛奶说事，现在村子的人都会使用微信了，同样都通过
微信群定于了张三家牛奶。等第二天张三家牛奶挤出来了，
张三就在朋友圈发布消息，说乡亲们牛奶好了，请自提。
相信们通过微信群看到消息就会陆续来自提牛奶。
发布订阅模式中的过程比之前观察者模式中的过程中间多了一个微信。
```

- 观察者模式和发布订阅模式有什么区别？
```
我们先来看下这两个模式的实现结构：
观察者模式：观察者（Observer）直接订阅（Subscribe）
主题（Subject），而当主题被激活的时候，
会触发（Fire Event）观察者里的事件。

发布订阅模式：订阅者（Subscriber）把自己想订阅的
事件注册（Subscribe）到调度中心（Topic），当发布者
（Publisher）发布该事件（Publish topic）到调度中心，
也就是该事件触发时，由调度中心统一调度（Fire Event）
订阅者注册到调度中心的处理代码。
```

- 观察者模式实现
```
为了更好的解释这种设计模式，我们另设置一个情景。
假定每一个人都具有发布新书和订阅新书的功能，同时能知道
谁订阅了自己的新书。现在我们规定系统生成了三个人，
每一个人都具有之前假定的功能。现在其中一个人比较有名，
所以另外两个人都订阅了他的新书，一旦新书发表，
他们就能获得新书。结合这个场景，我们看如下代码：
//list订阅列表
//publish发布新书->订阅列表中对象买到新书
//subscribe订阅新书的渠道
function Humen (){
    this.list = []
    this.publish = function(){
        this.list.forEach((item)=>{
            item()
        })
    }
    this.subscribe = function(target , fn){
        target.list.push(fn)
    }
}
var edward = new Humen();  //注册edward用户
var eric = new Humen()     //注册eric用户
var lucy = new Humen()    //注册lucy用户
edward.subscribe(lucy , function(){//edward订阅lucy新书
    console.log('Edward买到新书')
})
eric.subscribe(lucy , function(){//eric订阅lucy新书
    console.log('Eric买到新书')
})
lucy.publish(); //lucy发布新书
在上述代码中，系统生成了三个人分别为edward、eric、lucy。
其中lucy比较有名，edward和eric都调用自己的subscribe
函数订阅了lucy，并且规定了买到书之后的回调函数，
subscribe两个参数分别为订阅目标和回调函数，分别执行
edward，eric的subscribe函数后，相当于是在lucy的list属性
中加入了前两者买到书之后的回调函数。然后lucy发布新书，
就会执行lucy的publish函数，此函数遍历lucy的list中
已经添加好的函数，依次执行。到此，我们就实现了一个简单的观察者模式。
```

- 发布订阅模式实现
```
发布者模式之前提到它比观察者模式多了一个调度中心，
我们将这个调度中心比作当当网，也就是说上一个例子
中lucy发布的新书会通过当当网发布，订阅此书的其他人
也必须从当当网订阅。下面是代码实现：
var dangdang = {
    list : [],
    subscribe : function(name,fn){
        name.push(fn)
    },
    publish : function(name){
       name.forEach((item)=>{
           item()
       }) 
    }
}
function Humen (){
    this.subscribe = function(name , fn){
        dangdang.subscribe(name,fn)
    }
    this.publish = function(name){
        dangdang.publish(name)
    }
}
var edward = new Humen();  //注册edward用户
var eric = new Humen()     //注册eric用户
var lucy = new Humen()    //注册lucy用户
edward.subscribe(dangdang['list'] , function(){//edward订阅当当网新书
    console.log('Edward从当当网买到新书')
})
eric.subscribe(dangdang['list'] , function(){//eric订阅当当网新书
    console.log('Eric当当网买到新书')
})
lucy.publish(dangdang['list']); //lucy在当当网发布新书
上述代码中，我们依旧保留了用户的发布和订阅功能，
但是都将这些功能最终交给当当网的发布和订阅功能取去实现。
上述代码中写一个dangdang对象，在对象中list为当前
订阅人的回调函数，subscribe为订阅函数，publish为
发布函数。注册三个用户，其中edward和eric订阅了
当当网新书，并把订阅回调函数保存在了当当网list中。
下面lucy发布新书，通过当当网的发布函数。当当网发布
函数一调用，立刻执行所有list中的回调函数。
以上就是发布订阅者模式
```

- 总结
```
观察者模式和发布订阅模式最大的区别就是发布订阅模式有个事件调度中心。
观察者模式由具体目标调度，每个被订阅的目标里面都需要有对观察者的处理，这种处理方式比较直接粗暴，但是会造成代码的冗余。
而发布订阅模式中统一由调度中心进行处理，订阅者和发布者互不干扰，消除了发布者和订阅者之间的依赖。
```

  #### 严格模式的限制
```
变量必须声明后再使用
函数的参数不能有同名属性，否则报错
不能使用with语句
不能对只读属性赋值，否则报错
不能使用前缀0表示八进制数，否则报错
不能删除不可删除的属性，否则报错
不能删除变量delete prop，会报错，只能删除属性delete global[prop]
eval不会在它的外层作用域引入变量
eval和arguments不能被重新赋值
arguments不会自动反映函数参数的变化
不能使用arguments.callee
不能使用arguments.caller
禁止this指向全局对象
不能使用fn.caller和fn.arguments获取函数调用的堆栈
增加了保留字（比如protected、static和interface）
```

  #### 手写一个观察者模式
```js
var events = (function() {
  var topics = {};

  return {
    // 注册监听函数
    subscribe: function(topic, handler) {
      if (!topics.hasOwnProperty(topic)) {
        topics[topic] = [];
      }
      topics[topic].push(handler);
    },

    // 发布事件，触发观察者回调事件
    publish: function(topic, info) {
      if (topics.hasOwnProperty(topic)) {
        topics[topic].forEach(function(handler) {
          handler(info);
        });
      }
    },

    // 移除主题的一个观察者的回调事件
    remove: function(topic, handler) {
      if (!topics.hasOwnProperty(topic)) return;

      var handlerIndex = -1;
      topics[topic].forEach(function(item, index) {
        if (item === handler) {
          handlerIndex = index;
        }
      });

      if (handlerIndex >= 0) {
        topics[topic].splice(handlerIndex, 1);
      }
    },

    // 移除主题的所有观察者的回调事件
    removeAll: function(topic) {
      if (topics.hasOwnProperty(topic)) {
        topics[topic] = [];
      }
    }
  };
})();
```

#### 说说JavaScript对象的几种创建方式
工厂模式,创建方式
```
function createPerson(name,age,job){
    var o = new Object();
    o.name=name;
    o.age=age;
    o.job=job;
    o.sayName = function(){
        alert(this.name);
    }
}
var person1 = createPerson("da",1,"it");
var person2 = createPerson("dada",2,"it");
```
构造函数模式
```
function Person(name,age,ob){
    this.name=name;
    this.age=age;
    this.job=job;
    this.sayName = function(){
        alert(this.name);
    }
var person1 = new Person("dada",1,"web");
var person2 = new Person("dada",2,"web");
}
```
使用原型模式
```
function Person(){
}
Person.prototype.name = "da";
Person.prototype.age = 1;
Person.prototype.job = "web";
Person.prototype.sayName = function(){
    alert(this.name);
}
 
var person1 = new Person();
person1.sayName();    //"dada"
 
var person2 = new Person();
person2.sayName();    //"dada"
 
alert(person1.sayName == person2.sayName);   //true
```
组合使用构造函数模式和原型模式
```
function Person(name,age){
    this.name = name;
    this.age = age;
    this.friends = ["da","dada"];
}
Person.prototype = {
    constructor:Person,
    sayName:function(){
        alert(this.name);
    }
}
var person1 = new Person("da1",1);
var person2 = new Person("da2",2);
person1.friends.push("dadada");
console.log(person1.friends);    //["da","dada","dadada"]
console.log(person2.friends);    //["da","dada"]
console.log(person1.friends === person2.friends);    //false
console.log(person1.sayName === person2.sayName);   //true
```
动态原型模式
```
function Person(name,age,job){
    this.name=name;
    this.age=age;
    this.job=job;

    if(typeof this.sayName!="function"){
        Person.prototype.sayName=function(){
            alert(this.name);
        };
    }
}
```



### 模块化
- 模块化开发在现代开发中已是必不可少的一部分，它大大提高了项目的可维护、可拓展和可协作性。通常，我们 在浏览器中使用 ES6 的模块化支持，在 Node 中使用 commonjs 的模块化支持。

分类:
- es6: import / export
- commonjs: require / module.exports / exports
- amd: require / defined

require与import的区别
- require支持 动态导入，import不支持，正在提案 (babel 下可支持)
- require是 同步 导入，import属于 异步 导入
- require是 值拷贝，导出值变化不会影响导入值；import指向 内存地址，导入值会随导出值而变化

  #### 模块化开发怎么做
```
我对模块的理解是，一个模块是实现一个特定功能的一组方法。
在最开始的时候，js 只实现一些简单的功能，所以并没有模块的概念，
但随着程序越来越复杂，代码的模块化开发变得越来越重要。

由于函数具有独立作用域的特点，最原始的写法是使用函数来作为模块，
几个函数作为一个模块，但是这种方式容易造成全局变量的污染，
并且模块间没有联系。

后面提出了对象写法，通过将函数作为一个对象的方法来实现，
这样解决了直接使用函数作为模块的一些缺点，但是这种办法会暴露
所有的所有的模块成员，外部代码可以修改内部属性的值。

现在最常用的是立即执行函数的写法，通过利用闭包来实现模块
私有作用域的建立，同时不会对全局作用域造成污染。
```

```
立即执行函数,不暴露私有成员
var module1 = (function(){
　　　　var _count = 0;
　　　　var m1 = function(){
　　　　　　//...
　　　　};
　　　　var m2 = function(){
　　　　　　//...
　　　　};
　　　　return {
　　　　　　m1 : m1,
　　　　　　m2 : m2
　　　　};
})();
```

  #### js的几种模块规范
```
js 中现在比较成熟的有四种模块加载方案。

第一种是 CommonJS 方案，它通过 require 来引入模块，
通过 module.exports 定义模块的输出接口。这种模块加载方案是
服务器端的解决方案，它是以同步的方式来引入模块的，因为在服务端
文件都存储在本地磁盘，所以读取非常快，所以以同步的方式加载
没有问题。但如果是在浏览器端，由于模块的加载是使用网络请求，
因此使用异步加载的方式更加合适。

第二种是 AMD 方案，这种方案采用异步加载的方式来加载模块，
模块的加载不影响后面语句的执行，所有依赖这个模块的语句都定
义在一个回调函数里，等到加载完成后再执行回调函数。
require.js 实现了 AMD 规范。

第三种是 CMD 方案，这种方案和 AMD 方案都是为了解决异步模块
加载的问题，sea.js 实现了 CMD 规范。它和 require.js的区别
在于模块定义时对依赖的处理不同和对依赖模块的执行时机的处理不同。

第四种方案是 ES6 提出的方案，使用 import 和 export 
的形式来导入导出模块。这种方案和上面三种方案都不同。
```

  #### ES6模块与CommonJS模块、AMD、CMD的差异
```
(1)CommonJS 模块输出的是一个值的拷贝，ES6 模块输出的是值的引用。
CommonJS 模块输出的是值的拷贝，也就是说，一旦输出一个值，
模块内部的变化就影响不到这个值。ES6 模块的运行机制与 CommonJS 不一样。
JS 引擎对脚本静态分析的时候，遇到模块加载命令 import，
就会生成一个只读引用。等到脚本真正执行时，再根据这个只读引用，
到被加载的那个模块里面去取值。

(2)CommonJS 模块是运行时加载，ES6 模块是编译时输出接口。CommonJS 
模块就是对象，即在输入时是先加载整个模块，生成一个对象，然后再从
这个对象上面读取方法，这种加载称为“运行时加载”。而 ES6 模块不是
对象，它的对外接口只是一种静态定义，在代码静态解析阶段就会生成。
```

AMD 和 CMD 规范之间的主要区别有两个方面。
```
（1）第一个方面是在模块定义时对依赖的处理不同。AMD 推崇
依赖前置，在定义模块的时候就要声明其依赖的模块。
而 CMD 推崇就近依赖，只有在用到某个模块的时候再去 require。

（2）第二个方面是对依赖模块的执行时机处理不同。首先 AMD 和 CMD 
对于模块的加载方式都是异步加载，不过它们的区别在于模块的执行时机，
AMD 在依赖模块加载完成后就直接执行依赖模块，依赖模块的执行顺序和
我们书写的顺序不一定一致。而 CMD在依赖模块加载完成后并不执行，
只是下载而已，等到所有的依赖模块都加载好后，进入回调函数逻辑，
遇到 require 语句的时候才执行对应的模块，
这样模块的执行顺序就和我们书写的顺序保持一致了。

// CMD
define(function(require, exports, module) {
  var a = require("./a");
  a.doSomething();
  // 此处略去 100 行
  var b = require("./b"); // 依赖可以就近书写
  b.doSomething();
  // ...
});

// AMD 默认推荐
define(["./a", "./b"], function(a, b) {
  // 依赖必须一开始就写好
  a.doSomething();
  // 此处略去 100 行
  b.doSomething();
  // ...
});
```

```
CommonJS是服务器端模块的规范，Node.js采用了这个规范。
CommonJS规范加载模块是同步的，也就是说，只有加载完成，
才能执行后面的操作。AMD规范则是非同步加载模块，允许指定回调函数

AMD推荐的风格通过返回一个对象做为模块对象，CommonJS的风格通过
对module.exports或exports的属性赋值来达到暴露模块对象的目的

es6模块 CommonJS、AMD、CMD：
CommonJS 的规范中，每个 JavaScript 文件就是一个独立的
模块上下文（module context），在这个上下文中默认创建的属性
都是私有的。也就是说，在一个文件定义的变量（还包括函数和类），
都是私有的，对其他文件是不可见的。

CommonJS是同步加载模块,在浏览器中会出现堵塞情况，所以不适用

AMD 异步，需要定义回调define方式

es6 一个模块就是一个独立的文件，该文件内部的所有变量，
外部无法获取。如果你希望外部能够读取模块内部的某个变量，
就必须使用export关键字输出该变量 es6还可以导出类、
方法，自动适用严格模式
```

  #### JS模块加载器的轮子怎么造，也就是如何实现一个模块加载器
```
原理一： id即路径 原则。
通常我们的入口是这样的： require( [ 'a', 'b' ], callback ) 。
这里的 'a'、'b' 都是 ModuleId。通过 id 和路径的对应原则，
加载器才能知道需要加载的 js 的路径。在这个例子里，
就是 baseUrl + 'a.js' 和 baseUrl + 'b.js'。

但 id 和 path 的对应关系并不是永远那么简单，比如在 AMD 规范里
就可以通过配置 Paths 来给特定的 id 指配 path。

原理二：createElement('script') & appendChild
知道路径之后，就需要去请求。一般是通过 
createElement('script') & appendChild 去请求。
有时候有的加载器也会通过 AJAX 去请求脚本内容。

一般来说，需要给 <script> 设置一个属性用来标识模块 id, 作用后面会提到。

原理三：document.currentScript
a.js 里可能是 define( id, factory ) 或者是 define( factory )，
后者被称为匿名模块。那么当 define(factory) 被执行的时候，
我们怎么知道当前被定义的是哪个模块呢，具体地说，这个匿名模块的
实际模块 id 是什么？ 答案是通过 document.currentScript 获取
当前执行的<script>，然后通过上面给 script 设置的属性来得到模块 id。

需要注意的是，低级浏览器是不支持 currentScript 的，这里需要进行
浏览器兼容。在高级浏览器里面，还可以通过 script.onload 来处理这个事情。

原理四：依赖分析
在继续讲之前，需要先简单介绍下模块的生命周期。模块在被 Define 之后
并不是马上可以用了，在你执行它的 factory 方法来生产出最终的 export 
之前，你需要保证它的依赖是可用的。那么首先就要先把依赖分析出来。

简单来说，就是通过 toString 这个方法得到 factory 的内容，然后
用正则去匹配其中的 require( 'moduleId' )。当然也可以不用正则。

这就是为什么 require( var ); 这种带变量的语句是不被推荐的，因为它会影响
依赖分析。如果一定要用变量，可以用 require( [ var ] ) 这种异步加载的方式。

原理五：递归加载
在分析出模块的依赖之后，我们需要递归去加载依赖模块。用伪代码来表达大概是这样的：
Module.prototype.load = function () {
    var deps = this.getDeps();
    for (var i = 0; i < deps.length; i++) {
        var m = deps[i];
        if (m.state < STATUS.LOADED) {
            m.load();
        }
    }
    this.state = STATUS.LOADED;
}
上面的代码只是表达一个意思，实际上 load 方法很可能是异步的，
所以递归的返回要特殊处理下。

实现一个可用的加载器并没有那么简单，比如你要处理循环依赖，
还有各种各样的牵一发动全身的细节。但要说原理，大概就是这么几条。
个人觉得，比起照着规范实现一个加载器，更加吸引人的是 
AMD 或者CommonJS 这些规范的完善和背后的设计思路。
```

  #### require模块引入的查找方式
```
当 Node 遇到 require(X) 时，按下面的顺序处理。

（1）如果 X 是内置模块（比如 require('http')）
　　a. 返回该模块。
　　b. 不再继续执行。

（2）如果 X 以 "./" 或者 "/" 或者 "../" 开头
　　a. 根据 X 所在的父模块，确定 X 的绝对路径。
　　b. 将 X 当成文件，依次查找下面文件，只要其中有一个存在，
  就返回该文件，不再继续执行。
    X
    X.js
    X.json
    X.node

　　c. 将 X 当成目录，依次查找下面文件，只要其中有一个存在，
  就返回该文件，不再继续执行。
    X/package.json（main字段）
    X/index.js
    X/index.json
    X/index.node

（3）如果 X 不带路径
　　a. 根据 X 所在的父模块，确定 X 可能的安装目录。
　　b. 依次在每个目录中，将 X 当成文件名或目录名加载。

（4）抛出 "not found"
```

### DOM

  #### 什么是DOM和BOM
```
DOM 指的是文档对象模型，它指的是把文档当做一个对象来对待，
这个对象主要定义了处理网页内容的方法和接口。

BOM 指的是浏览器对象模型，它指的是把浏览器当做一个对象来对待，
这个对象主要定义了与浏览器进行交互的法和接口。BOM的核心是 window，
而 window 对象具有双重角色，它既是通过 js 访问浏览器窗口的
一个接口，又是一个 Global（全局）对象。这意味着在网页中定义的
任何对象，变量和函数，都作为全局对象的一个属性或者方法存在。
window 对象含有 location 对象、navigator 对象、screen 对象等子对象，
并且 DOM 的最根本的对象 document 对象也是 BOM 的 window 对象的子对象。
```

- BOM
```
BOM即Browers Object Model(浏览器对象模型)，整个BOM的核心
即window对象。使用window对象可以操作浏览器的一些行为。
下面是常用的BOM属性、方法、事件：
history属性
location属性
document属性
prompt方法
alert方法
setTimeout方法
setInterval方法
onload事件
onclick事件
onkeydown事件
```

- DOM
```
DOM即Document Object Model(文档对象模型)，每一个html文件
都具有一个DOM对象，在这个DOM对象中包含了html文件中所有标签，
所有标签的属性等。下面列举一些常用的方法和属性。
getElementById方法
getattribute方法
```

  #### 介绍DOM的发展
```
DOM：文档对象模型（Document Object Model），
定义了访问HTML和XML文档的标准，与编程语言及平台无关

DOM0：提供了查询和操作Web文档的内容API。未形成标准，实现混乱。
如：document.forms['login']

DOM1：W3C提出标准化的DOM，简化了对文档中任意部分的访问和操作。
如：JavaScript中的Document对象

DOM2：原来DOM基础上扩充了鼠标事件等细分模块，增加了对CSS的支持。
如：getComputedStyle(elem, pseudo)

DOM3：增加了XPath模块和加载与保存（Load and Save）模块。
如：XPathEvaluator
```

  #### DOM操作怎样添加、移除、移动、复制、创建和查找节点
（1）创建新节点
```js
createDocumentFragment(node);
createElement(node);
createTextNode(text);
```

（2）添加、移除、替换、插入
```js
appendChild(node)
removeChild(node)
replaceChild(new,old)
insertBefore(new,old)
```

（3）查找
```js
getElementById();
getElementsByName();
getElementsByTagName();
getElementsByClassName();
querySelector();
querySelectorAll();
```

（4）属性操作
```js
getAttribute(key);
setAttribute(key, value);
hasAttribute(key);
removeAttribute(key);
```

#### 操作DOM节点方法
创建新节点
```
createDocumentFragment()    //创建一个DOM片段
createElement()   //创建一个具体的元素
createTextNode()   //创建一个文本节点
```
添加、移除、替换、插入
```
appendChild()      //添加
removeChild()      //移除
replaceChild()      //替换
insertBefore()      //插入
```
查找
```
getElementsByTagName()    //通过标签名称
getElementsByName()     //通过元素的Name属性的值
getElementById()        //通过元素Id，唯一性
```

  #### 虚拟DOM(Virtual DOM),为什么虚拟DOM比原生DOM快
```
我对 Virtual DOM 的理解是，

首先对我们将要插入到文档中的 DOM 树结构进行分析，使用 js 对象
将其表示出来，比如一个元素对象，包含 TagName、props 和 
Children 这些属性。然后我们将这个 js 对象树给保存下来，
最后再将 DOM 片段插入到文档中。

当页面的状态发生改变，我们需要对页面的 DOM 的结构进行调整的时候，
我们首先根据变更的状态，重新构建起一棵对象树，然后将这棵
新的对象树和旧的对象树进行比较，记录下两棵树的的差异。

最后将记录的有差异的地方应用到真正的 DOM 树中去，这样视图就更新了。

我认为 Virtual DOM 这种方法对于我们需要有大量的 DOM 操作的时候，
能够很好的提高我们的操作效率，通过在操作前确定需要做的最小修改，
尽可能的减少 DOM 操作带来的重流和重绘的影响。其实 Virtual DOM 
并不一定比我们真实的操作 DOM 要快，这种方法的目的是为了
提高我们开发时的可维护性，在任意的情况下，都能保证一个
尽量小的性能消耗去进行操作。
```

  #### 如何比较两个DOM树的差异
```
两个树的完全 diff 算法的时间复杂度为 O(n^3) ，但是在前端中，
我们很少会跨层级的移动元素，所以我们只需要比较同一层级的元素
进行比较，这样就可以将算法的时间复杂度降低为 O(n)。

算法首先会对新旧两棵树进行一个深度优先的遍历，这样每个节点
都会有一个序号。在深度遍历的时候，每遍历到一个节点，我们就将
这个节点和新的树中的节点进行比较，如果有差异，
则将这个差异记录到一个对象中。

在对列表元素进行对比的时候，由于 TagName 是重复的，所以我们
不能使用这个来对比。我们需要给每一个子节点加上一个 key，
列表对比的时候使用 key 来进行比较，
这样我们才能够复用老的 DOM 树上的节点。
```

  #### 介绍DOM0，DOM2，DOM3事件处理方式区别
```
DOM0级事件处理方式：
	btn.onclick = func;
	btn.onclick = null;
	
DOM2级事件处理方式：
	btn.addEventListener('click', func, false);
	btn.removeEventListener('click', func, false);
	btn.attachEvent("onclick", func);
	btn.detachEvent("onclick", func);
	
DOM3级事件处理方式：
	eventUtil.addListener(input, "textInput", func);
	eventUtil 是自定义对象，textInput 是DOM3级事件
```

#### 说说有几种类型的DOM节点
- Document节点，整个文档是一个文档节点；
- Element节点，每个HTML标签是一个元素节点；
- Attribute节点，每一个HTML属性是一个属性节点；
- Text节点，包含在HTML元素中的文本是文本节点


### 优化

  #### 项目做过哪些性能优化
```
减少 HTTP 请求数
减少 DNS 查询
使用 CDN
避免重定向
图片懒加载
减少 DOM 元素数量
减少DOM 操作
使用外部 JavaScript 和 CSS
压缩 JavaScript 、 CSS 、字体、图片等
优化 CSS Sprite
使用 iconfont
字体裁剪
多域名分发划分内容到不同域名
尽量减少 iframe 使用
避免图片 src 为空
把样式表放在link 中
把JavaScript放在页面底部
```

  #### 懒加载 预加载 懒执行
```
懒加载也叫延迟加载，指的是在长网页中延迟加载图片的时机，
当用户需要访问时，再去加载，这样可以提高网站的首屏加载速度，
提升用户的体验，并且可以减少服务器的压力。它适用于图片很多，
页面很长的电商网站的场景。懒加载的实现原理是，将页面上的图片
的 src 属性设置为空字符串，将图片的真实路径保存在一个自定义属性中，
当页面滚动的时候，进行判断，如果图片进入页面可视区域内，
则从自定义属性中取出真实路径赋值给图片的 src 属性，
以此来实现图片的延迟加载。懒加载不仅可以用于图片，
也可以使用在别的资源上。比如进入可视区域才开始播放视频等等。

预加载指的是将所需的资源提前请求加载到本地，这样后面在需要
用到时就直接从缓存取资源。通过预加载能够减少用户的等待时间，
提高用户的体验。我了解的预加载的最常用的方式是使用 js 中的 
image 对象，通过为 image 对象来设置 scr 属性，来实现图片的预加载。

这两种方式都是提高网页性能的方式，两者主要区别是一个是提前加载，
一个是迟缓甚至不加载。懒加载对服务器前端有一定的缓解压力作用，
预加载则会增加服务器前端压力。

懒执行就是将某些逻辑延迟到使用时再计算。该技术可以用于首屏优化，
对于某些耗时逻辑并不需要在首屏就使用的，就可以使用懒执行。
懒执行需要唤醒，一般可以通过定时器或者事件的调用来唤醒懒加载
```

```
预加载：提前加载图片，当用户需要查看时可直接从本地缓存中渲染。

懒加载：懒加载的主要目的是作为服务器前端的优化，
减少请求数或延迟请求数。

两种技术的本质：两者的行为是相反的，一个是提前加载，
一个是迟缓甚至不加载。 懒加载对服务器前端有一定的
缓解压力作用，预加载则会增加服务器前端压力。
```

懒加载实现：
```
图片懒加载
// <img src="default.png" data-src="https://xxxx/real.png">
function isVisible(el) {
  const position = el.getBoundingClientRect()
  const windowHeight = document.documentElement.clientHeight
  // 顶部边缘可见
  const topVisible = position.top > 0 && position.top < windowHeight;
  // 底部边缘可见
  const bottomVisible = position.bottom < windowHeight && position.bottom > 0;
  return topVisible || bottomVisible;
}

function imageLazyLoad() {
  const images = document.querySelectorAll('img')
  for (let img of images) {
    const realSrc = img.dataset.src
    if (!realSrc) continue
    if (isVisible(img)) {
      img.src = realSrc
      img.dataset.src = ''
    }
  }
}

// 测试
window.addEventListener('load', imageLazyLoad)
window.addEventListener('scroll', imageLazyLoad)
// or
window.addEventListener('scroll', throttle(imageLazyLoad, 1000))
```

  #### 如何渲染几万条数据并不卡住界面
```
这道题考察了如何在不卡住页面的情况下渲染数据，也就是说不能
一次性将几万条都渲染出来，而应该一次渲染部分 DOM，
那么就可以通过 requestAnimationFrame 来每 16 ms 刷新一次

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>Document</title>
</head>
<body>
  <ul>控件</ul>
  <script>
    setTimeout(() => {
      // 插入十万条数据
      const total = 100000
      // 一次插入 20 条，如果觉得性能不好就减少
      const once = 20
      // 渲染数据总共需要几次
      const loopCount = total / once
      let countOfRender = 0
      let ul = document.querySelector("ul");
      function add() {
        // 优化性能，插入不会造成回流
        const fragment = document.createDocumentFragment();
        for (let i = 0; i < once; i++) {
          const li = document.createElement("li");
          li.innerText = Math.floor(Math.random() * total);
          fragment.appendChild(li);
        }
        ul.appendChild(fragment);
        countOfRender += 1;
        loop();
      }
      function loop() {
        if (countOfRender < loopCount) {
          window.requestAnimationFrame(add);
        }
      }
      loop();
    }, 0);
  </script>
</body>
</html>
```

  #### 一个列表，假设有100000个数据，这个该怎么办
```
我们需要思考的问题：该处理是否必须同步完成？数据是否必须按顺序完成？

解决办法：
（1）将数据分页，利用分页的原理，每次服务器端只返回
一定数目的数据，浏览器每次只对一部分进行加载。

（2）使用懒加载的方法，每次加载一部分数据，其余数据当需要使用时再去加载。

（3）使用数组分块技术，基本思路是为要处理的项目创建一个队列，
然后设置定时器每过一段时间取出一部分数据，然后再使用定时器
取出下一个要处理的项目进行处理，接着再设置另一个定时器。
```


### 安全

  #### 同源
同源策略是一种安全协议
```
我对浏览器的同源政策的理解是，一个域下的 js 脚本在未经允许的情况下，
不能够访问另一个域的内容。这里的同源的指的是两个域的
协议、域名、端口号必须相同，否则则不属于同一个域。

同源政策主要限制了三个方面：
第一个是当前域下的 js 脚本不能够访问其他域下的 cookie、localStorage 和 indexDB。
第二个是当前域下的 js 脚本不能够操作访问操作其他域下的 DOM。
第三个是当前域下 ajax 无法发送跨域请求。

同源政策的目的主要是为了保证用户的信息安全，防止某个文档或脚本从
多个不同源装载。
它只是对 js 脚本的一种限制，并不是对浏览器的限制，
对于一般的 img、或者script 脚本请求都不会有跨域的限制，
这是因为这些操作都不会通过响应结果来进行可能出现安全问题的操作。
```

```
举例说明：比如一个黑客程序，他利用Iframe把真正的银行登录页面
嵌到他的页面上，当你使用真实的用户名，密码登录时，他的页面就
可以通过Javascript读取到你的表单中input中的内容，
这样用户名，密码就轻松到手了。

缺点：
现在网站的JS都会进行压缩，一些文件用了严格模式，而另一些没有。
这时这些本来是严格模式的文件，被 merge后，这个串就到了文件的中间，
不仅没有指示严格模式，反而在压缩后浪费了字节
```

   #### 浏览器的同源政策
```
我对浏览器的同源政策的理解是，一个域下的 js 脚本在未经允许
的情况下，不能够访问另一个域的内容。这里的同源的指的是两个域
的协议、域名、端口号必须相同，否则则不属于同一个域。

同源政策主要限制了三个方面：
第一个是当前域下的 js 脚本不能够访问其他域下的 cookie、localStorage 和 indexDB。

第二个是当前域下的 js 脚本不能够操作访问操作其他域下的 DOM。

第三个是当前域下 ajax 无法发送跨域请求。

同源政策的目的主要是为了保证用户的信息安全，它只是对 js 脚本的
一种限制，并不是对浏览器的限制，对于一般的 img、或者script 脚本请求
都不会有跨域的限制，这是因为这些操作都不会通过响应结果来进行
可能出现安全问题的操作。
```

  #### 限制
为什么会产生跨域？
```
你之所以会遇到跨域问题，正是因为 SOP 的各种限制。
本质上 SOP 并不是禁止跨域请求，而是在请求后拦截了请求的回应。

其实表面上 SOP 分两种情况：
可以正常引用 iframe、图片等各种资源，但是限制对其内容进行操作
直接限制 ajax 请求，准确来说是限制操作 ajax 响应结果，这会引起 CSRF
但是，本质上这两条是一样的：总之，对于非同源的资源，
浏览器可以“直接使用”，但是程序员和用户不可以对这些数据进行操作，
杜绝某些居心不良的行为。这就是现代安全浏览器对用户的保护之一。

下面是 3 个在实际应用中会遇到的例子：
使用 ajax 请求其他跨域 API，最常见的情况
iframe 与父页面交流（如 DOM 或变量的获取），出现率比较低
对跨域图片（例如来源于 <img> ）进行操作，
在 canvas 操作图片的时候会遇到这个问题

如果没有了 SOP：
iframe 里的机密信息被肆意读取
更加肆意地进行 CSRF
接口被第三方滥用
```

  #### 跨域
因为浏览器出于安全考虑，有同源策略。也就是说，
如果协议、域名或者端口有一个不同就是跨域
```
1. 通过 jsonp 跨域
2. document.domain + iframe 跨域
3. location.hash + iframe
4. window.name + iframe 跨域
5 .postMessage 跨域
6. 跨域资源共享（CORS)
7. nginx 代理跨域
8. nodejs 中间件代理跨域
9. WebSocket 协议跨域
```

```
解决跨域的方法我们可以根据我们想要实现的目的来划分。

首先我们如果只是想要实现主域名下的不同子域名的跨域操作，
我们可以使用设置 document.domain 来解决。
（1）将 document.domain 设置为主域名，来实现相同子域名的跨域操作，
这个时候主域名下的 cookie 就能够被子域名所访问。
同时如果文档中含有主域名相同，子域名不同的 iframe 的话，
我们也可以对这个 iframe 进行操作。

如果是想要解决不同跨域窗口间的通信问题，比如说一个页面
想要和页面的中的不同源的 iframe 进行通信的问题，我们可以使用 
location.hash 或者 window.name 或者 postMessage 来解决。
（2）使用 location.hash 的方法，我们可以在主页面动态的修改 
iframe 窗口的 hash 值，然后在 iframe 窗口里实现监听函数
来实现这样一个单向的通信。因为在 iframe 是没有办法访问到
不同源的父级窗口的，所以我们不能直接修改父级窗口的 hash 值
来实现通信，我们可以在 iframe 中再加入一个 iframe ，
这个 iframe 的内容是和父级页面同源的，所以我们可以使用
window.parent.parent 来修改最顶级页面的 src，以此来实现双向通信。

（3）使用 window.name 的方法，主要是基于同一个窗口中设置了 
window.name 后不同源的页面也可以访问，所以不同源的子页面
可以首先在 window.name 中写入数据，然后跳转到一个和父级同源的页面。
这个时候父级页面就可以访问同源的子页面中 window.name 
中的数据了，这种方式的好处是可以传输的数据量大。

（4）使用 postMessage 来解决的方法，这是一个 h5 中新增的
一个 api。通过它我们可以实现多窗口间的信息传递，通过获取到
指定窗口的引用，然后调用 postMessage 来发送信息，
在窗口中我们通过对 message 信息的监听来接收信息，
以此来实现不同源间的信息交换。

如果是像解决 ajax 无法提交跨域请求的问题，我们可以使用 jsonp、
cors、websocket 协议、服务器代理来解决问题。
（5）使用 jsonp 来实现跨域请求，它的主要原理是通过动态构建 
script  标签来实现跨域请求，因为浏览器对 script 标签的
引入没有跨域的访问限制 。通过在请求的 url 后指定一个回调函数，
然后服务器在返回数据的时候，构建一个 json 数据的包装，
这个包装就是回调函数，然后返回给前端，前端接收到数据后，
因为请求的是脚本文件，所以会直接执行，这样我们先前定义好的
回调函数就可以被调用，从而实现了跨域请求的处理。
这种方式只能用于 get 请求。

（6）使用 CORS 的方式，CORS 是一个 W3C 标准，全称是"跨域资源共享"。
CORS 需要浏览器和服务器同时支持。目前，所有浏览器都支持该功能，
因此我们只需要在服务器端配置就行。浏览器将 CORS 请求分成两类：
简单请求和非简单请求。对于简单请求，浏览器直接发出 CORS 请求。
具体来说，就是会在头信息之中，增加一个 Origin 字段。Origin 
字段用来说明本次请求来自哪个源。服务器根据这个值，决定是否同意这次请求。
对于如果 Origin 指定的源，不在许可范围内，服务器会返回一个正常的 HTTP 回应。
浏览器发现，这个回应的头信息没有包含 Access-Control-Allow-Origin 字段，
就知道出错了，从而抛出一个错误，ajax 不会收到响应信息。
如果成功的话会包含一些以 Access-Control- 开头的字段。
非简单请求，浏览器会先发出一次预检请求，来判断该域名是否
在服务器的白名单中，如果收到肯定回复后才会发起请求。

（7）使用 websocket 协议，这个协议没有同源限制。

（8）使用服务器来代理跨域的访问请求，就是有跨域的请求操作时
发送请求给后端，让后端代为请求，然后最后将获取的结果发返回。
```

   #### jsonp
在CORS和postMessage以前，我们一直都是通过JSONP来做跨域通信的。
```
JSONP的原理：通过<script>标签的异步加载来实现的。
比如说，实际开发中，我们发现，
head标签里，可以通过<script>标签的src，里面放url，
加载很多在线的插件。这就是用到了JSONP。
JSONP 使用简单且兼容性不错，但是只限于 get 请求。
在开发中可能会遇到多个 JSONP 请求的回调函数名是相同的，
这时候就需要自己封装一个 JSONP

JSONP的实现：
比如说，客户端这样写：
    <script src="http://www.smyhvae.com/?data=name&callback=myjsonp"></script>

上面的src中，data=name是get请求的参数，myjsonp是和后台约定好的函数名。 服务器端这样写：
  myjsonp({
      data: {}
  })
于是，本地要求创建一个myjsonp 的全局函数，才能将返回的数据执行出来。
实际开发中，前端的JSONP是这样实现的：
<script>
    var util = {};
    //定义方法：动态创建 script 标签
    /**
     * [function 在页面中注入js脚本]
     * @param  {[type]} url     [description]
     * @param  {[type]} charset [description]
     * @return {[type]}         [description]
     */
    util.createScript = function (url, charset) {
        var script = document.createElement('script');
        script.setAttribute('type', 'text/javascript');
        charset && script.setAttribute('charset', charset);
        script.setAttribute('src', url);
        script.async = true;
        return script;
    };

    /**
     * [function 处理jsonp]
     * @param  {[type]} url      [description]
     * @param  {[type]} onsucess [description]
     * @param  {[type]} onerror  [description]
     * @param  {[type]} charset  [description]
     * @return {[type]}          [description]
     */
    util.jsonp = function (url, onsuccess, onerror, charset) {
        var callbackName = util.getName('tt_player'); //事先约定好的 函数名
        window[callbackName] = function () {      //根据回调名称注册一个全局的函数
            if (onsuccess && util.isFunction(onsuccess)) {
                onsuccess(arguments[0]);
            }
        };
        var script = util.createScript(url + '&callback=' + callbackName, charset);   //动态创建一个script标签
        script.onload = script.onreadystatechange = function () {   //监听加载成功的事件，获取数据
            if (!script.readyState || /loaded|complete/.test(script.readyState)) {
                script.onload = script.onreadystatechange = null;
                // 移除该script的 DOM 对象
                if (script.parentNode) {
                    script.parentNode.removeChild(script);
                }
                // 删除函数或变量
                window[callbackName] = null;  //最后不要忘了删除
            }
        };
        script.onerror = function () {
            if (onerror && util.isFunction(onerror)) {
                onerror();
            }
        };
        document.getElementsByTagName('head')[0].appendChild(script); //往html中增加这个标签，目的是把请求发送出去
    };
</script>
```

   #### 手写一个jsonp
```js
function jsonp(url, params, callback) {
  // 判断是否含有参数
  let queryString = url.indexOf("?") === "-1" ? "?" : "&";

  // 添加参数
  for (var k in params) {
    if (params.hasOwnProperty(k)) {
      queryString += k + "=" + params[k] + "&";
    }
  }

  // 处理回调函数名
  let random = Math.random()
      .toString()
      .replace(".", ""),
    callbackName = "myJsonp" + random;

  // 添加回调函数
  queryString += "callback=" + callbackName;

  // 构建请求
  let scriptNode = document.createElement("script");
  scriptNode.src = url + queryString;

  window[callbackName] = function() {
    // 调用回调函数
    callback(...arguments);

    // 删除这个引入的脚本
    document.getElementsByTagName("head")[0].removeChild(scriptNode);
  };

  // 发起请求
  document.getElementsByTagName("head")[0].appendChild(scriptNode);
}
```

   #### postMessage
H5中新增的postMessage()方法，可以用来做跨域通信。
```
场景：窗口 A (http:A.com)向跨域的窗口 B (http:B.com)发送信息。步骤如下
在A窗口中操作如下：向B窗口发送数据：
	// 窗口A(http:A.com)向跨域的窗口B(http:B.com)发送信息
 	Bwindow.postMessage('data', 'http://B.com'); //这里强调的是B窗口里的window对象
2. 在B窗口中操作如下：
    // 在窗口B中监听 message 事件
    Awindow.addEventListener('message', function (event) {   //这里强调的是A窗口里的window对象
        console.log(event.origin);  //获取 ：url。这里指：http://A.com
        console.log(event.source);  //获取：A window对象
        console.log(event.data);    //获取传过来的数据
    }, false);
```

   #### CORS
```
CORS：不受同源策略的限制，支持跨域。一种新的通信协议标准。
可以理解成是：同时支持同源和跨域的Ajax。
CORS为什么支持跨域的通信？
跨域时，浏览器会拦截Ajax请求，并在http头中加Origin。

浏览器会自动进行 CORS 通信，实现 CORS 通信的关键是后端。
只要后端实现了 CORS，就实现了跨域。服务端设置 
Access-Control-Allow-Origin 就可以开启 CORS。 
该属性表示哪些域名可以访问资源，如果设置通配符则表示所有网站
都可以访问资源。 虽然设置 CORS和前端没什么关系，但是通过这种方式
解决跨域问题的话，会在发送请求时出现两种情况，分别为简单请求和复杂请求。

简单请求：
以 Ajax 为例，当满足以下条件时，会触发简单请求
1.使用下列方法之一：GET、HEAD、POST
2.Content-Type 的值仅限于下列三者之一：text/plain、
multipart/form-data、application/x-www-form-urlencoded

请求中的任意 XMLHttpRequestUpload 对象均没有注册任何事件监听器； 
XMLHttpRequestUpload 对象可以使用XMLHttpRequest.upload 属性访问

复杂请求：
对于复杂请求来说，首先会发起一个预检请求，该请求是 option 方法的，
通过该请求来知道服务端是否允许跨域请求。
对于预检请求来说，如果你使用过 Node 来设置 CORS 的话，可能会遇到过这么一个坑。

以下以 express框架举例
app.use((req, res, next) => {
  res.header('Access-Control-Allow-Origin', '*')
  res.header('Access-Control-Allow-Methods', 'PUT, GET, POST, DELETE, OPTIONS')
  res.header(
    'Access-Control-Allow-Headers',
    'Origin, X-Requested-With, Content-Type, Accept, Authorization, Access-Control-Allow-Credentials'
  )
  next()
})
该请求会验证你的 Authorization 字段，没有的话就会报错。
当前端发起了复杂请求后，你会发现就算你代码是正确的，
返回结果也永远是报错的。因为预检请求也会进入回调中，
也会触发 next 方法，因为预检请求并不包含 Authorization 字段，
所以服务端会报错。
想解决这个问题很简单，只需要在回调中过滤 option 方法即可

res.statusCode = 204
res.setHeader('Content-Length', '0')
res.end()

  if (req.method == "OPTIONS") {
    res.send(200);
  }
  else {
    next();
  }
  
项目实例：
解决方式是给服务器设置允许跨域的字段，一般需要设置如下几个字段，
以express框架来说，设置允许cros跨域响应头：
app.all("*" , function(req,res,next){
	res.header('Access-Control-Allow-Origin' , "*")  
	res.header('Access-Control-Allow-Headers' , 'Content-Type,Content-length,Authorization,Accept,X-Requested-With,yourHeaderFeild');  
	res.header('Access-Control-Allow-Methods' , 'PUT,POST,GEt,DELETE,OPTIONS');  
	if(req.method == 'OPTIONS'){    
		res.send(200)  
	}  else{    
		next()  
	}
})
上述代码中设置细则如下：  
Access-Control-Allow-Origin：设置允许cros跨域的网址
Access-Control-Allow-Headers：设置允许cros跨域的请求头部
Access-Control-Allow-Methods：设置允许cros跨域的请求方式
```

   #### WebSocket
```
WebSocket不受同源策略的限制，支持跨域
用法如下：
    var ws = new WebSocket('wss://echo.websocket.org'); //创建WebSocket的对象。参数可以是 ws 或 wss，后者表示加密。

    //把请求发出去
    ws.onopen = function (evt) {
        console.log('Connection open ...');
        ws.send('Hello WebSockets!');
    };

    //对方发消息过来时，我接收
    ws.onmessage = function (evt) {
        console.log('Received Message: ', evt.data);
        ws.close();
    };

    //关闭连接
    ws.onclose = function (evt) {
        console.log('Connection closed.');
    };
```

```
由于 http 存在一个明显的弊端（消息只能有客户端推送到服务器端，
而服务器端不能主动推送到客户端），导致如果服务器如果有连续的变化，
这时只能使用轮询，而轮询效率过低，并不适合。于是 WebSocket被发明出来

相比与 http 具有以下优点：
支持双向通信，实时性更强；

可以发送文本，也可以二进制文件；

协议标识符是 ws，加密后是 wss ；

较少的控制开销。连接创建后，ws客户端、服务端进行数据交换时，
协议控制的数据包头部较小。在不包含头部的情况下，服务端到
客户端的包头只有2~10字节（取决于数据包长度），客户端到
服务端的的话，需要加上额外的4字节的掩码。而HTTP协议每次
通信都需要携带完整的头部；

支持扩展。ws协议定义了扩展，用户可以扩展协议，
或者实现自定义的子协议。（比如支持自定义压缩算法等）

无跨域问题。

实现比较简单，服务端库如 socket.io、ws，
可以很好的帮助我们入门。而客户端也只需要参照 api 实现即可
```

   #### proxy代理跨域(最常见)
```
使用vue开发的时候，可以使用vue脚手架自带的http-proxy代理程序进行跨域。
步骤：
1.在vue脚手架中新增配置文件vue.config.js文件，添加一个新的配置项，如下：
module.exports = {	
	devServer:{		
		proxy:{			
			'/api':{				
				target:'http://localhost:3000/'//自己的服务器端口3000							
				changeOrigin:true //打开跨域			
			}		
		}	
	}
}
上述代码中设置了一个接口/api，这个接口作为自己的服务器的代理服务器，
即访问这个接口就如访问http://localhost:3000
然后我们需要将这个/api作为我们提交数据的默认地址，
即在vue项目的mian.js文件中设置如下代码，此处以axios为例：
axios.defalts.baseURL = "/api"
```

  #### 鉴权
什么是鉴权：
```
鉴权（authentication）是指验证用户是否拥有访问系统的权利。
传统的鉴权是通过密码来验证的。这种方式的前提是，
每个获得密码的用户都已经被授权。在建立用户时，就为此用户分配一个密码，
用户的密码可以由管理员指定，也可以由用户自行申请。
这种方式的弱点十分明显：一旦密码被偷或用户遗失密码，
情况就会十分麻烦，需要管理员对用户密码进行重新修改，
而修改密码之前还要人工验证用户的合法身份。

为了克服这种鉴权方式的缺点，需要一个更加可靠的鉴权方式。
目前的主流鉴权方式是利用认证授权来验证数字签名的正确与否。

逻辑上，授权发生在鉴权之后，而实际上，这两者常常是一个过程。
```

常用的鉴权有四种：
```
1、HTTP Basic Authentication
2、session-cookie
3、Token验证
4、OAuth(开放授权)
```

鉴权分类：
```
用户鉴权，网络对用户进行鉴权，防止非法用户占用网络资源。
网络鉴权，用户对网络进行鉴权，防止用户接入了非法的网络，被骗取关键信息。
这种双向的认证机制，就是AKA
（Authentication and Key Agreement，鉴权和密钥协商）鉴权。

除了AKA鉴权，也可以使用其它鉴权方式。在IMS AKA鉴权广泛实施之前，
或在特定的条件下（例如通过固定网络ADSL连接方式接入IMS），
可以使用HTTP摘要鉴权等其他鉴权方式。

3G UMTS（Universal Mobile Telecommunication System，通用移动通讯系统）、
EPS（Evolved Packet System，演进的分组系统）、
IMS（IP Multimedia Subsystem，IP多媒体子系统）
网络都采用了AKA双向鉴权机制，鉴权原理也大致相同。
而2G网络，只有用户鉴权，无网络鉴权。
```

```
鉴权时机：
移动网络对鉴权时机的要求为：
2G、3G网络中，鉴权发生在开机、呼叫、位置更新以及在补充业务的
激活、去活、登记或删除操作之前。
2G网络中，运营商都是启用的“按比例鉴权”方案。
3G网络中，用户首次接入网络必须鉴权，此后启用“按比例鉴权”方案。
IMS网络中，网络可以通过注册或重注册过程，在任何时候对用户进行鉴权。
```

   #### HTTP Basic Authentication
```
这种授权方式是浏览器遵守http协议实现的基本授权方式,
HTTP协议进行通信的过程中，
HTTP协议定义了基本认证认证允许HTTP服务器对
客户端进行用户身份证的方法。

认证过程：
1．客户端向服务器请求数据，请求的内容可能是一个网页
或者是一个ajax异步请求，
此时，假设客户端尚未被验证，则客户端提供如下请求至服务器:
Get /index.html HTTP/1.0
Host:www.google.com

2． 服务器向客户端发送验证请求代码401,
（WWW-Authenticate: Basic realm=”google.com”这句话是关键，
如果没有客户端不会弹出用户名和密码输入界面）服务器返回的数据大抵如下：
HTTP/1.0 401 Unauthorised
Server: SokEvo/1.0
WWW-Authenticate: Basic realm=”google.com”
Content-Type: text/html
Content-Length: xxx

3． 当符合http1.0或1.1规范的客户端（如IE，FIREFOX）收到401返回值时，
将自动弹出一个登录窗口，要求用户输入用户名和密码。

4． 用户输入用户名和密码后，将用户名及密码以BASE64加密方式加密，
并将密文放入前一条请求信息中，则客户端发送的第一条请求信息
则变成如下内容：
Get /index.html HTTP/1.0
Host:www.google.com
Authorization: Basic d2FuZzp3YW5n

注：d2FuZzp3YW5n表示加密后的用户名及密码（用户名：密码 然后通过base64加密，
加密过程是浏览器默认的行为，不需要我们人为加密，我们只需要输入用户名密码即可）

5． 服务器收到上述请求信息后，将Authorization字段后的用户信息
取出、解密，将解密后的用户名及密码与用户数据库进行比较验证，
如用户名及密码正确，服务器则根据请求，将所请求资源发送给客户端。

效果：
客户端未未认证的时候，会弹出用户名密码输入框，
这个时候请求时属于pending状态，
这个时候其实服务当用户输入用户名密码的时候客户端
会再次发送带Authentication头的请求。
```

   #### session-cookie
```
HTTP Cookie（也叫Web Cookie或浏览器Cookie）是服务器发送到
用户浏览器并保存在本地的一小块数据，它会在浏览器下次向
同一服务器再发起请求时被携带并发送到服务器上。通常，
它用于告知服务端两个请求是否来自同一浏览器，如保持用户的登录状态。
Cookie使基于无状态的HTTP协议记录稳定的状态信息成为了可能。

Cookie主要用于以下三个方面：
会话状态管理（如用户登录状态、购物车、游戏分数或其它需要记录的信息）
个性化设置（如用户自定义设置、主题等）
浏览器行为跟踪（如跟踪分析用户行为等）

认证过程：
1.服务器在接受客户端首次访问时在服务器端创建seesion，然后
保存seesion(我们可以将seesion保存在内存中，也可以保存在redis中，
推荐使用后者)，然后给这个session生成一个唯一的标识字符串,
然后在响应头中种下这个唯一标识字符串。

2.签名。这一步只是对sid进行加密处理，
3.服务端会根据这个secret密钥进行解密。（非必需步骤）

3.浏览器中收到请求响应的时候会解析响应头，然后将sid保存在本地cookie中，
浏览器在下次http请求的请求头中会带上该域名下的cookie信息。

4.服务器在接受客户端请求时会去解析请求头cookie中的sid，然后根据这个sid
去找服务器端保存的该客户端的session，然后判断该请求是否合法。

5.一旦用户登出，服务端和客户端同时销毁该会话在后续请求中，
6.服务器会根据数据库验证会话id，如果验证通过，则继续处理；
```

   #### token验证
```
认证过程：
1.用户输入登陆凭据；
2.服务器验证凭据是否正确，然后返回一个经过签名的token；
3.客户端负责存储token，可以存在localstorage，或者cookie中
4.对服务器的请求带上这个token；
5.服务器对JWT进行解码，如果token有效，则处理该请求；
6.一旦用户登出，客户端销毁token。

cookie与token性能对比：cookie与token看上去很像，但是有区别
1.sessionid 他只是一个唯一标识的字符串，服务端是根据这个字符串，
来查询在服务器端保持的seesion，这里面才保存着用户的登陆状态。
但是token本身就是一种登陆成功凭证，他是在登陆成功后根据某种规则生成的
一种信息凭证，他里面本身就保存着用户的登陆状态。
服务器端只需要根据定义的规则校验这个token是否合法就行。

2.session-cookie是需要cookie配合的，居然要cookie，
3.那么在http代理客户端的选择上就是只有浏览器了，
因为只有浏览器才会去解析请求响应头里面的cookie,
然后每次请求再默认带上该域名下的cookie。
但是我们知道http代理客户端不只有浏览器，还有原生APP等等，
这个时候cookie是不起作用的，或者浏览器端是可以禁止cookie的，
但是token就不一样，他是登陆请求在登陆成功后再请求响应体中返回的信息，
客户端在收到响应的时候，可以把他存在本地的cookie,storage，
或者内存中，然后再下一次请求的请求头重带上这个token就行了。
简单点来说cookie-session机制他限制了客户端的类型，
而token验证机制丰富了客户端类型。

3.时效性。session-cookie的sessionid实在登陆的时候生成的
而且在登出事时一直不变的，在一定程度上安全就会低，
而token是可以在一段时间内动态改变的。

4.可扩展性。token验证本身是比较灵活的，一是token的解决方案
有许多，常用的是JWT，二来我们可以基于token验证机制，
专门做一个鉴权服务，用它向多个服务的请求进行统一鉴权。
```

   #### OAuth
```
(开放授权)
OAUTH协议为用户资源的授权提供了一个安全的、开放而又简易的标准。
与以往的授权方式不同之处是OAUTH的授权不会使第三方触及到用户的
帐号信息（如用户名与密码），即第三方无需使用用户的用户名与密码
就可以申请获得该用户资源的授权，因此OAUTH是安全的。同时，
任何第三方都可以使用OAUTH认证服务，任何服务提供商都
可以实现自身的OAUTH认证服务，因而OAUTH是开放的。

我们常见的提供OAuth认证服务的厂商有支付宝，QQ，微信。

OAuth协议又有1.0和2.0两个版本。相比较1.0版，
2.0版整个授权验证流程更简单更安全，
也是目前最主要的用户身份验证和授权方式。

典型案例：
如果一个用户拥有两项服务：一项服务是图片在线存储服务A，
另一个是图片在线打印服务B。由于服务A与服务B是由两家不同
的服务提供商提供的，所以用户在这两家服务提供商的网站上
各自注册了用户，假设这两个用户名各不相同，密码也各不相同。

当用户要使用服务B打印存储在服务A上的图片时，用户该如何处理？
方法一：用户可能先将待打印的图片从服务A上下载下来并上传到
服务B上打印，这种方式安全但处理比较繁琐，效率低下；

方法二：用户将在服务A上注册的用户名与密码提供给服务B，
服务B使用用户的帐号再去服务A处下载待打印的图片，
这种方式效率是提高了，但是安全性大大降低了，
服务B可以使用用户的用户名与密码去服务A上查看甚至篡改用户的资源。

方法三：当服务B（打印服务）要访问用户的服务A（图片服务）时，
通过OAUTH机制，服务B向服务A请求未经用户授权的RequestToken后，
服务A将引导用户在服务A的网站上登录，并询问用户是否将
图片服务授权给服务B。用户同意后，服务B就可以访问用户
在服务A上的图片服务。整个过程服务B没有触及到用户在服务A的帐号信息。

OAuth相关术语：
在认证和授权的过程中涉及的三方包括：
(1)服务提供方（ServiceProvider），用户使用服务提供方来
存储受保护的资源，如照片，视频，联系人列表。
(2)用户（User），存放在服务提供方的受保护的资源的拥有者
(3)客户端（Consumer），要访问服务提供方资源的第三方应用，
通常是网站，如提供照片打印服务的网站
也可以是桌面或移动应用程序。在认证过程之前，
客户端要向服务提供者申请客户端标识。

OAuth相关的三个URL：
RequestToken URL:获取未授权的RequestToken服务地址；
UserAuthorization URL:获取用户授权的RequestToken服务地址；
AccessToken URL:用授权的RequestToken换取AccessToken的服务地址。

OAuth认证和授权过程：
(1)客户端（第三方软件）向OAUTH服务提供商请求未授权的RequestToken。
即向RequestToken URL发起请求；
(2)OAUTH服务提供商同意使用者的请求，并向其颁发未经用户授权
的oauth_token与对应的oauth_token_secret，并返回给使用者；
(3)使用者向OAUTH服务提供商请求用户授权的RequestToken。
即向UserAuthorization URL发起请求并在请求中携带
上一步服务提供商颁发的未授权的token与其密钥；
(4)OAUTH服务提供商通过网页要求用户登录并引导用户完成授权；
(5)RequestToken授权后，使用者将向AccessToken URL发起请求，
将上步授权的RequestToken换取成AccessToken。
请求的参数见上图，这个比第一步多了一个参数就是RequestToken；
(6)OAUTH服务提供商同意使用者的请求，并向其颁发AccessToken
与对应的密钥，并返回给使用者；
(7)使用者以后就可以使用上步返回的AccessToken访问用户授权的资源。

简单整理就三个步骤：
1.获取未授权的RequestToken
2.获取用户授权的RequestToken
3.用授权的RequestToken换取AccessToken
```

  #### 哪些操作会造成内存泄漏
```
第一种情况是我们由于使用未声明的变量，而意外的创建了一个全局变量，
而使这个变量一直留在内存中无法被回收。

第二种情况是我们设置了 setInterval 定时器，而忘记取消它，
如果循环函数有对外部变量的引用的话，那么这个变量会被
一直留在内存中，而无法被回收。

第三种情况是我们获取一个 DOM 元素的引用，而后面这个元素被删除，
由于我们一直保留了对这个元素的引用，所以它也无法被回收。

第四种情况是不合理的使用闭包，从而导致某些变量一直被留在内存当中。
```

```
1.意外的全局变量
2.被遗忘的计时器或回调函数
3.脱离 DOM 的引用
4.闭包
```

```
JavaScript 内存泄露指对象在不需要使用它时仍然存在，
导致占用的内存不能使用或回收

未使用 var 声明的全局变量
闭包函数(Closures)

循环引用(两个对象相互引用)

控制台日志(console.log)

移除存在绑定事件的DOM元素(IE)

setTimeout 的第一个参数使用字符串而非函数的话，会引发内存泄漏

垃圾回收器定期扫描对象，并计算引用了每个对象的其他对象的数量。
如果一个对象的引用数量为 0（没有其他对象引用过该对象），
或对该对象的惟一引用是循环的，那么该对象的内存即可回收

内存泄漏指任何对象在您不再拥有或需要它之后仍然存在
setTimeout 的第一个参数使用字符串而非函数的话，会引发内存泄漏
闭包、控制台日志、循环（在两个对象彼此引用且彼此保留时，就会产生一个循环）
```

  #### 常见web安全及防护原理
```
sql注入原理：
就是通过把SQL命令插入到Web表单递交或输入域名或页面请求的
查询字符串，最终达到欺骗服务器执行恶意的SQL命令

总的来说有以下几点：
永远不要信任用户的输入，要对用户的输入进行校验，
可以通过正则表达式，或限制长度，对单引号和双"-"进行转换等
永远不要使用动态拼装SQL，可以使用参数化的SQL或者
直接使用存储过程进行数据查询存取，永远不要使用
管理员权限的数据库连接，为每个应用使用单独的权限有限的数据库连接
不要把机密信息明文存放，请加密或者hash掉密码和敏感的信息

XSS原理及防范：
Xss(cross-site scripting)攻击指的是攻击者往Web页面里
插入恶意html标签或者javascript代码。比如：
攻击者在论坛中放一个看似安全的链接，骗取用户点击后，
窃取cookie中的用户私密信息；或者攻击者在论坛中加
一个恶意表单，当用户提交表单的时候，却把信息传送到
攻击者的服务器中，而不是用户原本以为的信任站点

XSS防范方法：
首先代码里对用户输入的地方和变量都需要仔细检查长度和对”<”,”>”,”;”,”’”等
字符做过滤；其次任何内容写到页面之前都必须加以encode，
避免不小心把html tag 弄出来。这一个层面做好，至少可以堵住超过一半的XSS 攻击

XSS与CSRF有什么区别吗？
XSS是获取信息，不需要提前知道其他用户页面的代码和数据包。
CSRF是代替用户完成指定的动作，需要知道其他用户页面的代码和
数据包。要完成一次CSRF攻击，受害者必须依次完成两个步骤

登录受信任网站A，并在本地生成Cookie

在不登出A的情况下，访问危险网站B

CSRF的防御：
服务端的CSRF方式方法很多样，但总的思想都是一致的，
就是在客户端页面增加伪随机数通过验证码的方法
```

  #### 什么是XSS攻击？如何防范XSS攻击
```
XSS 攻击指的是跨站脚本攻击，是一种代码注入攻击。
攻击者通过在网站注入恶意脚本，使之在用户的浏览器上运行，
从而盗取用户的信息如 cookie 等。

XSS 的本质是因为网站没有对恶意代码进行过滤，与正常的代码
混合在一起了，浏览器没有办法分辨哪些脚本是可信的，
从而导致了恶意代码的执行。

XSS 一般分为存储型、反射型和 DOM 型。

存储型指的是恶意代码提交到了网站的数据库中，当用户请求数据
的时候，服务器将其拼接为 HTML 后返回给了用户，
从而导致了恶意代码的执行。

反射型指的是攻击者构建了特殊的 URL，当服务器接收到请求后，
从 URL 中获取数据，拼接到 HTML 后返回，从而导致了恶意代码的执行。

DOM 型指的是攻击者构建了特殊的 URL，用户打开网站后，
js 脚本从 URL 中获取数据，从而导致了恶意代码的执行。

XSS 攻击的预防可以从两个方面入手，一个是恶意代码提交的时候，
一个是浏览器执行恶意代码的时候。

对于第一个方面，如果我们对存入数据库的数据都进行的转义处理，
但是一个数据可能在多个地方使用，有的地方可能不需要转义，
由于我们没有办法判断数据最后的使用场景，
所以直接在输入端进行恶意代码的处理，其实是不太可靠的。

因此我们可以从浏览器的执行来进行预防，一种是使用纯前端的方式，
不用服务器端拼接后返回。另一种是对需要插入到 HTML 中的代码
做好充分的转义。对于 DOM 型的攻击，主要是前端脚本的不可靠而造成的，
我们对于数据获取渲染和字符串拼接的时候应该对可能出现的恶意代码情况进行判断。

还有一些方式，比如使用 CSP ，CSP 的本质是建立一个白名单，
告诉浏览器哪些外部资源可以加载和执行，从而防止恶意代码的注入攻击。

还可以对一些敏感信息进行保护，比如 cookie 使用 http-only ，
使得脚本无法获取。也可以使用验证码，避免脚本伪装成用户执行一些操作。
```

  #### 什么是CSRF攻击？如何防范CSRF攻击
```
CSRF 攻击指的是跨站请求伪造攻击，攻击者诱导用户进入一个
第三方网站，然后该网站向被攻击网站发送跨站请求。
如果用户在被攻击网站中保存了登录状态，那么攻击者就
可以利用这个登录状态，绕过后台的用户验证，
冒充用户向服务器执行一些操作。

CSRF 攻击的本质是利用了 cookie 会在同源请求中携带
发送给服务器的特点，以此来实现用户的冒充。

一般的 CSRF 攻击类型有三种：
第一种是 GET 类型的 CSRF 攻击，比如在网站中的一个 img 标签
里构建一个请求，当用户打开这个网站的时候就会自动发起提交。

第二种是 POST 类型的 CSRF 攻击，比如说构建一个表单，
然后隐藏它，当用户进入页面时，自动提交这个表单。

第三种是链接类型的 CSRF 攻击，比如说在 a 标签的 href 
属性里构建一个请求，然后诱导用户去点击。

CSRF 可以用下面几种方法来防护：
第一种是同源检测的方法，服务器根据 http 请求头中 origin 或者 
referer 信息来判断请求是否为允许访问的站点，从而对请求进行过滤。
当 origin 或者 referer 信息都不存在的时候，直接阻止。
这种方式的缺点是有些情况下 referer 可以被伪造。还有就是我们这种
方法同时把搜索引擎的链接也给屏蔽了，所以一般网站会允许搜索引擎
的页面请求，但是相应的页面请求这种请求方式也可能被攻击者给利用。

第二种方法是使用 CSRF Token 来进行验证，服务器向用户返回一个
随机数 Token ，当网站再次发起请求时，在请求参数中加入服务器端
返回的 token ，然后服务器对这个 token 进行验证。这种方法解决了
使用 cookie 单一验证方式时，可能会被冒用的问题，但是这种方法
存在一个缺点就是，我们需要给网站中的所有请求都添加上这个 token，
操作比较繁琐。还有一个问题是一般不会只有一台网站服务器，
如果我们的请求经过负载平衡转移到了其他的服务器，但是这个服务器
的 session 中没有保留这个 token 的话，就没有办法验证了。
这种情况我们可以通过改变 token 的构建方式来解决。

第三种方式使用双重 Cookie 验证的办法，服务器在用户访问网站页面时，
向请求域名注入一个Cookie，内容为随机字符串，然后当用户再次向服务器
发送请求的时候，从 cookie 中取出这个字符串，添加到 URL 参数中，
然后服务器通过对 cookie 中的数据和参数中的数据进行比较，来进行验证。
使用这种方式是利用了攻击者只能利用 cookie，但是不能访问获取 cookie 
的特点。并且这种方法比 CSRF Token 的方法更加方便，并且不涉及到
分布式访问的问题。这种方法的缺点是如果网站存在 XSS 漏洞的，
那么这种方式会失效。同时这种方式不能做到子域名的隔离。

第四种方式是使用在设置 cookie 属性的时候设置 Samesite ，限制 cookie 
不能作为被第三方使用，从而可以避免被攻击者利用。Samesite 一共有
两种模式，一种是严格模式，在严格模式下 cookie 在任何情况下都不可能
作为第三方 Cookie 使用，在宽松模式下，cookie 可以被请求是 GET 请求，
且会发生页面跳转的请求所使用。
```

  #### SQL注入攻击
```
SQL 注入攻击指的是攻击者在 HTTP 请求中注入恶意的 SQL 代码，
服务器使用参数构建数据库 SQL 命令时，恶意 SQL 被一起构造，
破坏原有 SQL 结构，并在数据库中执行，
达到编写程序时意料之外结果的攻击行为。
```

  #### 什么是CSP
```
CSP 指的是内容安全策略，它的本质是建立一个白名单，
告诉浏览器哪些外部资源可以加载和执行。我们只需要配置
规则，如何拦截由浏览器自己来实现。

通常有两种方式来开启 CSP，一种是设置 HTTP 首部中的 
Content-Security-Policy，一种是设置 meta 标签的方式 
<metahttp-equiv="Content-Security-Policy">
```

  #### 什么是点击劫持？如何防范点击劫持
```
点击劫持是一种视觉欺骗的攻击手段，攻击者将需要攻击的网站通过
iframe 嵌套的方式嵌入自己的网页中，
并将 iframe 设置为透明，在页面中透出一个按钮诱导用户点击。

我们可以在 http 相应头中设置 X-FRAME-OPTIONS 来防御用 
iframe 嵌套的点击劫持攻击。通过不同的值，
可以规定页面在特定的一些情况才能作为 iframe 来使用。
```

### Ajax和axios

  #### Ajax是什么?原理?如何创建一个Ajax
```
我对 ajax 的理解是，它是一种异步通信的方法，通过直接由 
js 脚本向服务器发起 http 通信，然后根据服务器返回的数据，
更新网页的相应部分，而不用刷新整个页面的一种方法。

创建一个 ajax 有这样几个步骤：
首先是创建一个 XMLHttpRequest 对象。

然后在这个对象上使用 open 方法创建一个 http 请求，
open 方法所需要的参数是请求的方法、请求的地址、
是否异步和用户的认证信息。

在发起请求前，我们可以为这个对象添加一些信息和监听函数。
比如说我们可以通过 setRequestHeader 方法来为请求添加头信息。
我们还可以为这个对象添加一个状态监听函数。一个 XMLHttpRequest 
对象一共有 5 个状态，当它的状态变化时会触发onreadystatechange 
事件，我们可以通过设置监听函数，来处理请求成功后的结果。
当对象的 readyState 变为 4 的时候，代表服务器返回的数据接收完成，
这个时候我们可以通过判断请求的状态，如果状态是 2xx 或者 304 
的话则代表返回正常。这个时候我们就可以通过 response 
中的数据来对页面进行更新了。

当对象的属性和监听函数设置完成后，最后我们调用 sent 
方法来向服务器发起请求，可以传入参数作为发送的数据体。
```

一般实现：
```js
const SERVER_URL = "/server";

let xhr = new XMLHttpRequest();

// 创建 Http 请求
xhr.open("GET", SERVER_URL, true);

// 设置状态监听函数
xhr.onreadystatechange = function() {
  if (this.readyState !== 4) return;

  // 当请求成功时
  if (this.status === 200) {
    handle(this.response);
  } else {
    console.error(this.statusText);
  }
};

// 设置请求失败时的监听函数
xhr.onerror = function() {
  console.error(this.statusText);
};

// 设置请求头信息
xhr.responseType = "json";
xhr.setRequestHeader("Accept", "application/json");

// 发送 Http 请求
xhr.send(null);

// promise 封装实现：

function getJSON(url) {
  // 创建一个 promise 对象
  let promise = new Promise(function(resolve, reject) {
    let xhr = new XMLHttpRequest();

    // 新建一个 http 请求
    xhr.open("GET", url, true);

    // 设置状态的监听函数
    xhr.onreadystatechange = function() {
      if (this.readyState !== 4) return;

      // 当请求成功或失败时，改变 promise 的状态
      if (this.status === 200) {
        resolve(this.response);
      } else {
        reject(new Error(this.statusText));
      }
    };

    // 设置错误监听函数
    xhr.onerror = function() {
      reject(new Error(this.statusText));
    };

    // 设置响应的数据类型
    xhr.responseType = "json";

    // 设置请求头信息
    xhr.setRequestHeader("Accept", "application/json");

    // 发送 http 请求
    xhr.send(null);
  });

  return promise;
}
```

```
Ajax的原理简单来说是在用户和服务器之间加了—个中间层(AJAX引擎)，
通过XmlHttpRequest对象来向服务器发异步请求，从服务器获得数据，
然后用javascript来操作DOM而更新页面。使用户操作与服务器响应异步化。
这其中最关键的一步就是从服务器获得请求数据

Ajax的过程只涉及JavaScript、XMLHttpRequest和DOM。
XMLHttpRequest是ajax的核心机制
/** 1. 创建连接 **/
var xhr = null;
xhr = new XMLHttpRequest()
/** 2. 连接服务器 **/
xhr.open('get', url, true)
/** 3. 发送请求 **/
xhr.send(null);
/** 4. 接受请求 **/
xhr.onreadystatechange = function(){
	if(xhr.readyState == 4){
		if(xhr.status == 200){
			success(xhr.responseText);
		} else { 
			/** false **/
			fail && fail(xhr.status);
		}
	}
}

ajax 有那些优缺点?
优点：
通过异步模式，提升了用户体验.

优化了浏览器和服务器之间的传输，减少不必要的数据往返，减少了带宽占用.

Ajax在客户端运行，承担了一部分本来由服务器承担的工作，减少了大用户量下的服务器负载。

Ajax可以实现动态不刷新（局部刷新）

缺点：
安全问题 AJAX暴露了与服务器交互的细节。

对搜索引擎的支持比较弱。

不容易调试。
```

```
2005 年 2 月，AJAX 这个词第一次正式提出，它是 
Asynchronous JavaScript and XML 的缩写，指的是通过 
JavaScript 的异步通信，从服务器获取 XML 文档从中提取数据，
再更新当前网页的对应部分，而不用刷新整个网页。

具体来说，AJAX 包括以下几个步骤。
1.创建 XMLHttpRequest 对象，也就是创建一个异步调用对象
2.创建一个新的 HTTP 请求，并指定该 HTTP 请求的方法、URL 及验证信息
3.设置响应 HTTP 请求状态变化的函数
4.发送 HTTP 请求
5.获取异步调用返回的数据
6.使用 JavaScript 和 DOM 实现局部刷新
```

#### Ajax总结
- Ajax的原理简单来说是在用户和服务器之间加了—个中间层(AJAX引擎)，通过XmlHttpRequest对象来向服务器发异步请求，从服务器获得数据，然后用javascript来操作DOM而更新页面。使用户操作与服务器响应异步化。这其中最关键的一步就是从服务器获得请求数据
- Ajax的过程只涉及JavaScript、XMLHttpRequest和DOM。XMLHttpRequest是ajax的核心机制
```
// 1. 创建连接
var xhr = null;
xhr = new XMLHttpRequest()
// 2. 连接服务器
xhr.open('get', url, true)
// 3. 发送请求
xhr.send(null);
// 4. 接受请求
xhr.onreadystatechange = function(){
    if(xhr.readyState == 4){
        if(xhr.status == 200){
            success(xhr.responseText);
        } else { // fail
            fail && fail(xhr.status);
        }
    }
}
```
ajax 有那些优缺点?
优点：
- 通过异步模式，提升了用户体验.
- 优化了浏览器和服务器之间的传输，减少不必要的数据往返，减少了带宽占用.
- Ajax在客户端运行，承担了一部分本来由服务器承担的工作，减少了大用户量下的服务器负载。
- Ajax可以实现动态不刷新（局部刷新）

缺点：
- 安全问题 AJAX暴露了与服务器交互的细节。
- 对搜索引擎的支持比较弱。
- 不容易调试。

  #### ajax、axios、fetch区别
fetch
- fetch是基于promise实现的，也可以结合async/await。
- fetch请求默认是不带cookie的，需要设置fetch（URL，{credentials:’include’})。
Credentials有三种参数：same-origin，include，*
- 服务器返回400 500 状态码时并不会reject，只有网络出错导致请求不能完成时，fetch才会被reject。
- 所有版本的 IE 均不支持原生 Fetch。
- fetch是widow的一个方法；

ajax
- 是XMLHTTPRequest的一个实例；
- 只有当状态为200或者304时才会请求成功；

Ajax
- Ajax前后端数据通信「同源、跨域」
```
let xhr = new XMLHttpRequest;
xhr.open('get', 'http://127.0.0.1:8888/user/list');
xhr.onreadystatechange = function () {
    if (xhr.readyState === 4 && xhr.status === 200) {
        let text = xhr.responseText;
        console.log(JSON.parse(text));
    }
};
xhr.send(); 
```
```$.ajax({
    url: 'http://127.0.0.1:8888/user/list',
    method: 'get',
    success(result) {
        console.log(result);
    }
});

// 用户登录
// 登录成功 -> 获取用户信息

/* 回调地狱 */
$.ajax({
    url: 'http://127.0.0.1:8888/user/login',
    method: 'post',
    data: Qs.stringify({
        account: '18310612838',
        password: md5('1234567890')
    }),
    success(result) {
        if (result.code === 0) {
            // 登录成功
            $.ajax({
                url: 'http://127.0.0.1:8888/user/list',
                method: 'get',
                success(result) {
                    console.log(result);
                }
            });
        }
    }
});
```

Axios
- Axios也是对ajax的封装，基于Promise管理请求，解决回调地狱问题
```
(async function () {
    let result = await axios.post('/user/login', {
        account: '18310612838',
        password: md5('1234567890')
    });

    result = await axios.get('/user/list');
    console.log(result);
})(); 
```

Fetch
- Fetch是ES6新增的通信方法，不是ajax，但是他本身实现数据通信，就是基于promise管理的
```
(async function () {
    let result = await fetch('http://127.0.0.1:8888/user/login', {
        method: 'post',
        headers: {
            'Content-Type': 'application/x-www-form-urlencoded'
        },
        body: Qs.stringify({
            account: '18310612838',
            password: md5('1234567890')
        })
    }).then(response => {
        return response.json();
    });

    result = await fetch('http://127.0.0.1:8888/user/list').then(response => {
        return response.json();
    });
    console.log(result);
})(); 
```

```
jQuery ajax

$.ajax({
   type: 'POST',
   url: url,
   data: data,
   dataType: dataType,
   success: function () {},
   error: function () {}
});

优缺点：
本身是针对MVC的编程,不符合现在前端MVVM的浪潮
基于原生的XHR开发，XHR本身的架构不清晰，已经有了fetch的替代方案
JQuery整个项目太大，单纯使用ajax却要引入整个JQuery非常的不合理
（采取个性化打包的方案又不能享受CDN服务）

axios：
axios({
    method: 'post',
    url: '/user/12345',
    data: {
        firstName: 'Fred',
        lastName: 'Flintstone'
    }
})
.then(function (response) {
    console.log(response);
})
.catch(function (error) {
    console.log(error);
});

优缺点：
从浏览器中创建 XMLHttpRequest
从 node.js 发出 http 请求
支持 Promise API
拦截请求和响应
转换请求和响应数据
取消请求
自动转换JSON数据
客户端支持防止CSRF/XSRF

fetch：
try {
  let response = await fetch(url);
  let data = response.json();
  console.log(data);
} catch(e) {
  console.log("Oops, error", e);

}

优缺点：
fetcht只对网络请求报错，对400，500都当做成功的请求，需要封装去处理

fetch默认不会带cookie，需要添加配置项

fetch不支持abort，不支持超时控制，使用setTimeout及Promise.reject
的实现的超时控制并不能阻止请求过程继续在后台运行，造成了量的浪费

fetch没有办法原生监测请求的进度，而XHR可以
```

#### 关于http,XMLHttpRequest,Ajax的关系
- http是浏览器和web服务器交换数据的协议,规范
- XMLHttpRequest是一个JS对象，是浏览器实现的一组api函数，使用这些函数，浏览器再通过http协议请求和发送数据。
- Ajax是一种技术方案，但并不是一种新技术，它最核心的就是依赖浏览器提供的XMLHttpRequest对象。用一句话来概括就是我们使用XMLHttpRequest对象来发送一个Ajax请求。

XMLHttpRequest的发展历程是怎样的？
- 它最开始只是微软浏览器提供的一个接口，后来各大浏览器纷纷效仿也提供了这个接口，再后来W3C对它进行了标准化，提出了XMLHttpRequest标准。标准又分为Level 1和Level 2。

Level 2相对于Level 1做了很大的改进，具体来说是：
- 可以设置HTTP请求的超时时间。
- 可以使用FormData对象管理表单数据。
- 可以上传文件。
- 可以请求不同域名下的数据（跨域请求）。
- 可以获取服务器端的二进制数据。
- 可以获得数据传输的进度信息。

使用XMLHttpRequest封装一个get和post请求
get请求：
核心就四步：
- var xhr = new XMLHttpRequest()
- xhr.open('GET', 'http://www.example.com/api/getname', true)
- xhr.onreadystatechange = function () {}
- xhr.send()

让我们来封装一个简易版的：
```
/*
* xhr的get请求
* @param url: 请求地址
* @param params: 请求参数
* @param onSuccess: 成功回调函数
* @param onError: 失败回调函数
*/
function xhrGet (url, params = {}, onSuccess, onError) {
  // 兼容IE6
  var xhr = window.XMLHttpRequest ? new XMLHttpRequest() : new ActiveXObject('Microsoft.XMLHTTP');
  let paramString = formatParams(params);
  // xhr.open的第三个参数isAsync：是否异步 
  xhr.open('GET', `${url}${paramString}`, true);
  xhr.onreadystatechange = function () {
    // console.log(e);
    console.log(this);
    if (this.readyState === 4) {
      if (this.status >= 200 && this.status < 300) {
        onSuccess(this.response);
      } else {
        onError(this.response)
      }
    }
  }
  xhr.send();
}
// 处理参数：如将{name: 'lindaidai'}转为'?name=lindaidai'
function formatParams (params) {
  var paramString = Object.keys(params).map(key => {
    return `${key}=${encodeURIComponent(params[key])}`
  }).join('&');
  return paramString ? `?${paramString}` : ''
}
```
```
（当然上面的兼容IE6估计现在考的不多了，而且我这种写法其实
也没啥用，因为如果真是在IE6下的话，后面的Object.keys()等
方法也用不了了）
```

需要注意的是两种状态，一个是readyState，一个是status。

readyState请求状态：
- 0（未初始化）：还没有调用 open() 方法。
- 1（载入）：已调用 send() 方法，正在发送请求。
- 2（载入完成）：send() 方法完成，已收到全部响应内容。
- 3（解析）：正在解析响应内容。
- 4（完成）：响应内容解析完成，可以在客户端调用。

status结果状态码：
- 0 ：如果状态是 UNSENT 或 OPENED；或者如果错误标签被设置(例如跨域时)
- 200 成功
- 其它HTTP状态码

post请求：
```
function xhrPost (url, params, onSuccess, onError) {
  var xhr = new XMLHttpRequest();
  xhr.open('POST', url, true);
  // ajax的默认请求ContentType:text/plain(纯文本)
  xhr.setRequestHeader("Content-Type", "application-x-www-form-urlencode");
  xhr.onreadystatechange = function () {
    if (this.readyState === 4) {
      if (this.status >= 200 && this.status < 300) {
        onSuccess(this.response);
      } else {
        onError(this.response);
      }
    }
  }
  xhr.send(params);
}
```

### 概念

  #### 写JavaScript的基本规范
```
在平常项目开发中，我们遵守一些这样的基本规范，比如说：

（1）一个函数作用域中所有的变量声明应该尽量提到函数首部，
用一个 var 声明，不允许出现两个连续的 var 声明，声明时
如果变量没有值，应该给该变量赋值对应类型的初始值，
便于他人阅读代码时，能够一目了然的知道变量对应的类型值。

（2）代码中出现地址、时间等字符串时需要使用常量代替。

（3）在进行比较的时候吧，尽量使用'===', '!=='代替'==', '!='。

（4）不要在内置对象的原型上添加方法，如 Array, Date。

（5）switch 语句必须带有 default 分支。

（6）for 循环必须使用大括号。

（7）if 语句必须使用大括号。
```

```
不要在同一行声明多个变量
请使用===/!==来比较true/false或者数值
使用对象字面量替代new Array这种形式
不要使用全局函数
Switch语句必须带有default分支
If语句必须使用大括号
for-in循环中的变量 应该使用var关键字明确限定作用域，从而避免作用域污
```

```
代码缩进，建议使用“四个空格”缩进
代码段使用花括号{}包裹
语句结束使用分号;
变量和函数在使用前进行声明
以大写字母开头命名构造函数，全大写命名常量
规范定义JSON对象，补全双引号
用{}和[]声明对象和数组
```

  #### js的节流与防抖
```
函数防抖是指在事件被触发 n 秒后再执行回调，如果在这 n 秒
内事件又被触发，则重新计时。这可以使用在一些点击请求的事件上，
避免因为用户的多次点击向后端发送多次请求。

函数节流是指规定一个单位时间，在这个单位时间内，只能有一次
触发事件的回调函数执行，如果在同一个单位时间内某事件被触发多次，
只有一次能生效。节流可以使用在 scroll 函数的事件监听上，
通过事件节流来降低事件调用的频率。
```

```
防抖：
在滚动事件中需要做个复杂计算或者实现一个按钮的防二次点击操作。
可以通过函数防抖动来实现

// 使用 underscore 的源码来解释防抖动
/**
 * underscore 防抖函数，返回函数连续调用时，空闲时间必须大于或等于 wait，func 才会执行
 *
 * @param  {function} func        回调函数
 * @param  {number}   wait        表示时间窗口的间隔
 * @param  {boolean}  immediate   设置为ture时，是否立即调用函数
 * @return {function}             返回客户调用函数
 */
_.debounce = function(func, wait, immediate) {
    var timeout, args, context, timestamp, result;

    var later = function() {
      // 现在和上一次时间戳比较
      var last = _.now() - timestamp;
      // 如果当前间隔时间少于设定时间且大于0就重新设置定时器
      if (last < wait && last >= 0) {
        timeout = setTimeout(later, wait - last);
      } else {
        // 否则的话就是时间到了执行回调函数
        timeout = null;
        if (!immediate) {
          result = func.apply(context, args);
          if (!timeout) context = args = null;
        }
      }
    };

    return function() {
      context = this;
      args = arguments;
      // 获得时间戳
      timestamp = _.now();
      // 如果定时器不存在且立即执行函数
      var callNow = immediate && !timeout;
      // 如果定时器不存在就创建一个
      if (!timeout) timeout = setTimeout(later, wait);
      if (callNow) {
        // 如果需要立即执行函数的话 通过 apply 执行
        result = func.apply(context, args);
        context = args = null;
      }

      return result;
    };
  };
整体函数实现

对于按钮防点击来说的实现：
开始一个定时器，只要我定时器还在，不管你怎么点击都不会执行
回调函数。一旦定时器结束并设置为 null，就可以再次点击了

对于延时执行函数来说的实现：每次调用防抖动函数都会判断本次调用
和之前的时间间隔，如果小于需要的时间间隔，就会重新创建一个定时器，
并且定时器的延时为设定时间减去之前的时间间隔。
一旦时间到了，就会执行相应的回调函数

节流：
防抖动和节流本质是不一样的。防抖动是将多次执行变为最后一次执行，
节流是将多次执行变成每隔一段时间执行
/**
 * underscore 节流函数，返回函数连续调用时，func 执行频率限定为 次 / wait
 *
 * @param  {function}   func      回调函数
 * @param  {number}     wait      表示时间窗口的间隔
 * @param  {object}     options   如果想忽略开始函数的的调用，传入{leading: false}。
 *                                如果想忽略结尾函数的调用，传入{trailing: false}
 *                                两者不能共存，否则函数不能执行
 * @return {function}             返回客户调用函数   
 */
_.throttle = function(func, wait, options) {
    var context, args, result;
    var timeout = null;
    // 之前的时间戳
    var previous = 0;
    // 如果 options 没传则设为空对象
    if (!options) options = {};
    // 定时器回调函数
    var later = function() {
      // 如果设置了 leading，就将 previous 设为 0
      // 用于下面函数的第一个 if 判断
      previous = options.leading === false ? 0 : _.now();
      // 置空一是为了防止内存泄漏，二是为了下面的定时器判断
      timeout = null;
      result = func.apply(context, args);
      if (!timeout) context = args = null;
    };
    return function() {
      // 获得当前时间戳
      var now = _.now();
      // 首次进入前者肯定为 true
	  // 如果需要第一次不执行函数
	  // 就将上次时间戳设为当前的
      // 这样在接下来计算 remaining 的值时会大于0
      if (!previous && options.leading === false) previous = now;
      // 计算剩余时间
      var remaining = wait - (now - previous);
      context = this;
      args = arguments;
      // 如果当前调用已经大于上次调用时间 + wait
      // 或者用户手动调了时间
 	  // 如果设置了 trailing，只会进入这个条件
	  // 如果没有设置 leading，那么第一次会进入这个条件
	  // 还有一点，你可能会觉得开启了定时器那么应该不会进入这个 if 条件了
	  // 其实还是会进入的，因为定时器的延时
	  // 并不是准确的时间，很可能你设置了2秒
	  // 但是他需要2.2秒才触发，这时候就会进入这个条件
      if (remaining <= 0 || remaining > wait) {
        // 如果存在定时器就清理掉否则会调用二次回调
        if (timeout) {
          clearTimeout(timeout);
          timeout = null;
        }
        previous = now;
        result = func.apply(context, args);
        if (!timeout) context = args = null;
      } else if (!timeout && options.trailing !== false) {
        // 判断是否设置了定时器和 trailing
	    // 没有的话就开启一个定时器
        // 并且不能不能同时设置 leading 和 trailing
        timeout = setTimeout(later, remaining);
      }
      return result;
    };
  };
```

```js
// 函数防抖： 在事件被触发 n 秒后再执行回调，如果在这 n 秒内事件又被触发，则重新计时。

// 函数节流： 规定一个单位时间，在这个单位时间内，只能有一次触发事件的回调函数执行，如果在同一个单位时间内某事件被触发多次，只有一次能生效。

// 函数防抖的实现
function debounce(fn, wait) {
  var timer = null;

  return function() {
    var context = this,
      args = arguments;

    // 如果此时存在定时器的话，则取消之前的定时器重新记时
    if (timer) {
      clearTimeout(timer);
      timer = null;
    }

    // 设置定时器，使事件间隔指定事件后执行
    timer = setTimeout(() => {
      fn.apply(context, args);
    }, wait);
  };
}

// 函数节流的实现;
function throttle(fn, delay) {
  var preTime = Date.now();

  return function() {
    var context = this,
      args = arguments,
      nowTime = Date.now();

    // 如果两次时间间隔超过了指定时间，则执行函数。
    if (nowTime - preTime >= delay) {
      preTime = Date.now();
      return fn.apply(context, args);
    }
  };
}
```

  #### js中的深浅拷贝实现
```
浅拷贝指的是将一个对象的属性值复制到另一个对象，如果有的属性
的值为引用类型的话，那么会将这个引用的地址复制给对象，因此
两个对象会有同一个引用类型的引用。浅拷贝可以使用  
Object.assign 和展开运算符来实现。

深拷贝相对浅拷贝而言，如果遇到属性值为引用类型的时候，它新建一个
引用类型并将对应的值复制给它，因此对象获得的一个新的引用类型
而不是一个原有类型的引用。深拷贝对于一些对象可以使用 JSON 的
两个函数来实现，但是由于 JSON 的对象格式比 js 的对象格式更加严格，
所以如果属性值里边出现函数或者 Symbol 类型的值时，会转换失败。
```

```js
// 浅拷贝的实现;

function shallowCopy(object) {
  // 只拷贝对象
  if (!object || typeof object !== "object") return;

  // 根据 object 的类型判断是新建一个数组还是对象
  let newObject = Array.isArray(object) ? [] : {};

  // 遍历 object，并且判断是 object 的属性才拷贝
  for (let key in object) {
    if (object.hasOwnProperty(key)) {
      newObject[key] = object[key];
    }
  }

  return newObject;
}

// 深拷贝的实现;

function deepCopy(object) {
  if (!object || typeof object !== "object") return;

  let newObject = Array.isArray(object) ? [] : {};

  for (let key in object) {
    if (object.hasOwnProperty(key)) {
      newObject[key] =
        typeof object[key] === "object" ? deepCopy(object[key]) : object[key];
    }
  }

  return newObject;
}
```

```
浅拷贝：
Object.assign
或者展开运算符

深拷贝：
可以通过 JSON.parse(JSON.stringify(object)) 来解决
let a = {
    age: 1,
    jobs: {
        first: 'FE'
    }
}
let b = JSON.parse(JSON.stringify(a))
a.jobs.first = 'native'
console.log(b.jobs.first) // FE

该方法也是有局限性的：
会忽略 undefined
不能序列化函数
不能解决循环引用的对象
```

递归实现深拷贝
```
function deepClone(obj) {
    let objClone = Array.isArray(obj) ? [] : {};
    if (obj && typeof obj === "object") {
        for (key in obj) {
            if (obj.hasOwnProperty(key)) {
                if (obj[key] && typeof obj[key] === "object") {
                    objClone[key] = deepClone(obj[key]);
                } else {
                    objClone[key] = obj[key];
                }
            }
        }
    }
    return objClone;
}
let a = [1, 2, 3, 4];
let b = deepClone(a);
a[0] = 2;
console.log(b); //[ 1, 2, 3, 4 ]
```

JSON实现深拷贝
```
function deepClone(obj){
    let _obj = JSON.stringify(obj);
    let objClone = JSON.parse(_obj);
    return objClone
}    
let a=[0,1,[2,3],4];
let b=deepClone(a);
a[0]=1;
a[2][0]=1;
console.log(b);
```

#### JS中浅拷贝的手段有哪些
重要: 什么是拷贝？
- 首先来直观的感受一下什么是拷贝
```
let arr = [1, 2, 3];
let newArr = arr;
newArr[0] = 100;

console.log(arr);//[100, 2, 3]
```
```
这是直接赋值的情况，不涉及任何拷贝。当改变newArr的时候，
由于是同一个引用，arr指向的值也跟着改变。
```

现在进行浅拷贝:
```
let arr = [1, 2, 3];
let newArr = arr.slice();
newArr[0] = 100;

console.log(arr);//[1, 2, 3]
```

```
当修改newArr的时候，arr的值并不改变。什么原因?因为这里newArr是
arr浅拷贝后的结果，newArr和arr现在引用的已经不是同一块空间啦！

这就是浅拷贝！
```

但是这又会带来一个潜在的问题:
```
let arr = [1, 2, {val: 4}];
let newArr = arr.slice();
newArr[2].val = 1000;

console.log(arr);//[ 1, 2, { val: 1000 } ]
```

```
不是已经不是同一块空间的引用了吗？为什么改变了newArr改变了
第二个元素的val值，arr也跟着变了。
```

```
这就是浅拷贝的限制所在了。它只能拷贝一层对象。如果有对象的嵌套，
那么浅拷贝将无能为力。但幸运的是，深拷贝就是为了解决这个问题而生的，
它能解决无限极的对象嵌套问题，实现彻底的拷贝。当然，
这是我们下一篇的重点。 现在先让大家有一个基本的概念。
```
接下来，我们来研究一下JS中实现浅拷贝到底有多少种方式？
1. 手动实现
```
const shallowClone = (target) => {
  if (typeof target === 'object' && target !== null) {
    const cloneTarget = Array.isArray(target) ? []: {};
    for (let prop in target) {
      if (target.hasOwnProperty(prop)) {
          cloneTarget[prop] = target[prop];
      }
    }
    return cloneTarget;
  } else {
    return target;
  }
}
```
2. Object.assign
```
但是需要注意的是，Object.assgin() 拷贝的是对象的属性的引用，
而不是对象本身。

let obj = { name: 'sy', age: 18 };
const obj2 = Object.assign({}, obj, {name: 'sss'});
console.log(obj2);//{ name: 'sss', age: 18 }
```

3. concat浅拷贝数组
```
let arr = [1, 2, 3];
let newArr = arr.concat();
newArr[1] = 100;
console.log(arr);//[ 1, 2, 3 ]
```
4. slice浅拷贝
```
开头的例子
```

5. ...展开运算符
```
let arr = [1, 2, 3];
let newArr = [...arr];//跟arr.slice()是一样的效果
```

  #### js中的命名规则
```
（1）第一个字符必须是字母、下划线（_）或美元符号（$）
（2）余下的字符可以是下划线、美元符号或任何字母或数字字符

一般我们推荐使用驼峰法来对变量名进行命名，因为这样
可以与 ECMAScript 内置的函数和对象命名格式保持一致。
```

  #### 对原生Javascript了解程度
```
数据类型、运算、对象、Function、继承、闭包、作用域、原型链、
事件、RegExp、JSON、Ajax、DOM、BOM、内存泄漏、跨域、异步装载、
模板引擎、前端MVC、路由、模块化、Canvas、ECMAScript
```

  #### 渐进增强和优雅降级
```
渐进增强 ：针对低版本浏览器进行构建页面，保证最基本的功能，然后
再针对高级浏览器进行效果、交互等改进和追加功能达到更好的用户体验。

优雅降级 ：一开始就构建完整的功能，然后再针对低版本浏览器进行兼容
```

  #### JavaScript的组成
```
JavaScript 由以下三部分组成：
ECMAScript（核心）：JavaScript` 语言基础
DOM（文档对象模型）：规定了访问HTML和XML的接口
BOM（浏览器对象模型）：提供了浏览器窗口之间进行交互的对象和方法
```

  #### 如何编写高性能的JavaScript
```
1.使用位运算代替一些简单的四则运算。
2.避免使用过深的嵌套循环。
3.不要使用未定义的变量。
4.当需要多次访问数组长度时，可以用变量保存起来，
避免每次都会去进行属性查找。
```

```
遵循严格模式："use strict";
将js脚本放在页面底部，加快渲染页面
将js脚本将脚本成组打包，减少请求
使用非阻塞方式下载js脚本
尽量使用局部变量来保存全局变量
尽量减少使用闭包
使用 window 对象属性方法时，省略 window
尽量减少对象成员嵌套
缓存 DOM 节点的访问
通过避免使用 eval() 和 Function() 构造器
给 setTimeout() 和 setInterval() 传递函数而不是字符串作为参数
尽量使用直接量创建对象和数组
最小化重绘(repaint)和回流(reflow)
```

  #### js语句末尾分号是否可以省略
```
在 ECMAScript 规范中，语句结尾的分号并不是必需的。
但是我们一般最好不要省略分号，因为加上分号一方面有
利于我们代码的可维护性，另一方面也可以避免我们在
对代码进行压缩时出现错误。
```

  #### js延迟加载的方式有哪些
```
js 的加载、解析和执行会阻塞页面的渲染过程，因此我们希望 
js 脚本能够尽可能的延迟加载，提高页面的渲染速度。

我了解到的几种方式是：

第一种方式是我们一般采用的是将 js 脚本放在文档的底部，
来使 js 脚本尽可能的在最后来加载执行。

第二种方式是给 js 脚本添加 defer 属性，这个属性会让脚本
的加载与文档的解析同步解析，然后在文档解析完成后再执行
这个脚本文件，这样的话就能使页面的渲染不被阻塞。
多个设置了 defer 属性的脚本按规范来说最后是顺序执行的，
但是在一些浏览器中可能不是这样。

第三种方式是给 js 脚本添加 async 属性，这个属性会使
脚本异步加载，不会阻塞页面的解析过程，但是当脚本加载完成后
立即执行 js 脚本，这个时候如果文档没有解析完成的话同样
会阻塞。多个 async 属性的脚本的执行顺序是不可预测的，
一般不会按照代码的顺序依次执行。

第四种方式是动态创建 DOM 标签的方式，我们可以对文档的加载事件
进行监听，当文档加载完成后再动态的创建 script 标签来引入 js 脚本。
```

```
js 延迟加载，也就是等页面加载完成之后再加载 JavaScript 文件。
js 延迟加载有助于提高页面加载速度。
```

一般有以下几种方式：
```
defer 属性
async 属性
动态创建 DOM 方式
使用 setTimeout 延迟方法
让 JS 最后加载
```

```
设置<script>属性 defer="defer" （脚本将在页面完成解析时执行）
动态创建 script DOM：document.createElement('script');
XmlHttpRequest 脚本注入
延迟加载工具 LazyLoad
```

  #### 使用JS实现获取文件扩展名
```js
// String.lastIndexOf() 方法返回指定值（本例中的'.'）
在调用该方法的字符串中最后出现的位置，如果没找到则返回 -1。

// 对于 'filename' 和 '.hiddenfile' ，lastIndexOf 的返回值
分别为 0和 -1 无符号右移操作符(>>>) 将 -1 转换为 4294967295 ，
将 -2 转换为 4294967294 ，这个方法可以保证边缘情况时文件名不变。

// String.prototype.slice() 从上面计算的索引处提取文件的扩展名。
如果索引比文件名的长度大，结果为""。
function getFileExtension(filename) {
  return filename.slice(((filename.lastIndexOf(".") - 1) >>> 0) + 2);
}
```

  #### 对web标准、可用性、可访问性的理解
```
可用性（Usability）：产品是否容易上手，用户能否完成任务，
效率如何，以及这过程中用户的主观感受可好，是从用户的角度来
看产品的质量。可用性好意味着产品质量高，是企业的核心竞争力

可访问性（Accessibility）：Web内容对于残障用户的可阅读和可理解性

可维护性（Maintainability）：一般包含两个层次，
一是当系统出现问题时，快速定位并解决问题的成本，成本低则可维护性好。
二是代码是否容易被人理解，是否容易修改和增强功能。
```

  #### 对于JSON的了解
```
JSON 是一种基于文本的轻量级的数据交换格式。
它可以被任何的编程语言读取和作为数据格式来传递。

在项目开发中，我们使用 JSON 作为前后端数据交换的方式。
在前端我们通过将一个符合 JSON 格式的数据结构序列化为 
JSON 字符串，然后将它传递到后端，后端通过 JSON 格式的
字符串解析后生成对应的数据结构，以此来实现前后端数据的一个传递。

因为 JSON 的语法是基于 js 的，因此很容易将 JSON 和 js 
中的对象弄混，但是我们应该注意的是 JSON 和 js 中的对象
不是一回事，JSON 中对象格式更加严格，比如说在 JSON 中
属性值不能为函数，不能出现 NaN 这样的属性值等，
因此大多数的 js 对象是不符合 JSON 对象的格式的。

在 js 中提供了两个函数来实现 js 数据结构和 JSON 格式的
转换处理，一个是 JSON.stringify 函数，通过传入一个符合 
JSON 格式的数据结构，将其转换为一个 JSON 字符串。
如果传入的数据结构不符合 JSON 格式，那么在序列化的时候会
对这些值进行对应的特殊处理，使其符合规范。在前端向后端发送数据时，
我们可以调用这个函数将数据对象转化为 JSON 格式的字符串。

另一个函数 JSON.parse() 函数，这个函数用来将 JSON 格式的
字符串转换为一个 js 数据结构，如果传入的字符串不是标准的
JSON 格式的字符串的话，将会抛出错误。当我们从后端接收到 
JSON 格式的字符串时，我们可以通过这个方法来将其解析为一个 
js 数据结构，以此来进行数据的访问。
```

```
JSON 是一种数据交换格式，基于文本，优于轻量，用于交换数据。

JSON 可以表示数字、布尔值、字符串、null、数组（值的有序序列），
以及由这些值（或数组、对象）所组成的对象（字符串与值的映射）。

JSON 使用 JavaScript 语法，但是 JSON 格式仅仅是一个文本。文
本可以被任何编程语言读取及作为数据格式传递。
```

```
JSON(JavaScript Object Notation) 是一种轻量级的数据交换格式

它是基于JavaScript的一个子集。数据格式简单, 易于读写, 占用带宽小

JSON字符串转换为JSON对象:

var obj =eval('('+ str +')');
var obj = str.parseJSON();
var obj = JSON.parse(str);
JSON对象转换为JSON字符串：
var last=obj.toJSONString();
var last=JSON.stringify(obj);
```

  #### XML和JSON的区别
```
数据体积方面
JSON相对于XML来讲，数据的体积小，传递的速度更快些。

数据交互方面
JSON与JavaScript的交互更加方便，更容易解析处理，更好的数据交互

数据描述方面
JSON对数据的描述性比XML较差

传输速度方面
JSON的速度要远远快于XML
```

  #### JavaScript对象生命周期的理解
```
当创建一个对象时，JavaScript 会自动为该对象分配适当的内存
垃圾回收器定期扫描对象，并计算引用了该对象的其他对象的数量
如果被引用数量为 0，或惟一引用是循环的，那么该对象的内存即可回收
```

  #### requireJS的核心原理是什么？（如何动态加载的？如何避免多次加载的？如何缓存的？）
```
require.js 的核心原理是通过动态创建 script 脚本来异步引入模块，
然后对每个脚本的 load 事件进行监听，如果每个脚本都加载完成了，
再调用回调函数。
```

  #### 什么是“前端路由”？什么时候适合使用“前端路由”？“前端路由”有哪些优点和缺点
```
（1）什么是前端路由？
前端路由就是把不同路由对应不同的内容或页面的任务交给前端来做，
之前是通过服务端根据 url 的不同返回不同的页面实现的。

（2）什么时候使用前端路由？
在单页面应用，大部分页面结构不变，只改变部分内容的使用

（3）前端路由有什么优点和缺点？
优点：用户体验好，不需要每次都从服务器全部获取，快速展现给用户

缺点：单页面无法记住之前滚动的位置，无法在前进，后退的时候记住滚动的位置

前端路由一共有两种实现方式，一种是通过 hash 的方式，
一种是通过使用 pushState 的方式。
```

  #### Polyfill
```
Polyfill 指的是用于实现浏览器并不支持的原生 API 的代码。

比如说 querySelectorAll 是很多现代浏览器都支持的原生 Web API，
但是有些古老的浏览器并不支持，那么假设有人写了一段代码来实现这个
功能使这些浏览器也支持了这个功能，那么这就可以成为一个 Polyfill。

一个 shim 是一个库，有自己的 API，而不是单纯实现原生不支持的 API。
```

  #### rest参数
```
rest 参数（形式为...变量名），用于获取函数的多余参数。
```

  #### Proxy
```
Proxy 用于修改某些操作的默认行为，等同于在语言层面做出修改，
所以属于一种“元编程”，即对编程语言进行编程。

Proxy 可以理解成，在目标对象之前架设一层“拦截”，外界对该对象
的访问，都必须先通过这层拦截，因此提供了一种机制，可以对外界
的访问进行过滤和改写。Proxy 这个词的原意是代理，
用在这里表示由它来“代理”某些操作，可以译为“代理器”。
```

  #### gulp
```
gulp是前端开发过程中一种基于流的代码构建工具，是自动化项目的
构建利器；它不仅能对网站资源进行优化，而且在开发过程中很多
重复的任务能够使用正确的工具自动完成

Gulp的核心概念：流

流，简单来说就是建立在面向对象基础上的一种抽象的处理数据的工具。
在流中，定义了一些处理数据的基本操作，如读取数据，写入数据等，
程序员是对流进行所有操作的，而不用关心流的另一头数据的真正流向

gulp正是通过流和代码优于配置的策略来尽量简化任务编写的工作

Gulp的特点：
易于使用：通过代码优于配置的策略，gulp 让简单的任务简单，复杂的任务可管理
构建快速 利用 Node.js 流的威力，你可以快速构建项目并减少频繁的 IO 操作
易于学习 通过最少的 API，掌握 gulp 毫不费力，构建工作尽在掌握：如同一系列流管道
```

  #### web开发中会话跟踪的方法有哪些
```
cookie
session
url重写
隐藏input
ip地址
```

  #### 进程间通信的方式
```
1.管道通信
2.消息队列通信
3.信号量通信
4.信号通信
5.共享内存通信
6.套接字通信
```

  #### Reflect对象创建目的
```
1.将 Object 对象的一些明显属于语言内部的方法（比如 Object.defineProperty，放到 Reflect 对象上。
2.修改某些 Object 方法的返回结果，让其变得更合理。
3.让 Object 操作都变成函数行为。
4.Reflect 对象的方法与 Proxy 对象的方法一一对应，
只要是 Proxy 对象的方法，就能在 Reflect 对象上找到对应的方法。
这就让 Proxy 对象可以方便地调用对应的 Reflect 方法，
完成默认行为，作为修改行为的基础。也就是说，不管 Proxy 
怎么修改默认行为，你总可以在 Reflect 上获取默认行为。
```


### 实现

  #### Js动画与CSS动画区别及相应实现
```
CSS3 的动画的优点：
在性能上会稍微好一些，浏览器会对 CSS3 的动画做一些优化
代码相对简单

缺点:
在动画控制上不够灵活
兼容性不好

JavaScript 的动画正好弥补了这两个缺点，控制能力很强，
可以单帧的控制、变换，同时写得好完全可以兼容 IE6，并且功能强大。
对于一些复杂控制的动画，使用 javascript 会比较靠谱。
而在实现一些小的交互动效的时候，就多考虑考虑 CSS 吧
```

  #### js拖拽功能的实现,对页面某个节点的拖曳如何做？（使用原生JS）
```
一个元素的拖拽过程，我们可以分为三个步骤，
第一步是鼠标按下目标元素，

第二步是鼠标保持按下的状态移动鼠标，第三步是鼠标抬起，拖拽过程结束。

这三步分别对应了三个事件，mousedown 事件，mousemove 事件和 
mouseup 事件。只有在鼠标按下的状态移动鼠标我们才会执行拖拽事件，
因此我们需要在 mousedown 事件中设置一个状态来标识鼠标已经按下，
然后在 mouseup 事件中再取消这个状态。在 mousedown 事件中我们
首先应该判断，目标元素是否为拖拽元素，如果是拖拽元素，我们就
设置状态并且保存这个时候鼠标的位置。然后在 mousemove 事件中，
我们通过判断鼠标现在的位置和以前位置的相对移动，来确定拖拽元素
在移动中的坐标。

最后 mouseup 事件触发后，清除状态，结束拖拽事件。
```

```
首先是三个事件，分别是 mousedown，mousemove，mouseup
当鼠标点击按下的时候，需要一个 tag 标识此时已经按下，
可以执行 mousemove 里面的具体方法。
clientX，clientY 标识的是鼠标的坐标，分别标识横坐标和纵坐标，
并且我们用 offsetX 和 offsetY 来表示元素的元素的初始坐标，
移动的举例应该是：
鼠标移动时候的坐标-鼠标按下去时候的坐标。
也就是说定位信息为：
鼠标移动时候的坐标-鼠标按下去时候的坐标+元素初始情况下的 offetLeft.
```

```
给需要拖拽的节点绑定mousedown, mousemove, mouseup事件
mousedown事件触发后，开始拖拽
mousemove时，需要通过event.clientX和clientY获取拖拽位置，并实时更新位置
mouseup时，拖拽结束
需要注意浏览器边界的情况
```

  #### 使用js实现一个持续的动画效果
```
定时器思路：
var e = document.getElementById('e')
var flag = true;
var left = 0;
setInterval(() => {
    left == 0 ? flag = true : left == 100 ? flag = false : ''
    flag ? e.style.left = ` ${left++}px` : e.style.left = ` ${left--}px`
}, 1000 / 60)

requestAnimationFrame：
//兼容性处理
window.requestAnimFrame = (function(){
    return window.requestAnimationFrame       ||
           window.webkitRequestAnimationFrame ||
           window.mozRequestAnimationFrame    ||
           function(callback){
                window.setTimeout(callback, 1000 / 60);
           };
})();

var e = document.getElementById("e");
var flag = true;
var left = 0;

function render() {
    left == 0 ? flag = true : left == 100 ? flag = false : '';
    flag ? e.style.left = ` ${left++}px` :
        e.style.left = ` ${left--}px`;
}

(function animloop() {
    render();
    requestAnimFrame(animloop);
})();

使用css实现一个持续的动画效果：
animation:mymove 5s infinite;

@keyframes mymove {
    from {top:0px;}
    to {top:200px;}
}
animation-name 规定需要绑定到选择器的 keyframe名称。
animation-duration 规定完成动画所花费的时间，以秒或毫秒计。
animation-timing-function 规定动画的速度曲线。
animation-delay 规定在动画开始之前的延迟。
animation-iteration-count 规定动画应该播放的次数。
animation-direction 规定是否应该轮流反向播放动画
```

  #### 实现点击容器内的图标，图标边框变成border:1px solid red，点击空白处重置
```
const box = document.getElementById('box');
function isIcon(target) {
  return target.className.includes('icon');
}

box.onClick = function(e) {
  e.stopPropagation();
  const target = e.target;
  if (isIcon(target)) {
    target.style.border = '1px solid red';
  }
}
const doc = document;
doc.onclick = function(e) {
  const children = box.children;
  for(let i; i < children.length; i++) {
    if (isIcon(children[i])) {
      children[i].style.border = 'none';
    }
  }
}
```

  #### canvas上面随机布着一些黑块，请实现方法，计算canvas上有多少个黑块
```
想要知道有多少个图形，想到的就是先获取图片中的每一个像素点然后
判获取像素点的背景颜色（RGBA）。想要获得图片中的每一个像素点，
那就可以联想到使用h5的canvas。

如下：
canvas的getimagedata方法

书写html标签。
 <canvas id="canvas" height="200" width="350">对不你，你的浏览器不支持Canvas</canvas> 
 
js获取canvas对象
let ctxt = canvas.getContext('2d');

js创建image对象
let img = new Image;
img.src = './image.png'; //图片路径
img.onload = function(){}  //加载成功后的执行函数，之后的代码就写在其中

创建存储图片像素点的二维数组
let coordinates = [];
for(let i=0; i<200; i++){
       coordinates[i] = [];
}

获取像素点，也就是使用getimagedata方法。
ctxt.drawImage(img, 0, 0);  //将图片画如canvas
let data = ctxt.getImageData(0, 0, 350, 200).data;//读取整张图片的像素。

将像素存入二维数组
let x=0,y=0;  //二维数组的行和列， x：列  y：行
for(let i =0,len = data.length; i<len;i+=4){
        let red = data[i],//红色色深
        green = data[i+1],//绿色色深
        blue = data[i+2],//蓝色色深
        alpha = data[i+3];//透明度
        //把每个像素点，以二位数组的形式展开
        if(`${red} ${green} ${blue}` === '210 227 199'){
            coordinates[y][x] = 0;
        }else{
            coordinates[y][x] = 1;
        }
        x++;
        if(x >= 350){
            x = 0;
            y++;
        }
}

目前代码如下：
(function(){
        let ctxt = canvas.getContext('2d');
        let img = new Image;
        let coordinates = [];
        let h = 200,
            w = 350;
        for(let i=0; i<200; i++){
            coordinates[i] = [];
        }
        img.src = './image.png'; //图片路径
        img.onload = function(){
            ctxt.drawImage(img, 0, 0);
            let data = ctxt.getImageData(0, 0, 350, 200).data;//读取整张图片的像素。
            let x=0,y=0;
            for(let i =0,len = data.length; i<len;i+=4){
                    let red = data[i],//红色色深
                    green = data[i+1],//绿色色深
                    blue = data[i+2],//蓝色色深
                    alpha = data[i+3];//透明度
                    //把每个像素点，以二位数组的形式展开
                    if(`${red} ${green} ${blue}` === '210 227 199'){
                        coordinates[y][x] = 0;
                    }else{
                        coordinates[y][x] = 1;
                    }
                    x++;
                    if(x >= 350){
                        x = 0;
                        y++;
                    }
                }
                console.log(coordinates);
        }
    })();

构成类似如下二维数组：

0,0,0,0,0,0,0,0,0,0,0,0
0,0,1,1,1,0,0,0,0,0,0,0
0,1,1,1,1,0,0,0,0,0,0,0
0,1,1,1,0,0,0,1,1,1,1,0
0,0,0,0,0,0,1,1,1,0,0,0
0,0,0,0,0,0,1,1,1,0,0,0
0,0,0,0,0,0,0,0,0,0,0,0

那么我们就只需要知道二维数组中这种连续为1的块有多少个就知道了
图片中形状有多少个，并且块中有多少个1，那么这个块的面积就是1的个数。

递归回溯算法
//计算连续的面积和个数
const linkSum = (i,j,num)=>{
        //走过的路就置0
      coordinates[i][j] = 0;
      num++;
      //向上
      if((i+1 < h) && coordinates[i+1][j] == 1){
        num = linkSum(i+1 , j , num);
      }
      //向下
      if((j+1 < w) && coordinates[i][j+1] == 1){
        num = linkSum(i , j+1 , num);
      }
      //向左
      if((i-1 >= 0) && coordinates[i-1][j] == 1){
        num = linkSum(i-1 , j , num);
      }
      //向右
    if((j-1 >= 0) && coordinates[i][j-1] == 1){
        num = linkSum(i , j-1 , num);
    }

    return num;
}

使用算法，统计并计算出结果。
const getCountAndArea = () =>{
    let sum = [];
    let count = 0;
    for(let i = 0; i < h; i++)  //遍历二维数组
    {
      for(let j = 0; j < w; j++)
      {
       //连续1的个数
       if(coordinates[i][j] == 1)
       {
        let buf = 0;  //连续1的个数
        buf = linkSum(i,j,buf);
        count++;  //形状的总数
        sum.push({
            index: count,   //第几个形状
            area: buf         //形状的面积
        });
       }
      }
    }
    return {
        count,
        sum
    };
}

最后的代码
(function(){
        let ctxt = canvas.getContext('2d');
        let img = new Image;
        let coordinates = [];
        let h = 200,
            w = 350;
        for(let i=0; i<200; i++){
            coordinates[i] = [];
        }
        img.src = './image.png'; //图片路径
        img.onload = function(){
            ctxt.drawImage(img, 0, 0);
            let data = ctxt.getImageData(0, 0, 350, 200).data;//读取整张图片的像素。
            let x=0,y=0;
            for(let i =0,len = data.length; i<len;i+=4){
                    let red = data[i],//红色色深
                    green = data[i+1],//绿色色深
                    blue = data[i+2],//蓝色色深
                    alpha = data[i+3];//透明度
                    //把每个像素点，以二位数组的形式展开
                    if(`${red} ${green} ${blue}` === '210 227 199'){
                        coordinates[y][x] = 0;
                    }else{
                        coordinates[y][x] = 1;
                    }
                    x++;
                    if(x >= 350){
                        x = 0;
                        y++;
                    }
                }
                // console.log(coordinates);
                let rst = getCountAndArea();
                // console.log(rst);
                console.log('个数： ' + rst.count);
                for(let i=0; i<rst.sum.length; i++){
                    console.log(`第${i+1}个面积为: ${rst.sum[i].area} px`);
                }
        }
    
        const getCountAndArea = () =>{
            let sum = [];
            let count = 0;
            for(let i = 0; i < h; i++)
            {
              for(let j = 0; j < w; j++)
              {
               //连续1的个数
               if(coordinates[i][j] == 1)
               {
                let buf = 0;
                buf = linkSum(i,j,buf);
                count++;
                sum.push({
                    index: count,
                    area: buf
                });
               }
              }
            }
            return {
                count,
                sum
            };
        }

        //计算连续的面积和个数
        const linkSum = (i,j,num)=>{
            //走过的路就置0
          coordinates[i][j] = 0;
          num++;
          //向上
          if((i+1 < h) && coordinates[i+1][j] == 1){
            num = linkSum(i+1 , j , num);
          }
          //向下
          if((j+1 < w) && coordinates[i][j+1] == 1){
            num = linkSum(i , j+1 , num);
          }
          //向左
          if((i-1 >= 0) && coordinates[i-1][j] == 1){
            num = linkSum(i-1 , j , num);
          }
          //向右
        if((j-1 >= 0) && coordinates[i][j-1] == 1){
            num = linkSum(i , j-1 , num);
        }

        return num;
        }
    })();
```

  #### 怎么做JS代码Error统计
```
error 统计使用浏览器的 window.error 事件。
```

  #### 完成一个Dialog组件，说说你设计的思路？它应该有什么功能
```
该组件需要提供hook指定渲染位置，默认渲染在body下面。

然后改组件可以指定外层样式，如宽度等

组件外层还需要一层mask来遮住底层内容，
点击mask可以执行传进来的onCancel函数关闭Dialog。

另外组件是可控的，需要外层传入visible表示是否可见。

然后Dialog可能需要自定义头head和底部footer，默认有头部和底部，
底部有一个确认按钮和取消按钮，确认按钮会执行外部传进来的onOk事件，
然后取消按钮会执行外部传进来的onCancel事件。

当组件的visible为true时候，设置body的overflow为hidden，
隐藏body的滚动条，反之显示滚动条。

组件高度可能大于页面高度，组件内部需要滚动条。

只有组件的visible有变化且为ture时候，才重渲染组件内的所有内容
```

  #### js中倒计时的纠偏实现
```
在前端实现中我们一般通过 setTimeout 和 setInterval 方法来
实现一个倒计时效果。但是使用这些方法会存在时间偏差的问题，
这是由于 js 的程序执行机制造成的，setTimeout 和 setInterval 
的作用是隔一段时间将回调事件加入到事件队列中，因此事件并不是
立即执行的，它会等到当前执行栈为空的时候再取出事件执行，
因此事件等待执行的时间就是造成误差的原因。

一般解决倒计时中的误差的有这样两种办法：
（1）第一种是通过前端定时向服务器发送请求获取最新的时间差，
以此来校准倒计时时间。

（2）第二种方法是前端根据偏差时间来自动调整间隔时间的方式来
实现的。这一种方式首先是以 setTimeout 递归的方式来实现倒计时，
然后通过一个变量来记录已经倒计时的秒数。每一次函数调用的时候，
首先将变量加一，然后根据这个变量和每次的间隔时间，我们就可以
计算出此时无偏差时应该显示的时间。然后将当前的真实时间与这个
时间相减，这样我们就可以得到时间的偏差大小，因此我们在设置
下一个定时器的间隔大小的时候，我们就从间隔时间中减去这个
偏差大小，以此来实现由于程序执行所造成的时间误差的纠正。
```

  #### 函数柯里化的实现
```js
// 函数柯里化指的是一种将使用多个参数的一个函数转换成
一系列使用一个参数的函数的技术。

function curry(fn, args) {
  // 获取函数需要的参数长度
  let length = fn.length;

  args = args || [];

  return function() {
    let subArgs = args.slice(0);

    // 拼接得到现有的所有参数
    for (let i = 0; i < arguments.length; i++) {
      subArgs.push(arguments[i]);
    }

    // 判断参数的长度是否已经满足函数所需参数的长度
    if (subArgs.length >= length) {
      // 如果满足，执行函数
      return fn.apply(this, subArgs);
    } else {
      // 如果不满足，递归返回科里化的函数，等待参数的传入
      return curry.call(this, fn, subArgs);
    }
  };
}

// es6 实现
function curry(fn, ...args) {
  return fn.length <= args.length ? fn(...args) : curry.bind(null, fn, ...args);
}
```

  #### EventEmitter实现
```js
class EventEmitter {
  constructor() {
    this.events = {};
  }

  on(event, callback) {
    let callbacks = this.events[event] || [];
    callbacks.push(callback);
    this.events[event] = callbacks;

    return this;
  }

  off(event, callback) {
    let callbacks = this.events[event];
    this.events[event] = callbacks && callbacks.filter(fn => fn !== callback);

    return this;
  }

  emit(event, ...args) {
    let callbacks = this.events[event];
    callbacks.forEach(fn => {
      fn(...args);
    });

    return this;
  }

  once(event, callback) {
    let wrapFun = function(...args) {
      callback(...args);

      this.off(event, wrapFun);
    };
    this.on(event, wrapFun);

    return this;
  }
}
```

  #### 如何查找一篇英文文章中出现频率最高的单词
```js
function findMostWord(article) {
  // 合法性判断
  if (!article) return;

  // 参数处理
  article = article.trim().toLowerCase();

  let wordList = article.match(/[a-z]+/g),
    visited = [],
    maxNum = 0,
    maxWord = "";

  article = " " + wordList.join("  ") + " ";

  // 遍历判断单词出现次数
  wordList.forEach(function(item) {
    if (visited.indexOf(item) < 0) {

      // 加入 visited 
      visited.push(item);

      let word = new RegExp(" " + item + " ", "g"),
        num = article.match(word).length;

      if (num > maxNum) {
        maxNum = num;
        maxWord = item;
      }
    }
  });

  return maxWord + "  " + maxNum;
}
```

  #### 实现Storage，使得该对象为单例，并对localStorage进行封装设置值setItem(key,value)和getItem(key)
```
var instance = null;
class Storage {
  static getInstance() {
    if (!instance) {
      instance = new Storage();
    }
    return instance;
  }
  setItem = (key, value) => localStorage.setItem(key, value),
  getItem = key => localStorage.getItem(key)
}
```

  #### 获取页面所有的checkbox
```
 var domList = document.getElementsByTagName(‘input’)
 var checkBoxList = [];
 var len = domList.length;　　//缓存到局部变量
 while (len--) {　　//使用while的效率会比for循环更高
 　　if (domList[len].type == ‘checkbox’) {
     　　checkBoxList.push(domList[len]);
 　　}
 }

```

```
var resultArr= [];
var input = document.querySelectorAll('input');
for( var i = 0; i < input.length; i++ ) {
    if( input[i].type == 'checkbox' ) {
        resultArr.push( input[i] );
    }
}
//resultArr即中获取到了页面中的所有checkbox
```



### 宏任务和微任务

  #### requestAnimationFrame
```
随着前端的发展，css已经能够实现非常多的动画特效，但是仍然
存在css无法完成的动画任务（比如页面滚动），通常的解决方案
都是使用js中的setInterval来设置定时器来实现动画特效，
比如下面的一个基本的动画循环。
(function() {
  function updateAnimations() {
    doAnimation1();
    doAnimation2();
  }
  setInterval(updateAnimations, 100);
})();
该代码实现的功能是每隔100毫秒执行函数操作来达到动画效果，
然而，使用计时器不可靠

由于JavaScript是单线程的，所以定时器的实现是在当前任务队列
完成后再执行定时器的回调的，假如当前队列任务执行时间大于
定时器设置的延迟时间，那么定时器就不是那么可靠了，如下所示：
let startTime = new Date().getTime();
setTimeout(()=>{
  let endTime = new Date().getTime();
  console.log(endTime - startTime);
},50)

for(let i=0;i<20000;i++) {
  console.log(1);
}
设置了50毫秒后执行，实际执行延迟时间远大于这个数值，
这就会导致动画效果并不会达到想要的效果。

动画是由浏览器按照一定的频率一帧一帧的绘制的，由css实现的
动画的优势就是浏览器知道动画的开始及每一帧的循环间隔，
能够在恰当的时间刷新UI，给用户一种流畅的体验，而setInterval
或setTimeout实现的JavaScript动画就没有这么可靠了，因为浏览器
压根就无法保证每一帧渲染的时间间隔，一般情况下，每秒平均刷新次数
能够达到60帧，就能够给人流畅的体验，即每过 1000/60 毫秒渲染
新一帧即可，但从上面的例子知，这一点单靠定时器是无法保证的。

为此，requestAnimationFrame应运而生，其作用就是让浏览器流畅
的执行动画效果。可以将其理解为专门用来实现动画效果的api，
通过这个api,可以告诉浏览器某个JavaScript代码要执行动画，
浏览器收到通知后，则会运行这些代码的时候进行优化，
实现流畅的效果，而不再需要开发人员烦心刷新频率的问题了。

使用方法如下：
function animationWidth() {
  var div = document.getElementById('box');
  div.style.width = parseInt(div.style.width) + 1 + 'px';

  if(parseInt(div.style.width) < 200) {
    requestAnimationFrame(animationWidth)
  }
}
requestAnimationFrame(animationWidth);

requestAnimationFrame接受一个动画执行函数作为参数，这个函数
的作用是仅执行一帧动画的渲染，并根据条件判断是否结束，如果
动画没有结束，则继续调用requestAnimationFrame并将自身
作为参数传入。从示例来看，得到了效果平滑流畅的动画，
这样就巧妙地避开了每一帧动画渲染的时间间隔问题。

在高级浏览器中，开发人员不用去操心每一帧动画渲染的时间间隔
问题，而针对低版本浏览器，则需要使用setTimeout来模拟
requestAnimationFrame,且针对不同浏览器对requestAnimationFrame
的实现，这个api的名字也略有差异，针对低版本浏览器的模拟
requestAnimationFrame的写法如下(来自张鑫旭大神的博客)：
(function() {
    var lastTime = 0;
    var vendors = ['webkit', 'moz'];
    for(var x = 0; x < vendors.length && !window.requestAnimationFrame; ++x) {
        window.requestAnimationFrame = window[vendors[x] + 'RequestAnimationFrame'];
        window.cancelAnimationFrame = window[vendors[x] + 'CancelAnimationFrame'] ||    // Webkit中此取消方法的名字变了
                                      window[vendors[x] + 'CancelRequestAnimationFrame'];
    }

    if (!window.requestAnimationFrame) {
        window.requestAnimationFrame = function(callback, element) {
            var currTime = new Date().getTime();
            var timeToCall = Math.max(0, 16.7 - (currTime - lastTime));
            var id = window.setTimeout(function() {
                callback(currTime + timeToCall);
            }, timeToCall);
            lastTime = currTime + timeToCall;
            return id;
        };
    }
    if (!window.cancelAnimationFrame) {
        window.cancelAnimationFrame = function(id) {
            clearTimeout(id);
        };
    }
}());
具体含义不做解释，如果遇到低版本浏览器的动画需求，你只需要把
这段代码丢进去定义一个低配版requestAnimationFrame方法即可
```

说一下requestAnimationFrame
- 简介：
  - 显示器都有自己固有的刷新频率(60HZ或者75HZ)，也就是说每秒最多重绘60次或者75次。而requestAnimationFrame的基本思想就是与这个刷新频率保持同步，利用这个刷新频率进行重绘。

- 特点：
  - 使用这个API时，一旦页面不处于浏览器的当前标签，就会自动停止刷新，这样就节省了CPU、GPU、电力。
  - 由于它时在主线程上完成的，所以若是主线程非常忙时它的动画也会收到影响
  - 它使用一个回调函数作为参数，这个回调函数会在浏览器重绘之前调用。

- 使用：
  - 正常使用：
```
const requestID = window.requestAnimationFrame(callback);
```
  - 兼容版本：
```
// 给 window 下挂载一个兼容版本的 requestAniFrame
window.requestAniFrame = (function () {
  return  window.requestAnimationFrame || 
    window.webkitRequestAnimationFrame || 
    window.mozRequestAnimationFrame    || 
    window.oRequestAnimationFrame      || 
    window.msRequestAnimationFrame     || 
    function( callback ){
      window.setTimeout(callback, 1000 / 60);
    };
})();
```

#### requestAnimationFrame对比setTimeout
- **屏幕刷新频率：**屏幕每秒出现图像的次数。普通笔记本为60Hz
- **动画原理：**计算机每16.7ms刷新一次，由于人眼的视觉停留，所以看起来是流畅的移动。
- **setTimeout：**通过设定间隔时间来不断改变图像位置，达到动画效果。但是容易出现卡顿抖动的现象；原因是：

- 1.settimeout任务被放入异步队列，只有当主线程任务执行完后才会执行队列中的任务，因此实际执行时间总是比设定时间要晚；
- 2.settimeout的固定时间间隔不一定与屏幕刷新时间相同，会引起丢帧。
```
**requestAnimationFrame：**优势：由系统决定回调函数的执行时机。
60Hz的刷新频率，那么每次刷新的间隔中会执行一次回调函数，不会引起
丢帧，不会卡顿。且由于一旦页面不处于浏览器的当前标签，
就会自动停止刷新，这样就节省了CPU、GPU、电力。
```

#### setTimeout、Promise、Async/Await的区别
- 首先，我们先来了解一下基本概念：
  - js EventLoop 事件循环机制:
  - JavaScript的事件分两种，宏任务(macro-task)和微任务(micro-task)
- 宏任务：包括整体代码script，setTimeout，setInterval
- 微任务：Promise.then(非new Promise)，process.nextTick(node中)
- 事件的执行顺序，是先执行宏任务，然后执行微任务，这个是基础，任务可以有同步任务和异步任务，同步的进入主线程，异步的进入Event Table并注册函数，异步事件完成后，会将回调函数放入Event Queue中(宏任务和微任务是不同的Event Queue)，同步任务执行完成后，会从Event Queue中读取事件放入主线程执行，回调函数中可能还会包含不同的任务，因此会循环执行上述操作。
- 注意： setTimeOut并不是直接的把你的回掉函数放进上述的异步队列中去，而是在定时器的时间到了之后，把回掉函数放到执行异步队列中去。如果此时这个队列已经有很多任务了，那就排在他们的后面。这也就解释了为什么setTimeOut为什么不能精准的执行的问题了。
- setTimeout执行需要满足两个条件：
  - 主进程必须是空闲的状态，如果到时间了，主进程不空闲也不会执行你的回掉函数
  - 这个回掉函数需要等到插入异步队列时前面的异步函数都执行完了，才会执行
- 上面是比较官方的解释，说一下自己的理解吧：
  - 了解了什么是宏任务和微任务，就好理解多了，首先执行 宏任务 => 微任务的Event Queue => 宏任务的Event Queue
- promise、async/await
  - 首先，new Promise是同步的任务，会被放到主进程中去立即执行。而.then()函数是异步任务会放到异步队列中去，那什么时候放到异步队列中去呢？当你的promise状态结束的时候，就会立即放进异步队列中去了。
  - 带async关键字的函数会返回一个promise对象，如果里面没有await，执行起来等同于普通函数；如果没有await，async函数并没有很厉害是不是
  - await 关键字要在 async 关键字函数的内部，await 写在外面会报错；await如同他的语意，就是在等待，等待右侧的表达式完成。此时的await会让出线程，阻塞async内后续的代码，先去执行async外的代码。等外面的同步代码执行完毕，才会执行里面的后续代码。就算await的不是promise对象，是一个同步函数，也会等这样操作

根据图片显示我们来整理一下流程：
- 执行console.log('script start')，输出script start；
- 执行setTimeout，是一个异步动作，放入宏任务异步队列中；
- 执行async1()，输出async1 start，继续向下执行；
- 执行async2()，输出async2，并返回了一个promise对象，await让出了线程，把返回的promise加入了微任务异步队列，所以async1()下面的代码也要等待上面完成后继续执行;
- 执行 new Promise，输出promise1，然后将resolve放入微任务异步队列；
- 执行console.log('script end')，输出script end；
- 到此同步的代码就都执行完成了，然后去微任务异步队列里去获取任务
- 接下来执行resolve（async2返回的promise返回的），输出了async1 end。
- 然后执行resolve（new Promise的），输出了promise2
- 最后执行setTimeout，输出了settimeout

  #### 为什么使用setTimeout实现setInterval？怎么模拟
```
setInterval 的作用是每隔一段指定时间执行一个函数，但是这个执行
不是真的到了时间立即执行，它真正的作用是每隔一段时间将事件加入
事件队列中去，只有当当前的执行栈为空的时候，才能去从事件队列中
取出事件执行。所以可能会出现这样的情况，就是当前执行栈执行的
时间很长，导致事件队列里边积累多个定时器加入的事件，当执行栈结束
的时候，这些事件会依次执行，因此就不能到间隔一段时间执行的效果。

针对 setInterval 的这个缺点，我们可以使用 setTimeout 递归
调用来模拟 setInterval，这样我们就确保了只有一个事件结束了，
我们才会触发下一个定时器事件，这样解决了 setInterval 的问题。
```

```js
// 思路是使用递归函数，不断地去执行 setTimeout 从而达到 setInterval 的效果

function mySetInterval(fn, timeout) {
  // 控制器，控制定时器是否继续执行
  var timer = {
    flag: true
  };

  // 设置递归函数，模拟定时器执行。
  function interval() {
    if (timer.flag) {
      fn();
      setTimeout(interval, timeout);
    }
  }

  // 启动定时器
  setTimeout(interval, timeout);

  // 返回控制器
  return timer;
}
```

#### setTimeout(fn,0)多久才执行，Event Loop
- setTimeout 按照顺序放到队列里面，然后等待函数调用栈清空之后才开始执行，而这些操作进入队列的顺序，则由设定的延迟时间来决定

#### setInterval存在哪些问题
- JavaScript中使用 setInterval 开启轮询。定时器代码可能在代码再次被添加到队列之前还没有完成执行，结果导致定时器代码连续运行好几次，而之间没有任何停顿。而javascript引擎对这个问题的解决是：当使用setInterval()时，仅当没有该定时器的任何其他代码实例时，才将定时器代码添加到队列中。这确保了定时器代码加入到队列中的最小时间间隔为指定间隔。

但是，这样会导致两个问题：
- 某些间隔被跳过；
- 多个定时器的代码执行之间的间隔可能比预期的小

#### 链式调用setTimeout对比setInterval
- 在上一题中也说到了setInterval本身是会存在一些问题的。而使用链式调用setTimeout这种方式会比它好一些：
```
setTimeout(function fn(){
    console.log('我是setTimeout');
    setTimeout(fn, 1000);
},1000);
```

- 这个模式链式调用了setTimeout()，每次函数执行的时候都会创建一个新的定时器。第二个setTimeout()调用当前执行的函数，并为其设置另外一个定时器。这样做的好处是：
  - 在前一个定时器代码执行完之前，不会向队列插入新的定时器代码，确保不会有任何缺失的间隔。
  - 而且，它可以保证在下一次定时器代码执行之前，至少要等待指定的间隔，避免了连续的运行。

  #### event loop
```
首先，js是单线程的，主要的任务是处理用户的交互，而用户的交互
无非就是响应DOM的增删改，使用事件队列的形式，一次事件循环
只处理一个事件响应，使得脚本执行相对连续，所以有了事件队列，
用来储存待执行的事件，那么事件队列的事件从哪里被push进来的呢。
那就是另外一个线程叫事件触发线程做的事情了，他的作用主要是
在定时触发器线程、异步HTTP请求线程满足特定条件下的回调函数
push到事件队列中，等待js引擎空闲的时候去执行，当然js引擎
执行过程中有优先级之分，首先js引擎在一次事件循环中，会先
执行js线程的主任务，然后会去查找是否有微任务microtask
（promise），如果有那就优先执行微任务，如果没有，在去
查找宏任务macrotask（setTimeout、setInterval）进行执行

众所周知 JS 是门非阻塞单线程语言，因为在最初 JS 就是为了
和浏览器交互而诞生的。如果 JS 是门多线程的语言话，我们在
多个线程中处理 DOM 就可能会发生问题（一个线程中新加节点，
另一个线程中删除节点）

JS 在执行的过程中会产生执行环境，这些执行环境会被顺序的
加入到执行栈中。如果遇到异步的代码，会被挂起并加入到 Task
（有多种 task） 队列中。一旦执行栈为空，Event Loop 就会从
Task 队列中拿出需要执行的代码并放入执行栈中执行，
所以本质上来说 JS 中的异步还是同步行为

console.log('script start');
setTimeout(function() {
  console.log('setTimeout');
}, 0);
console.log('script end');

不同的任务源会被分配到不同的 Task 队列中，任务源可以分为 
微任务（microtask） 和 宏任务（macrotask）。
在 ES6 规范中，microtask 称为 jobs，macrotask 称为 task

console.log('script start');
setTimeout(function() {
  console.log('setTimeout');
}, 0);
new Promise((resolve) => {
    console.log('Promise')
    resolve()
}).then(function() {
  console.log('promise1');
}).then(function() {
  console.log('promise2');
});
console.log('script end');
// script start => Promise => script end => promise1 => promise2 => setTimeout
以上代码虽然 setTimeout 写在 Promise 之前，
但是因为 Promise 属于微任务而 setTimeout 属于宏任务

微任务
process.nextTick
promise
Object.observe
MutationObserver

宏任务
script
setTimeout
setInterval
setImmediate
I/O
UI rendering

宏任务中包括了 script ，浏览器会先执行一个宏任务，
接下来有异步代码的话就先执行微任务

所以正确的一次 Event loop 顺序是这样的:
执行同步代码，这属于宏任务
执行栈为空，查询是否有微任务需要执行
执行所有微任务
必要的话渲染 UI
然后开始下一轮 Event loop，执行宏任务中的异步代码

通过上述的 Event loop 顺序可知，如果宏任务中的异步代码有
大量的计算并且需要操作 DOM 的话，为了更快的响应界面响应，
我们可以把操作 DOM 放入微任务中
```

  #### 浏览器宏微任务
```
   宏任务                     微任务
input/output               MutationObserver
setTimeout                 Promise.then catch finally  
setInterval
requestAnimationFrame
```
上述就是在浏览器中主要的宏任务和微任务。
```
当一个js文件执行时，会先执行同步代码，此时所有的
异步代码进入到事件表里边，在事件表中分为宏任务
和微任务。当同步代码执行完毕，会先执行事件表
里边的微任务，等微任务全部执行完毕，执行下一个
宏任务，每一个宏任务执行完毕都会先判断一下
有没有微任务，如果有执行全部微任务，
如果没有，执行下一个宏任务。
```
下面我们就对浏览器中的宏微任务来看具体的例子。
```
function change( ) {
console.log( '1')
Promise.resolve( ).then(( )=> console. log('2'))
setTimeout(( )=> console.log( '3'))
requestAnimationFrame(( )=> console.log( '4'))
div . setAttribute( ' data- index'，
100' )
}
new Mutat ionObserver(( )=> {
console.log( '5')
}). observe(div, {
attributes: true
})
div . addEventL istener( 'click', change )
```
代码中既有微任务，又有宏任务，下面我们来看一下它的执行顺序：
```
当点击div执行change函数后
1.先执行console.log()同步代码
2.promise主体运行(注：promise主体是同步代码),then加入微任务队列
3.setTimeout加入宏任务队列
4.requestAnimationFrame加入宏任务队列
5.给div设置data-index属性。触发MutationObserver,加入微任务队列
6.执行微任务队列中then,MutationObserver
7.执行宏任务requestAnimationFrame
8.UI render
9.执行setTimeout

//12543
```

```
虽然setTimeout要先requestAnimation加入宏任务队列，
但是js规定requestAnimationFrame要在UI render之前运行。
因为给div设置data-index属性之后，会触发页面的
重新渲染(UI render)，所以requestAdnimaction就插队了。

再来看一个例子：
console.log('1');
setTimeout(function() {  //set1
    console.log('2');
    new Promise(function(resolve) {  //pro2
        console.log('4');
        resolve();
    }).then(function() {  //th2
        console.log('5')
    })
})
new Promise(function(resolve) {  //pro1
    console.log('7');
    resolve();
}).then(function() {  //th1
    console.log('8')
})
setTimeout(function() {  ///set2
    console.log('9');
    new Promise(function(resolve) {  //pro3
        console.log('11');
        resolve();
    }).then(function() {  //th3
        console.log('12')
    })
})
```
上述代码的执行顺序为：
```
1.console.log(1) 同步代码执行打印1
2.setTimeout(set1)入宏任务队列
3.promise主体(pro1)执行,打印7，then(th1)加入微任务队列
4.setTimeout(set2)加入宏任务队列
5.执行当前微任务队列中的then(th1)，打印8
6.执行set1，打印2，其中的promise主体也执行打印4，
  产生微任务then(th2)加入微任务
8.执行微任务then(th2),打印5
9.执行宏任务set2，打印9，promise主体也运行打印11,then(th3)加入微任务
10.微任务then(th3)执行打印12

1 7 8 2 4 5 9 11 12
```


### 对比

  #### addEventListener()和attachEvent()的区别
```
addEventListener()是符合W3C规范的标准方法; 
attachEvent()是IE低版本的非标准方法

addEventListener()支持事件冒泡和事件捕获; 
而attachEvent()只支持事件冒泡

addEventListener()的第一个参数中,事件类型不需要添加on; attachEvent()需要添加'on'

如果为同一个元素绑定多个事件, addEventListener()会按照事件绑定
的顺序依次执行, attachEvent()会按照事件绑定的顺序倒序执行
```

  #### attribute和property的区别是什么
```
attribute是dom元素在文档中作为html标签拥有的属性；

property就是dom元素在js中作为对象拥有的属性。

对于html的标准属性来说，attribute和property是同步的，
是会自动更新的

但是对于自定义的属性来说，他们是不同步的
```

  #### caller和callee的区别
```
caller：
caller返回一个函数的引用，这个函数调用了当前的函数。

使用这个属性要注意：
这个属性只有当函数在执行时才有用
如果在javascript程序中，函数是由顶层调用的，则返回null

functionName.caller: functionName是当前正在执行的函数。

function a() {
  console.log(a.caller)
}

callee：
callee放回正在执行的函数本身的引用，它是arguments的一个属性

使用callee时要注意:：
这个属性只有在函数执行时才有效

它有一个length属性，可以用来获得形参的个数，因此可以用来
比较形参和实参个数是否一致，即比较arguments.length是否
等于arguments.callee.length

它可以用来递归匿名函数。

function a() {
  console.log(arguments.callee)
}
```

  #### Javascript中callee和caller的作用
```
caller是返回一个对函数的引用，该函数调用了当前函数；
callee是返回正在被执行的function函数，
也就是所指定的function对象的正文

那么问题来了？如果一对兔子每月生一对兔子；一对新生兔，
从第二个月起就开始生兔子；假定每对兔子都是一雌一雄，
试问一对兔子，第n个月能繁殖成多少对兔子？（使用callee完成）

var result=[];
  function fn(n){  //典型的斐波那契数列
     if(n==1){
          return 1;
     }else if(n==2){
             return 1;
     }else{
          if(result[n]){
                  return result[n];
         }else{
                 //argument.callee()表示fn()
                 result[n]=arguments.callee(n-1)+arguments.callee(n-2);
                 return result[n];
         }
    }
 }
```

  #### documen.write和innerHTML的区别
```
document.write 的内容会代替整个文档内容，会重写整个页面。

innerHTML 的内容只是替代指定元素的内容，
只会重写页面中的部分内容。
```

  #### escape,encodeURI,encodeURIComponent区别
```
encodeURI 是对整个 URI 进行转义，将 URI 中的非法字符转换为
合法字符，所以对于一些在 URI 中有特殊意义的字符不会进行转义。

encodeURIComponent 是对 URI 的组成部分进行转义，
所以一些特殊字符也会得到转义。

escape 和 encodeURI 的作用相同，不过它们对于 unicode 
编码为 0xff 之外字符的时候会有区别，escape 是直接在字符的
unicode 编码前加上 %u，而 encodeURI 首先会将字符转换为
UTF-8 的格式，再在每个字节前加上 %。
```

```
escape 和 encodeURI 都属于 Percent-encoding，基本功能
都是把 URI 非法字符转化成合法字符，转化后形式类似「%*」。
它们的根本区别在于，escape 在处理 0xff 之外字符的时候，
是直接使用字符的 unicode 在前面加上一个「%u」，而 encode URI 
则是先进行 UTF-8，再在 UTF-8 的每个字节码前加上一个「%」；
在处理 0xff 以内字符时，编码方式是一样的（都是「%XX」，
XX 为字符的 16 进制 unicode，同时也是字符的 UTF-8），
只是范围（即哪些字符编码哪些字符不编码）不一样。
```

  #### innerHTML与outerHTML的区别
```
对于这样一个 HTML 元素：<div>content<br/></div>。

innerHTML：内部 HTML，content<br/>；
outerHTML：外部 HTML，<div>content<br/></div>；
innerText：内部文本，content ；
outerText：内部文本，content ；
```

  #### js代码中的"use strict";是什么意思?使用它区别是什么
```
use strict 指的是严格运行模式，在这种模式对 js 的使用添加了
一些限制。比如说禁止 this 指向全局对象，还有禁止使用 with 
语句等。设立严格模式的目的，主要是为了消除代码使用中的一些
不安全的使用方式，也是为了消除 js 语法本身的一些不合理的地方，
以此来减少一些运行时的怪异的行为。同时使用严格运行模式
也能够提高编译的效率，从而提高代码的运行速度。
我认为严格模式代表了 js 一种更合理、更安全、更严谨的发展方向。
```

```
use strict 是一种 ECMAscript5 添加的（严格）运行模式，
这种模式使得 Javascript 在更严格的条件下运行。

设立"严格模式"的目的，主要有以下几个：
消除 Javascript 语法的一些不合理、不严谨之处，减少一些怪异行为;
消除代码运行的一些不安全之处，保证代码运行的安全；
提高编译器效率，增加运行速度；
为未来新版本的 Javascript 做好铺垫。

区别：
1.禁止使用 with 语句。
2.禁止 this 关键字指向全局对象。
3.对象不能有重名的属性。
```

  #### mouseover和mouseenter区别
```
当鼠标移动到元素上时就会触发 mouseenter 事件，类似 
mouseover，它们两者之间的差别是 mouseenter 不会冒泡。

由于 mouseenter 不支持事件冒泡，导致在一个元素的子元素上
进入或离开的时候会触发其 mouseover 和 mouseout 事件，
但是却不会触发 mouseenter 和 mouseleave 事件。
```

  #### offsetWidth/offsetHeight,clientWidth/clientHeight与scrollWidth/scrollHeight的区别
```
clientWidth/clientHeight 返回的是元素的内部宽度，它的值
只包含 content + padding，如果有滚动条，不包含滚动条。
clientTop 返回的是上边框的宽度。
clientLeft 返回的左边框的宽度。

offsetWidth/offsetHeight 返回的是元素的布局宽度，
它的值包含 content + padding + border 包含了滚动条。
offsetTop 返回的是当前元素相对于其 offsetParent 
元素的顶部的距离。
offsetLeft 返回的是当前元素相对于其 offsetParent 
元素的左部的距离。

scrollWidth/scrollHeight 返回值包含 
content + padding + 溢出内容的尺寸。
scrollTop 属性返回的是一个元素的内容垂直滚动的像素数。
scrollLeft 属性返回的是元素滚动条到元素左边的距离。
```

```
offsetWidth/offsetHeight返回值包含content + padding + 
border，效果与e.getBoundingClientRect()相同
clientWidth/clientHeight返回值只包含content + padding，
如果有滚动条，也不包含滚动条
scrollWidth/scrollHeight返回值包含content + padding + 
溢出内容的尺寸
```

  #### toPrecision和toFixed和Math.round的区别
```
toPrecision 用于处理精度，精度是从左至右第一个
不为 0 的数开始数起。

toFixed 是对小数点后指定位数取整，从小数点开始数起。

Math.round 是将一个数字四舍五入到一个整数。
```

  #### Unicode和UTF-8之间的关系
```
Unicode 是一种字符集合，现在可容纳 100 多万个字符。每个字符
对应一个不同的 Unicode 编码，它只规定了符号的二进制代码，
却没有规定这个二进制代码在计算机中如何编码传输。

UTF-8 是一种对 Unicode 的编码方式，它是一种变长的编码方式，
可以用 1~4 个字节来表示一个字符。
```

  #### window.onload和$(document).ready
```
原生JS的window.onload与Jquery的
$(document).ready(function(){})有什么不同？
如何用原生JS实现Jq的ready方法？

window.onload()方法是必须等到页面内包括图片的
所有元素加载完毕后才能执行。
$(document).ready()是DOM结构绘制完毕后就执行，
不必等到加载完毕
function ready(fn){
      if(document.addEventListener) {        //标准浏览器
          document.addEventListener('DOMContentLoaded', function() {
              //注销事件, 避免反复触发
              document.removeEventListener('DOMContentLoaded',arguments.callee, false);
              fn();            //执行函数
          }, false);
      }else if(document.attachEvent) {        //IE
          document.attachEvent('onreadystatechange', function() {
             if(document.readyState == 'complete') {
                 document.detachEvent('onreadystatechange', arguments.callee);
                 fn();        //函数执行
             }
         });
     }
 };
```

  #### 区分什么是“客户区坐标”、“页面坐标”、“屏幕坐标”
```
客户区坐标：鼠标指针在可视区中的
水平坐标(clientX)和垂直坐标(clientY)

页面坐标：鼠标指针在页面布局中的
水平坐标(pageX)和垂直坐标(pageY)

屏幕坐标：设备物理屏幕的
水平坐标(screenX)和垂直坐标(screenY)
```

如何获得一个DOM元素的绝对位置？
```
elem.offsetLeft：返回元素相对于其定位父级左侧的距离
elem.offsetTop：返回元素相对于其定位父级顶部的距离
elem.getBoundingClientRect()：返回一个DOMRect对象，
包含一组描述边框的只读属性，单位像素
```


### 算法

  #### 常用正则表达式
```js
// （1）匹配 16 进制颜色值
var regex = /#([0-9a-fA-F]{6}|[0-9a-fA-F]{3})/g;

// （2）匹配日期，如 yyyy-mm-dd 格式
var regex = /^[0-9]{4}-(0[1-9]|1[0-2])-(0[1-9]|[12][0-9]|3[01])$/;

// （3）匹配 qq 号
var regex = /^[1-9][0-9]{4,10}$/g;

// （4）手机号码正则
var regex = /^1[34578]\d{9}$/g;

// （5）用户名正则
var regex = /^[a-zA-Z\$][a-zA-Z0-9_\$]{4,16}$/;
```

```
正则表达式构造函数var reg=new RegExp(“xxx”)与正则表达
字面量var reg=//有什么不同？匹配邮箱的正则表达式？

当使用RegExp()构造函数的时候，不仅需要转义引号
（即\”表示”），并且还需要双反斜杠（即\\表示一个\）。
使用正则表达字面量的效率更高

邮箱的正则匹配：
var regMail = /^([a-zA-Z0-9_-])+@([a-zA-Z0-9_-])+((.[a-zA-Z0-9_-]{2,3}){1,2})$/;
```

  #### 生成随机数的各种方法
```
一、随机浮点数的生成
1，生成 [ 0, 1 ) 范围内的随机数（大于等于0，小于1）
（1）使用 random() 方法可以返回一个介于 0 ~ 1 
之间的伪随机数（包括 0，不包括 1）。
Math.random()

（2）下面是一个测试样例
var random = Math.random();
console.log(random);

2，生成 [ n, m ) 范围内的随机数（大于等于n，小于m）
（1）这种最简单，因为和 random 的特点保持一致。
只需使用如下公式即可：
Math.random()*(m-n)+n

（2）比如下面生成 [10,15) 范围内的随机浮点数。
var random1 = Math.random()*(15-10)+10;
var random2 = Math.random()*(15-10)+10;
var random3 = Math.random()*(15-10)+10;
console.log(random1);
console.log(random2);
console.log(random3);

3，生成 [n,m]、(n,m)、(n,m] 范围内的随机数
因为 random 的特点，要取得这几个区间内的浮点数
稍微麻烦些，需要借助一些判断才能满足要求。

//取得[n,m]范围随机数
function fullClose(n,m) {
   var result = Math.random()*(m+1-n)+n;
   while(result>m) {
       result = Math.random()*(m+1-n)+n;
   }
   return result;
}
 
//取得(n,m)范围随机数
function fullOpen(n,m) {
   var result = Math.random()*(m-n)+n;
   while(result == n) {
       result = Math.random()*(m-n)+n;
   }
   return result;
}
 
//取得(n,m]范围随机数
function leftOpen(n,m) {
   var result = Math.random()*(m-n+1)+n-1;
   while(result<n) {
       result = Math.random()*(m-n+1)+n-1;
   }
   return result;
}

二、随机整数的生成
要生成随机整数，我们还需要借助如下两个方法：
    Math.round(num)：将 num 四舍五入取整
    Math.floor(num)：将 num 向下取整，即返回 num 的整数部分。
    当然我们也可以使用 parseInt() 方法代替。

1，随机生成 0、1 这两个整数
（1）下面这个方法可以随机获取 0 或 1，
它们获取到的几率是比较均衡的。
Math.round(Math.random())

（2）下面是一个测试样例
var random1 = Math.round(Math.random());
var random2 = Math.round(Math.random());
var random3 = Math.round(Math.random());
console.log(random1);
console.log(random2);
console.log(random3);

2，生成 [ 0, n ) 范围内的随机整数（大于等于0，小于n）
（1）下面方法生成一个 0 到 n-1 的随机整数
（这 n 个数获取几率都是均衡的）
Math.floor(Math.random()*n)

（2）比如下面生成几个 0 到 4 的随机整数（包括 0 和 4）。
var random1 = Math.floor(Math.random()*5);
var random2 = Math.floor(Math.random()*5);
var random3 = Math.floor(Math.random()*5);
console.log(random1);
console.log(random2);
console.log(random3);

3，生成 [ 1, n ] 范围内的随机整数（大于等于1，小于等于n）
（1）下面方法生成一个 1 到 n 的随机整数
（这 n 个数获取几率都是均衡的）
Math.floor(Math.random()*n)+1

（2）比如下面生成几个 1 到 5 的随机整数（包括 1 和 5）。
var random1 = Math.floor(Math.random()*5)+1;
var random2 = Math.floor(Math.random()*5)+1;
var random3 = Math.floor(Math.random()*5)+1;
console.log(random1);
console.log(random2);
console.log(random3);

4，生成 [ min, max ] 范围内的随机整数
（大于等于min，小于等于max）
（1）下面方法生成一个最小值为 min，最大值为 max 的随机整数。
Math.floor(Math.random()*(max-min+1))+min

（2）比如下面生成几个 5 到 10 的随机整数
var random1 = Math.floor(Math.random()*(10-5+1))+5;
var random2 = Math.floor(Math.random()*(10-5+1))+5;
var random3 = Math.floor(Math.random()*(10-5+1))+5;
console.log(random1);
console.log(random2);
console.log(random3);

三、随机字符串的生成
1，生成指定位数的纯数字字符串
//生成n位数字字符串
function randomNum(n){
  var res = "";
  for(var i=0;i<n;i++){
    res += Math.floor(Math.random()*10);
  }
  return res;
}
 
//测试
console.log(randomNum(3))
console.log(randomNum(5))
console.log(randomNum(7))
原文:JS - 生成随机数的方法汇总（不同范围、类型的随机数）

2，生成指定位数的数字字母混合的字符串
//生成n位数字字母混合字符串
function generateMixed(n) {
  var chars = ['0','1','2','3','4','5','6','7','8','9',
              'A','B','C','D','E','F','G','H','I','J','K','L','M',
              'N','O','P','Q','R','S','T','U','V','W','X','Y','Z'];
  var res = "";
  for(var i = 0; i < n ; i++) {
     var id = Math.floor(Math.random()*36);
     res += chars[id];
  }
  return res;
}
 
//测试
console.log(generateMixed(3))
console.log(generateMixed(5))
console.log(generateMixed(7))
```

  #### 为什么0.1+0.2!=0.3？如何解决这个问题
```
当计算机计算 0.1+0.2 的时候，实际上计算的是这两个数字在
计算机里所存储的二进制，0.1 和 0.2 在转换为二进制表示的时候
会出现位数无限循环的情况。js 中是以 64 位双精度格式来存储
数字的，只有 53 位的有效数字，超过这个长度的位数会被截取掉
这样就造成了精度丢失的问题。这是第一个会造成精度丢失的地方。
在对两个以 64 位双精度格式的数据进行计算的时候，首先会进行
对阶的处理，对阶指的是将阶码对齐，也就是将小数点的位置对齐后，
再进行计算，一般是小阶向大阶对齐，因此小阶的数在对齐的过程中，
有效数字会向右移动，移动后超过有效位数的位会被截取掉，这是
第二个可能会出现精度丢失的地方。当两个数据阶码对齐后，进行
相加运算后，得到的结果可能会超过 53 位有效数字，因此超过的
位数也会被截取掉，这是可能发生精度丢失的第三个地方。

对于这样的情况，我们可以将其转换为整数后再进行运算，
运算后再转换为对应的小数，以这种方式来解决这个问题。

我们还可以将两个数相加的结果和右边相减，如果相减的结果小于
一个极小数，那么我们就可以认定结果是相等的，这个极小数可以
使用 es6 的 Number.EPSILON
```

- 0.1和0.2在转换成二进制后会无限循环，由于标准位数的限制后面多余的位数会被截掉，此时就已经出现了精度的损失，相加后因浮点数小数位的限制而截断的二进制数字在转换为十进制就会变成0.30000000000000004

  #### 原码、反码和补码的介绍
```
原码是计算机中对数字的二进制的定点表示方法，最高位表示符号位，
其余位表示数值位。优点是易于分辨，缺点是不能够直接参与运算。

正数的反码和其原码一样；负数的反码，符号位为1，
数值部分按原码取反。
如 [+7]原 = 00000111，[+7]反 = 00000111； [-7]原 = 10000111，[-7]反 = 11111000。

正数的补码和其原码一样；负数的补码为其反码加1。

例如 [+7]原 = 00000111，[+7]反 = 00000111，[+7]补 = 00000111；
[-7]原 = 10000111，[-7]反 = 11111000，[-7]补 = 11111001

之所以在计算机中使用补码来表示负数的原因是，这样可以将
加法运算扩展到所有的数值计算上，因此在数字电路中我们只需要
考虑加法器的设计就行了，而不用再为减法设置新的数字电路。
```

  #### 什么是尾调用，使用尾调用有什么好处

```
尾调用指的是函数的最后一步调用另一个函数。我们代码执行是
基于执行栈的，所以当我们在一个函数里调用另一个函数时，我们
会保留当前的执行上下文，然后再新建另外一个执行上下文加入栈中。
使用尾调用的话，因为已经是函数的最后一步，所以这个时候我们可以
不必再保留当前的执行上下文，从而节省了内存，这就是尾调用优化。
但是 ES6 的尾调用优化只在严格模式下开启，正常模式是无效的。
```

  #### js中不同进制数字的表示方式
```
以 0X、0x 开头的表示为十六进制。

以 0、0O、0o 开头的表示为八进制。

以 0B、0b 开头的表示为二进制格式。
```

  #### Math.ceil和Math.floor
```
Math.ceil() === 向上取整，函数返回一个大于或
等于给定数字的最小整数。

Math.floor() === 向下取整，函数返回一个小于或
等于给定数字的最大整数。
```

  #### [,,,]的长度
```
尾后逗号 （有时叫做“终止逗号”）在向 JavaScript 代码添加元素、
参数、属性时十分有用。如果你想要添加新的属性，并且上一行
已经使用了尾后逗号，你可以仅仅添加新的一行，而不需要修改
上一行。这使得版本控制更加清晰，以及代码维护麻烦更少。

JavaScript 一开始就支持数组字面值中的尾后逗号，随后向
对象字面值（ECMAScript 5）中添加了尾后逗号。最近
（ECMAScript 2017），又将其添加到函数参数中。
但是 JSON 不支持尾后逗号。

如果使用了多于一个尾后逗号，会产生间隙。 
带有间隙的数组叫做稀疏数组（密致数组没有间隙）。
稀疏数组的长度为逗号的数量。
```

  #### js for循环注意点
```js
for (var i = 0, j = 0; i < 5, j < 9; i++, j++) {
  console.log(i, j);
}

// 当判断语句含有多个语句时，以最后一个判断语句的值为准，
因此上面的代码会执行 10 次。
// 当判断语句为空时，循环会一直进行。
```


### 其他

  #### hybrid
```
一、hybrid 是什么，为何会用 hybrid
1.1 hybrid 文字解释
hybrid 即“混合”，即前端和客户端的混合开发
需前端开发人员和客户端开发人员配合完成
某些环节也可能涉及到 server 端

1.2 hybrid 存在价值
可以快速迭代更新【关键】（无需 app 审核，思考为何？）
体验流畅（和 NA 的体验基本类似）
减少开发和沟通成本，双端公用一套代码

1.3 webview
是 app 中的一个组件（ app 可以有 webview ，也可以没有）
于加载 h5 页面，即一个小型的浏览器内核

1.4 file 协议
其实在一开始接触 html开发，就已经使用了 file 协议
只不过你当时没有“协议”“标准”等这些概念

1.5 http(s) 协议

1.6 两者区别
file 协议：本地文件，快
http(s) 协议：网络加载，慢
1.7 具体实现
不是所有场景都适合使用 hybrid
使用 NA ：体验要求极致，变化不频繁（无头条的首页）
使用 hybrid ：体验要求高，变化频繁（如头条的新闻详情页）
使用 h5 ：体验无要求，不常用（如举报、反馈等页面）
实现
前端做好静态页面（html js css），将文件交给客户端
客户端拿到前端静态页面，以文件形式存储在 app 中
客户端在一个 webview 中
使用 file 协议加载静态页面

二、hybrid 更新上线流程
2.1 具体流程图
要替换每个客户端的静态文件
只能客户端来做（客户端是我们开发的）
客户端去 server 下载最新的静态文件
我们维护 server 的静态文件

2.2 完整流程
分版本，有版本号，如 201803211015
将静态文件压缩成 zip包，上传到服务端
客户端每次启动，都去服务端检查版本号
如果服务端版本号大于客户端版本号，就去下载最新的 zip 包
下载完之后解压包，然后将现有文件覆盖

要点总结
要点1：服务端的版本和zip包维护
要点2：更新zip 包之前，先对比版本号
要点3：zip 下载解压和覆盖

三、hybrid 和 h5 的区别
3.1 优点
体验更好，跟 NA体验基本一致
可快速迭代，无需 app 审核【关键】
3.2 缺点
开发成本高。联调、测试、查 bug 都比较麻烦
运维成本高。参考此前讲过的更新上线的流程
3.3 适用的场景
hybrid ： 产品的稳定功能，体验要求高，迭代频繁
h5 ： 单词的运营活动（如 xx 红包）或不常用功能

四、前端和客户端通讯
4.1 JS 和客户端通讯的基本形式
JS 访问客户端能力，传递参数和回调函数
客户端通过回调函数返回内容

4.2 schema 协议简介和使用
之前介绍了 http(s) 和 file 协议
schema 协议 —— 前端和客户端通讯的约定

4.3 schema 使用的封装

4.4 内置上线
将以上封装的代码打包，叫做 invoke.js，内置到客户端
客户端每次启动 webview，都默认执行 invoke.js
本地加载，免去网络加载的时间，更快
本地加载，没有网络请求，黑客看不到 schema 协议，更安全
```

  #### 组件化
```
一、说一下对组件化的理解
1.1 组件的封装
视图
数据
变化逻辑

1.2 组件的复用
props 传递
复用

二、JSX 本质是什么
2.1 JSX 语法
html 形式
引入 JS 变量和表达式
循环
style 和 className
事件
JSX 语法根本无法被浏览器所解析
那么它如何在浏览器运行？

2.2 JSX 解析
JSX 其实是语法糖
开发环境会将 JSX 编译成 JS 代码
JSX 的写法大大降低了学习成本和编码工作量
同时，JSX 也会增加 debug成本

2.3 JSX 独立的标准
JSX 是 React 引入的，但不是 React 独有的
React已经将它作为一个独立标准开放，其他项目也可用
React.createElement 是可以自定义修改的
说明：本身功能已经完备；和其他标准监控和扩展性没问题

三、JSX 和 vdom 的关系
3.1 为何需要 vdom
vdom 是 React初次推广开来的，结合 JSX
JSX 就是模板，最终要渲染成 html
初次渲染 + 修改 state 后的 re-render
正好符合 vdom 的应用场景

3.2 React.createElement 和 h

3.3 何时 patch
初次渲染 - ReactDOM.render(<App/>, container)
会触发 patch(container, vnode)
re-render - setState
会触发 patch(vnode, newVnode)

3.4 自定义组件的解析
‘div’ - 直接渲染 <div> 即可，vdom 可以做到
Input 和 List ，是自定义组件（class），vdom 默认不认识
因此 Input 和 List 定义的时候必须声明 render 函数
根据 props 初始化实例，然后执行实例的 render 函数
render 函数返回的还是 vnode对象

四、说一下 React setState 的过程
4.1 setState 的异步

setState 为何需要异步？
可能会一次执行多次 setState
你无法规定、限制用户如何使用 setState
没必要每次 setState 都重新渲染，考虑性能
即便是每次重新渲染，用户也看不到中间的效果
只看到最后的结果即可

4.2 vue 修改属性也是异步
效果、原因和 setState 一样

4.3 setState 的过程
每个组件实例，都有renderComponent 方法
执行 renderComponent 会重新执行实例的 render
render 函数返回 newVnode ，然后拿到 preVnode
执行 patch(preVnode, newVnode)

五、React vs vue
5.1 两者的本质区别
vue - 本质是 MVVM 框架，由 MVC 发展而来
React - 本质是前端组件化框架，由后端组件化发展而来
但这并不妨碍他们两者都能实现相同的功能

5.2 看模板和组件化的区别
vue- 使用模板（最初由 angular 提出）
React- 使用 JSX
模板语法上，我更加倾向于 JSX
模板分离上，我更加倾向于 vue

模板的区别
模板应该和 JS 逻辑分离

组件化区别
React 本身就是组件化，没有组件化就不是 React
vue 也支持组件化，不过是在 MVVM 上的扩展
对于组件化，我更加倾向于 React ，做的彻底而清晰

5.3 两者共同点
都支持组件化
都是数据驱动试图
```

  #### 如何测试前端代码？知道BDD,TDD,Unit Test吗？知道怎么测试你的前端工程吗(mocha,sinon,jasmin,qUnit..)
```
1.前端单元测试是什么
首先我们要明确测试是什么：
为检测特定的目标是否符合标准而采用专用的工具
或者方法进行验证，并最终得出特定的结果。

对于前端开发过程来说，这里的特定目标就是指我们写的代码，
而工具就是我们需要用到的测试框架(库)、测试用例等。
检测处的结果就是展示测试是否通过或者给出测试报告，
这样才能方便问题的排查和后期的修正。

基于测试“是什么”的说法，为便于刚从事前端开发的同行的
进阶理解，那我们就列出单元测试它“不是什么”：
需要访问数据库的测试不是单元测试
需要访问网络的测试不是单元测试
需要访问文件系统的测试不是单元测试

对于单元测试“不是什么”的引用解释，至此点到为止。
鉴于篇幅限制，对于引用内容，我想前端开发的同行们
看到后会初步有一个属于自己的理解。

2.单元测试的意义以及为什么需要单元测试
2.1   单元测试的意义
对于现在的前端工程，一个标准完整的项目，测试是非常有必要的。
很多时候我们只是完成了项目而忽略了项目测试的部分，
测试的意义主要在于下面几点：
（1）TDD（测试驱动开发） 被证明是有效的软件编写原则，
它能覆盖更多的功能接口。
（2）快速反馈你的功能输出，验证你的想法。
（3）保证代码重构的安全性，没有一成不变的代码，
测试用例能给你多变的代码结构一个定心丸。
（4）易于测试的代码，说明是一个好的设计。做单元测试之前，
肯定要实例化一个东西，假如这个东西有很多依赖的话，
这个测试构7. 造过程将会非常耗时，会影响你的测试效率，
怎么办呢？要依赖分离，一个类尽量保证功能单一，
比如视图与功能分离，这样的话，你的代码也便于维护和理解。

2.2   为什么需要单元测试
（1）首先是一个前端单元测试的根本性原由：JavaScript 是
动态语言，缺少类型检查，编译期间无法定位到错误; JavaScript 
宿主的兼容性问题。比如 DOM 操作在不同浏览器上的表现。
（2）正确性：测试可以验证代码的正确性，在上线前做到心里有底。
（3）自动化：当然手工也可以测试，通过console可以打印出内部信息，
但是这是一次性的事情，下次测试还需要从头来过，效率不能得到保证。
通过编写测试用例，可以做到一次编写，多次运行。
（4）解释性：测试用例用于测试接口、模块的重要性，那么在
测试用例中就会涉及如何使用这些API。其他开发人员如果要使用
这些API，那阅读测试用例是一种很好地途径，有时比文档说明更清晰。
（5）驱动开发，指导设计：代码被测试的前提是代码本身的可测试性，
那么要保证代码的可测试性，就需要在开发中注意API的设计，
TDD将测试前移就是起到这么一个作用。
（6）保证重构：互联网行业产品迭代速度很快，迭代后必然存在
代码重构的过程，那怎么才能保证重构后代码的质量呢？
有测试用例做后盾，就可以大胆的进行重构。

3.如何写单元测试用例
3.1 原则
测试代码时，只考虑测试，不考虑内部实现
数据尽量模拟现实，越靠近现实越好
充分考虑数据的边界条件
对重点、复杂、核心代码，重点测试
利用AOP(beforeEach、afterEach),减少测试代码数量，避免无用功能
测试、功能开发相结合，有利于设计和代码重构

3.2 两个常用的单元测试方法论
在单元测试中，常用的方法论有两个：
TDD（测试驱动开发）&BDD（行为驱动开发）

对于之前没听说过前端测试这两个模式的同行可以在此了解一下，
篇幅限制此处不再敖述。

3.3 相信你看完之后也有一个自己对TDD和BDD的个人观点，
在此我先谈谈我对TDD和BDD的 理解：

TDD（Test-driven development）：
其基本思路是通过测试来推动整个开发的进行。
(1)单元测试的首要目的不是为了能够编写出大覆盖率的全部通过
的测试代码，而是需要从使用者(调用者)的角度出发，
尝试函数逻辑的各种可能性，进而辅助性增强代码质量
(2)测试是手段而不是目的。测试的主要目的不是证明代码正确，
而是帮助发现错误，包括低级的错误
(3)测试要快。快速运行、快速编写
(4)测试代码保持简洁
(5)不会忽略失败的测试。一旦团队开始接受1个测试的构建失败，
那么他们渐渐地适应2、3、4或者更多的失败。
在这种情况下，测试集就不再起作用

需要注意的是：
(1)一定不能误解了TDD的核心目的！
(2)测试不是为了覆盖率和正确率
(3)而是作为实例，告诉开发人员要编写什么代码
(4)红灯（代码还不完善，测试挂）-> 绿灯（编写代码，测试通过）-> 重构（优化代码并保证测试通过）

TDD的过程是：
(1)需求分析，思考实现。考虑如何“使用”产品代码，是一个实例方法还是
一个类方法，是从构造函数传参还是从方法调用传参，方法的命名，返回值
等。这时其实就是在做设计，而且设计以代码来体现。此时测试为红
(2)实现代码让测试为”绿灯“
(3)重构，然后重复测试
(4)最终符合所有要求即：
	每个概念都被清晰的表达
	代码中无自我重复
	没有多余的东西
	通过测试

BDD(Behavior-driven development)：
行为驱动开发（BDD），重点是通过与利益相关者（简单说就是
客户）的讨论，取得对预期的软件行为的认识，其重点在于沟通

BDD过程是：
(1)从业务的角度定义具体的，以及可衡量的目标
(2)找到一种可以达到设定目标的、对业务最重要的那些功能的方法
(3)然后像故事一样描述出一个个具体可执行的行为。其描述方法
基于一些通用词汇，这些词汇具有准确无误的表达能力和一致的含义。
例如，expect, should, assert
(4)寻找合适语言及方法，对行为进行实现
(5)测试人员检验产品运行结果是否符合预期行为。最大程度的
交付出符合用户期望的产品，避免表达不一致带来的问题

4. Mocha/Karma+Travis.CI的前端测试工作流
```

  #### 为什么通常在发送数据埋点请求的时候使用的是1x1像素的透明gif图片
```
能够完成整个 HTTP 请求+响应（尽管不需要响应内容）

触发 GET 请求之后不需要获取和处理数据、服务器也不需要发送数据

跨域友好

执行过程无阻塞

相比 XMLHttpRequest 对象发送 GET 请求，性能上更好

GIF的最低合法体积最小（最小的BMP文件需要74个字节，
PNG需要67个字节，而合法的GIF，只需要43个字节）
```

  #### 如何确定页面的可用性时间，什么是Performance API
```
Performance API 用于精确度量、控制、增强浏览器的性能表现。
这个 API 为测量网站性能，提供以前没有办法做到的精度。

使用 getTime 来计算脚本耗时的缺点，首先，getTime方法
（以及 Date 对象的其他方法）都只能精确到毫秒级别（一秒的
千分之一），想要得到更小的时间差别就无能为力了。其次，
这种写法只能获取代码运行过程中的时间进度，无法知道一些
后台事件的时间进度，比如浏览器用了多少时间从服务器加载网页。

为了解决这两个不足之处，ECMAScript 5引入“高精度时间戳”
这个 API，部署在 performance 对象上。它的精度可以
达到1毫秒的千分之一（1秒的百万分之一）。

navigationStart：当前浏览器窗口的前一个网页关闭，
发生 unload 事件时的 Unix 毫秒时间戳。如果没有前一个网页，
则等于 fetchStart 属性。

loadEventEnd：返回当前网页 load 事件的回调函数运行
结束时的 Unix 毫秒时间戳。如果该事件还没有发生，返回 0。
```

根据上面这些属性，可以计算出网页加载各个阶段的耗时。
比如，网页加载整个过程的耗时的计算方法如下：

```js
var t = performance.timing;
var pageLoadTime = t.loadEventEnd - t.navigationStart;
```

  #### Electron
```
最最重要的一点，electron 实际上是一个套了 Chrome 
的 nodeJS程序

所以应该是从两个方面说开来
Chrome （无各种兼容性问题）；
NodeJS（NodeJS 能做的它也能做）
```

  #### 有四个操作会忽略enumerable为false的属性
```
for...in循环：只遍历对象自身的和继承的可枚举的属性。
Object.keys()：返回对象自身的所有可枚举的属性的键名。
JSON.stringify()：只串行化对象自身的可枚举的属性。
Object.assign()： 忽略enumerable为false的属性，
只拷贝对象自身的可枚举的属性。
```

  #### 一道常被人轻视的前端JS面试题
```js
function Foo() {
  getName = function() {
    alert(1);
  };
  return this;
}
Foo.getName = function() {
  alert(2);
};
Foo.prototype.getName = function() {
  alert(3);
};
var getName = function() {
  alert(4);
};
function getName() {
  alert(5);
}

//请写出以下输出结果：
Foo.getName(); // 2
getName(); // 4
Foo().getName(); // 1
getName(); // 1
new Foo.getName(); // 2
new Foo().getName(); // 3
new new Foo().getName(); // 3
```

#### 内存机制
- 网上的资料基本是这样说的: 基本数据类型用栈存储，引用数据类型用堆存储。
- 看起来没有错误，但实际上是有问题的。可以考虑一下闭包的情况，如果变量存在栈中，那函数调用完栈顶空间销毁，闭包变量不就没了吗？

其实还是需要补充一句:
- 闭包变量是存在堆内存中的。

具体而言，以下数据类型存储在栈中:
- boolean
- null
- undefined
- number
- string
- symbol
- bigint

而所有的对象数据类型存放在堆中。
- 值得注意的是，对于赋值操作，原始类型的数据直接完整地复制变量值，对象数据类型的数据则是复制引用地址。

因此会有下面的情况:
```
let obj = { a: 1 };
let newObj = obj;
newObj.a = 2;
console.log(obj.a);//变成了2
```
- 之所以会这样，是因为 obj 和 newObj 是同一份堆空间的地址，改变newObj，等于改变了共同的堆内存，这时候通过 obj 来获取这块内存的值当然会改变。 当然，你可能会问: 为什么不全部用栈来保存呢？
- 首先，对于系统栈来说，它的功能除了保存变量之外，还有创建并切换函数执行上下文的功能。举个例子:

当然，你可能会问: 为什么不全部用栈来保存呢？
- 首先，对于系统栈来说，它的功能除了保存变量之外，还有创建并切换函数执行上下文的功能。举个例子:
```
function f(a) {
  console.log(a);
}

function func(a) {
  f(a);
}

func(1);
```
- 假设用ESP指针来保存当前的执行状态，在系统栈中会产生如下的过程：
- 调用func, 将 func 函数的上下文压栈，ESP指向栈顶。
- 执行func，又调用f函数，将 f 函数的上下文压栈，ESP 指针上移。
- 执行完 f 函数，将ESP 下移，f函数对应的栈顶空间被回收。
- 执行完 func，ESP 下移，func对应的空间被回收。

- 因此你也看到了，如果采用栈来存储相对基本类型更加复杂的对象数据，那么切换上下文的开销将变得巨大！
- 不过堆内存虽然空间大，能存放大量的数据，但与此同时垃圾内存的回收会带来更大的开销

#### 执行上下文
当执行 JS 代码时，会产生三种执行上下文
- 全局执行上下文
- 函数执行上下文
- eval 执行上下文

每个执行上下文中都有三个重要的属性
- 变量对象（VO），包含变量、函数声明和函数的形参，该属性只能在全局上下文中访问
- 作用域链（JS 采用词法作用域，也就是说变量的作用域是在定义时就决定了）
- this
```
var a = 10
function foo(i) {
  var b = 20
}
foo()
```
对于上述代码，执行栈中有两个上下文：全局上下文和函数 foo 上下文。
```
stack = [
    globalContext,
    fooContext
]
```
对于全局上下文来说，VO大概是这样的
```
globalContext.VO === globe
globalContext.VO = {
    a: undefined,
	foo: <Function>,
}
```
对于函数 foo 来说，VO 不能访问，只能访问到活动对象（AO）
```
fooContext.VO === foo.AO
fooContext.AO {
    i: undefined,
	b: undefined,
    arguments: <>
}
// arguments 是函数独有的对象(箭头函数没有)
// 该对象是一个伪数组，有 `length` 属性且可以通过下标访问元素
// 该对象中的 `callee` 属性代表函数本身
// `caller` 属性代表函数的调用者
```
- 对于作用域链，可以把它理解成包含自身变量对象和上级变量对象的列表，通过 [[Scope]]属性查找上级变量
```
fooContext.[[Scope]] = [
    globalContext.VO
]
fooContext.Scope = fooContext.[[Scope]] + fooContext.VO
fooContext.Scope = [
    fooContext.VO,
    globalContext.VO
]
```
接下来让我们看一个老生常谈的例子，var
```
b() // call b
console.log(a) // undefined

var a = 'Hello world'

function b() {
	console.log('call b')
}
```
- 想必以上的输出大家肯定都已经明白了，这是因为函数和变量提升的原因。通常提升的解释是说将声明的代码移动到了顶部，这其实没有什么错误，便于大家理解。但是更准确的解释应该是：在生成执行上下文时，会有两个阶段。第一个阶段是创建的阶段（具体步骤是创建 VO），JS 解释器会找出需要提升的变量和函数，并且给他们提前在内存中开辟好空间，函数的话会将整个函数存入内存中，变量只声明并且赋值为 undefined，所以在第二个阶段，也就是代码执行阶段，我们可以直接提前使用。

- 在提升的过程中，相同的函数会覆盖上一个函数，并且函数优先于变量提升
```
b() // call b second

function b() {
	console.log('call b fist')
}
function b() {
	console.log('call b second')
}
var b = 'Hello world'
```
- var会产生很多错误，所以在 ES6中引入了 let。let不能在声明前使用，但是这并不是常说的 let 不会提升，let 提升了声明但没有赋值，因为临时死区导致了并不能在声明前使用。

- 对于非匿名的立即执行函数需要注意以下一点
```
var foo = 1
(function foo() {
    foo = 10
    console.log(foo)
}()) // -> ƒ foo() { foo = 10 ; console.log(foo) }
```
因为当 JS 解释器在遇到非匿名的立即执行函数时，会创建一个辅助的特定对象，然后将函数名称作为这个对象的属性，因此函数内部才可以访问到 foo，但是这个值又是只读的，所以对它的赋值并不生效，所以打印的结果还是这个函数，并且外部的值也没有发生更改。
```
specialObject = {};

Scope = specialObject + Scope;

foo = new FunctionExpression;
foo.[[Scope]] = Scope;
specialObject.foo = foo; // {DontDelete}, {ReadOnly}

delete Scope[0]; // remove specialObject from the front of scope chain
```

小结
执行上下文可以简单理解为一个对象:
- 它包含三个部分:
  - 变量对象(VO)
  - 作用域链(词法作用域)
  - this指向
- 它的类型:
  - 全局执行上下文
  - 函数执行上下文
  - eval执行上下文
- 代码执行过程:
  - 创建 全局上下文 (global EC)
  - 全局执行上下文 (caller) 逐行 自上而下 执行。遇到函数时，函数执行上下文 (callee) 被push到执行栈顶层
  - 函数执行上下文被激活，成为 active EC, 开始执行函数中的代码，caller 被挂起
  - 函数执行完后，callee 被pop移除出执行栈，控制权交还全局上下文 (caller)，继续执行

#### 代码的复用
- 当你发现任何代码开始写第二遍时，就要开始考虑如何复用。一般有以下的方式:
  - 函数封装
  - 继承
  - 复制extend
  - 混入mixin
  - 借用apply/call

#### JavaScript实现对上传图片的压缩
- 答：读取用户上传的 File 对象，读写到画布（canvas）上，利用 Canvas 的 API 进行压缩，完成压缩之后再转成 File（Blob） 对象，上传到远程图片服务器；不过有时候我们也需要将一个 base64 字符串压缩之后再变为 base64 字符串传入到远程数据库或者再转成 File（Blob） 对象。

- 思路就是 File + Canvas 的 drawImage



### ES6
```
新增模板字符串（为JavaScript提供了简单的字符串插值功能）
箭头函数
for-of（用来遍历数据—例如数组中的值。）
arguments对象可被不定参数和默认参数完美代替。
ES6将promise对象纳入规范，提供了原生的Promise对象。
增加了let和const命令，用来声明变量。
增加了块级作用域。
let命令实际上就增加了块级作用域。
还有就是引入module模块的概念
```
 
#### ES6的了解
- 新增模板字符串（为JavaScript提供了简单的字符串插值功能）、箭头函数（操作符左边为输入的参数，而右边则是进行的操作以及返回的值Inputs=>outputs。）、for-of（用来遍历数据—例如数组中的值。）arguments对象可被不定参数和默认参数完美代替。ES6将promise对象纳入规范，提供了原生的Promise对象。增加了let和const命令，用来声明变量。增加了块级作用域。let命令实际上就增加了块级作用域。ES6规定，var命令和function命令声明的全局变量，属于全局对象的属性；let命令、const命令、class命令声明的全局变量，不属于全局对象的属性。。还有就是引入module模块的概念

#### ES5、ES6和ES2015有什么区别
- ES2015特指在2015年发布的新一代JS语言标准，ES6泛指下一代JS语言标准，包含ES2015、ES2016、ES2017、ES2018等。现阶段在绝大部分场景下，ES2015默认等同ES6。ES5泛指上一代语言标准。ES2015可以理解为ES5和ES6的时间分界线

  #### es6新特性
- 1.箭头函数
- 2.新增模板字符串，为 JavaScript 提供了简单的字符串插值功能
- 3.新增了 let 和 const 命令，用来声明变量
```
let 所声明的变量，只在let 命令所在的代码块内有效。const 声明的变量是常量，不能被修改
```
- 4.增加了块级作用域，let 命令实际上就增加了块级作用域
- 5.es6 将 Promise 对象纳入规范，提供了原生的 Promise 对象
- 6.提供了 set 和 map 的数据结构
- 7.for-of 用来遍历数据，例如数组中的值
- 8.arguments 对象可被不定参数和默认参数完美代替
- 9.还有就是引入 module 模块的概念

```
5.所谓Promise，简单说就是一个容器，里面保存着某个未来
6.才会结束的事件（通常是一个异步操作）的结果。
从语法上说，Promise 是一个对象，从它可以获取异步操作的消息。
Promise 提供统一的 API，各种异步操作都可以用同样的方法进行处理。
我们可以通过Promise的构造函数来创建Promise对象，
并在内部封装一个异步执行的结果。

如果我们想要等待异步执行完成，做一些事情，
我们可以通过promise的then方法来实现

如果想要处理promise异步执行失败的事件，还可以跟上catch
```

```
6. Set，本质与数组类似。不同在于Set中只能保存不同元素，
如果元素相同会被忽略。
map，本质是与Object类似的结构。不同在于，
Object强制规定key只能是字符串。
而Map结构的key可以是任意对象。
即：object是 <string,object>集合map是<object,object>集合
```

- 块级作用区域 let a = 1;
- 可定义常量 const PI = 3.141592654;
- 变量解构赋值 var [a, b, c] = [1, 2, 3];
- 字符串的扩展(模板字符串) var sum =${a + b};
- 数组的扩展(转换数组类型) Array.from($('li'));
- 函数的扩展(扩展运算符) [1, 2].push(...[3, 4, 5]);
- 对象的扩展(同值相等算法) Object.is(NaN, NaN);
- 新增数据类型(Symbol) let uid = Symbol('uid');
- 新增数据结构(Map) let set = new Set([1, 2, 2, 3]);
- for...of循环 for(let val of arr){};
- Promise对象 var promise = new Promise(func);
- Generator函数 function* foo(x){yield x; return x*x;}
- 引入Class(类) class Foo {}
- 引入模块体系 export default func;
- 引入async函数[ES7]
```
async function asyncPrint(value, ms) {
      await timeout(ms);
      console.log(value)
     }
```

  #### let var const
```
let命令不存在变量提升，如果在let前使用，会导致报错
如果块区中存在let和const命令，就会形成封闭作用域
不允许重复声明，因此，不能在函数内部重新声明参数
```

```
1.声明的变量只在声明时的代码块内有效
2.不存在声明提升
3.存在暂时性死区，如果在变量声明前使用，会报错
4.不允许重复声明，重复声明会报错
```

```
let：
允许你声明一个作用域被限制在块级中的变量、语句或者表达式

let绑定不受变量提升的约束，这意味着let声明不会被提升到当前

该变量处于从块开始到初始化处理的“暂存死区”

var：
声明变量的作用域限制在其声明位置的上下文中，而非声明变量总是全局的

由于变量声明（以及其他声明）总是在任意代码执行之前处理的，
所以在代码中的任意位置声明变量总是等效于在代码开头声明

const：
声明创建一个值的只读引用 (即指针)

基本数据当值发生改变时，那么其对应的指针也将发生改变，
故造成 const申明基本数据类型时

再将其值改变时，将会造成报错， 例如 const a = 3 ; a = 5时 将会报错

但是如果是复合类型时，如果只改变复合类型的其中某个Value项时， 
将还是正常使用
```

```
对于var、let、const他们三个的比较和总结，我们用几段代码来说明一下：
const a1 = 100;
a1 = 200;  //报错Assignment to constant variable
上述代码说明了const定义的是一个常量，而且更改之后会报错。

var a1 = 100;
let a2 = 100;
const a3 = 100;
console.log(window.a1);  
100console.log(window.a2);  //undefined
console.log(window.a3);  //undefined
上述代码说明了var定义的变量会挂载到window上，而let和const定义的则不会。

console.log(a1);  //undefinedvar a1 = 100;
console.log(a2);  //报错const a2 = 100;
console.log(a3);  //报错let a3 = 100;
上述代码说明了var定义的变量会提升，let和const定义的则不会。
let和const必须严格遵守先定义在访问的原则。

if (true) {    
	var a1 = 100;    
	let a2 = 100;    
	const a3 = 100;
}
console.log(a1) //100
console.log(a2) //报错
console.log(a3) //报错
let和const定义的值，其作用域会被限制在定义的
作用域中，不能被别的作用于访问，但是var可以。

const a = '123';
a = '456'; //报错
const obj = {    
        name : 1
}
obj.name = 2; //正确
const定义的基本数据类型不可更改，定义的
引用数据类型可以更改。因为基本数据类型保存在栈中，
即定义的常量值即为后边赋的值。引用数据类型保存
在堆中，但是他的地址保存在栈中，用const定义的
引用数据类型中保存的值实际上为此引用数据类型
在栈中的地址，所以只要地址不改变，
改变引用数据类型中的字段是没有问题的。
```

#### 全局作用域中，用const和let声明的变量不在window上，那到底在哪里？如何去获取
```
// 在 ES5 中，顶层对象的属性和全局变量是等价的，var 命令和 function 命令声明的全局变量，自然也是顶层对象。
var a = 12;
function f(){};
console.log(window.a);
// 12console.log(window.f);
// f(){}

// 但 ES6 规定，var 命令和 function 命令声明的全局变量，依旧是顶层对象的属性，但 let 命令、const 命令、class 命令声明的全局变量，不属于顶层对象的属性。
let aa = 1;
const bb = 2;
console.log(window.aa);
// undefinedconsole.log(window.bb);
// undefined

// 在哪里？怎么获取？通过在设置断点，看看浏览器是怎么处理的：
//通过上图也可以看到，在全局作用域中，用 let 和 const 声明的全局变量并没
//有在全局对象中，只是一个块级作用域（Script）中怎么获取？在定义变量的块级作用域中就能获取啊，既然不属于顶层对象，那就不加 window（global）呗。
let aa = 1;
const bb = 2;
console.log(aa);
// 1console.log(bb);
// 2
```

  #### 箭头函数
```
箭头函数的几种基本写法如下：
let func = (num)=>num ; //表示传入num，返回num，省略了return关键字
let func1 = num=>num;   //如果只传递一个参数，可以省略括号
let func2 = ()=>{    //比较标准的写法
    console.log(111)
}
箭头函数中的this是常考的点，下面我们用es5
的this和箭头函数中的this做一个比较，代码如下：
var obj1 = {
    name : "Edward",
    print : function(){
        console.log(this.name); //Edward
    }
}
obj1.print()

var obj2 = {
    name : "Eric",
    print : ()=>{
        console.log(this.name); //undefined
    }
}
obj2.print()

上述代码中，es5函数中的this指向调用这个函数的
对象obj1，所以可以打印出name值。箭头函数中的
this指向的并不是调用这个函数的对象obj2，
所以打印不出name值。
var obj2 = {
    name : "Eric",
    print : ()=>{
        console.log(this.name); //undefined
    }
}
obj2.print.call(obj2);
上述代码中我们试着用call方法改变print函数的
this指向，发现依然是没有效果的。
那么箭头函数中的this指向谁呢？我们接着看：
var obj2 = {
    name : "Eric",
    print : ()=>{
        console.log(this) ;//Window
    }
}
obj2.print.call(obj2);
经过打印后得知箭头函数中的this指向了window对象，
下面我们接着看：
function handle(){
    return ()=>{
        console.log(this.name) //edward
    }
}
var obj = {
    name : 'edward',
    handle : handle
}
obj.handle()()
上述代码中运行街头函数后得知this指向了obj对象。
综合上边代码，可以发现，
箭头函数的this指向了他所在函数的父级作用域。
var a = ()=>{
    console.log(arguments); //不是[1,2,....]
}
a(1,2)
上述代码运行时，并不能获取正确的arguments，即箭头函数不能使用

arguments对象
var Humen = (name)=>{  //报错
    this.name = name
}
var humen = new Humen('edward');
console.log(humen)
上述代码中使用箭头函数作为构造函数发现报错了，
即箭头函数不能作为构造函数，
因为es6中有class关键字可以做这个事儿。
```

```
function a() {
    return () => {
        return () => {
        	console.log(this)
        }
    }
}
console.log(a()()())
```
- 箭头函数其实是没有 this 的，这个函数中的 this 只取决于他外面的第一个不是箭头函数的函数的 this。在这个例子中，因为调用 a 符合前面代码中的第一个情况，所以 this 是window。并且 this一旦绑定了上下文，就不会被任何代码改变

  #### 模板字符串
```
这个比较简单，直接上代码。
var a = '100';
var str = `我今天考了${a}分`;
console.log(str)
```

  #### for in和for of的区别
```
for in用来遍历普通对象，for of用于遍历可迭代对象。
下边我们用代码来实现一下：
var obj = {
    name : 'edward',
    age : 100
}
var arr = ['a','b']
for(var i in obj){
    console.log(i)  ; //name age
    console.log(obj[i]) //edward 100
}
for(var i of arr){
    console.log(i)  ; //a , b
}
```

- for in性能很差，迭代当前对象中可枚举的属性，并且一直查找到原型上去。

- 问题1：遍历顺序数字优先
- 问题2：无法遍历symbol属性
- 问题3：可以遍历到原型属性中可枚举的
```
let obj = {
  name: 'poetry',
  age: 22,
  [Symbol('aa')]: 100,
  0: 200,
  1: 300
}
数字优先，不能遍历symbol属性
```
```
for(let key in obj) {
  // 不遍历原型上的属性
  if(!obj.hasOwnProperty(key)) {
    break;
  }
}
```
遍历obj的私有属性拼接
```
let keys = Object.keys(obj)
keys = keys.concat(Object.getOwnPropertySymbols(obj1))
keys.forEach(v=>{
  console.log(v)
})
```

for of
- 部分数据结构实现了迭代器规范
  - Symbol.itertor
  - 数组/set/map
  - 对象没有实现，for of不能遍历对象
```
// 数组具备迭代器规范，模拟实现
var arr = [1,2,3,4,5]

arr[Symbol.iterator] = function() {
  let self = this, index = 0;

  return {
    next() {
      if(index > self.length - 1) {
        return {
          done: true,
          value: undefined
        }
      }
      return {
        done: false,
        value: self[index++]
      }
    }
  }
}
```
```
// 使对象具备可迭代特性
let obj = {
  0: 100,
  1: 200,
  length: 2
}

obj[Symbol.iterator] = Array.prototype[Symbol.iterator]

for(var val of obj) {
  console.log(val)
}
```

  #### async/await
```
function demo1(){
    return new Promise((resolve,reject)=>{
        resolve(100)
    })
}

async function handle(){
    var a = await demo1()
    console.log(a)
}
handle()
上述代码简单介绍了async定义函数和await的用法。
其中await后边跟的demo1函数如果返回一个promise对象，
则a的值为promise中resolve传入的值。如果demo1没有
返回一个promise对象，则a的值为undefined。
当执行async函数，遇到await时，不管后边的demo1中
是否存在异步，都先要执行完demo1，再往下执行async
定义的函数中的其他语句。

原理：async顾名思义是异步的意思，即用async申明的
函数为异步函数，await是等待的意思，就是等异步完成，
并且await只能在async中调用。async能简化Promise操作，
await得到Promise对象之后就等待Promise接下来的
resolve或者reject。当你要对执行的函数进行排序时，
只需要将函数的位置依次写道await后边即可。
 ```


  - [arguments对象](#arguments对象)
  

  #### 解构赋值
```
var [a,b] = [1,2];
console.log(a , b); //1 2
```

#### babel是什么，有什么作用
- babel是一个 ES6 转码器，可以将 ES6 代码转为 ES5 代码，以便兼容那些还没支持ES6的平台

- Babel 是一个 JS 编译器，自带一组 ES6 语法转化器，用于转化 JS 代码。 这些转化器让开发者提前使用最新的 JS语法(ES6/ES7)，而不用等浏览器全部兼容。
- Babel 默认只转换新的 JS 句法(syntax)，而不转换新的API。

#### let有什么用，有了var为什么还要用let
- 在ES6之前，声明变量只能用var，var方式声明变量其实是很不合理的，准确的说，是因为ES5里面没有块级作用域是很不合理的。没有块级作用域回来带很多难以理解的问题，比如for循环var变量泄露，变量覆盖等问题。let声明的变量拥有自己的块级作用域，且修复了var声明变量带来的变量提升问题。

#### 举一些ES6对String字符串类型做的常用升级优化
优化部分
- ES6新增了字符串模板，在拼接大段字符串时，用反斜杠()`取代以往的字符串相加的形式，能保留所有空格和换行，使得字符串拼接看起来更加直观，更加优雅

升级部分
- ES6在String原型上新增了includes()方法，用于取代传统的只能用indexOf查找包含字符的方法(indexOf返回-1表示没查到不如includes方法返回false更明确，语义更清晰), 此外还新增了startsWith(), endsWith(), padStart(),padEnd(),repeat()等方法，可方便的用于查找，补全字符串

#### 举一些ES6对Array数组类型做的常用升级优化
优化部分
- 数组解构赋值。ES6可以直接以let [a,b,c] = [1,2,3]形式进行变量赋值，在声明较多变量时，不用再写很多let(var),且映射关系清晰，且支持赋默认值
- 扩展运算符。ES6新增的扩展运算符(...)(重要),可以轻松的实现数组和松散序列的相互转化，可以取代arguments对象和apply方法，轻松获取未知参数个数情况下的参数集合。（尤其是在ES5中，arguments并不是一个真正的数组，而是一个类数组的对象，但是扩展运算符的逆运算却可以返回一个真正的数组）。扩展运算符还可以轻松方便的实现数组的复制和解构赋值（let a = [2,3,4]; let b = [...a]）

升级部分
- ES6在Array原型上新增了find()方法，用于取代传统的只能用indexOf查找包含数组项目的方法,且修复了indexOf查找不到NaN的bug([NaN].indexOf(NaN) === -1).此外还新增了copyWithin(),includes(), fill(),flat()等方法，可方便的用于字符串的查找，补全,转换等

#### 举一些ES6对Number数字类型做的常用升级优化
优化部分
- ES6在Number原型上新增了isFinite(), isNaN()方法，用来取代传统的全局isFinite(), isNaN()方法检测数值是否有限、是否是NaN。ES5的isFinite(), isNaN()方法都会先将非数值类型的参数转化为Number类型再做判断，这其实是不合理的，最造成isNaN('NaN') === true的奇怪行为--'NaN'是一个字符串，但是isNaN却说这就是NaN。而Number.isFinite()和Number.isNaN()则不会有此类问题(Number.isNaN('NaN') === false)。（isFinite()同上）

升级部分
- ES6在Math对象上新增了Math.cbrt()，trunc()，hypot()等等较多的科学计数法运算方法，可以更加全面的进行立方根、求和立方根等等科学计算

#### 举一些ES6对Object类型做的常用升级优化
优化部分
- 对象属性变量式声明。ES6可以直接以变量形式声明对象属性或者方法，。比传统的键值对形式声明更加简洁，更加方便，语义更加清晰
```
let [apple, orange] = ['red appe', 'yellow orange'];
let myFruits = {apple, orange};    // let myFruits = {apple: 'red appe', orange: 'yellow orange'};
```
- 尤其在对象解构赋值(见优化部分b.)或者模块输出变量时，这种写法的好处体现的最为明显
```
let {keys, values, entries} = Object;
let MyOwnMethods = {keys, values, entries}; // let MyOwnMethods = {keys: keys, values: values, entries: entries}
```
- 可以看到属性变量式声明属性看起来更加简洁明了。方法也可以采用简洁写法
```
let es5Fun = {
    method: function(){}
}; 
let es6Fun = {
    method(){}
}
```
- 对象的解构赋值。 ES6对象也可以像数组解构赋值那样，进行变量的解构赋值
```
let {apple, orange} = {apple: 'red appe', orange: 'yellow orange'};
```
- 对象的扩展运算符(...)。 ES6对象的扩展运算符和数组扩展运算符用法本质上差别不大，毕竟数组也就是特殊的对象。对象的扩展运算符一个最常用也最好用的用处就在于可以轻松的取出一个目标对象内部全部或者部分的可遍历属性，从而进行对象的合并和分解
```
let {apple, orange, ...otherFruits} = {apple: 'red apple', orange: 'yellow orange', grape: 'purple grape', peach: 'sweet peach'}; 
// otherFruits  {grape: 'purple grape', peach: 'sweet peach'}
// 注意: 对象的扩展运算符用在解构赋值时，扩展运算符只能用在最有一个参数(otherFruits后面不能再跟其他参数)
let moreFruits = {watermelon: 'nice watermelon'};
let allFruits = {apple, orange, ...otherFruits, ...moreFruits};
```
- super 关键字。ES6在Class类里新增了类似this的关键字super。同this总是指向当前函数所在的对象不同，super关键字总是指向当前函数所在对象的原型对象

升级部分
- ES6在Object原型上新增了is()方法，做两个目标对象的相等比较，用来完善'==='方法。'==='方法中NaN === NaN //false其实是不合理的，Object.is修复了这个小bug。(Object.is(NaN, NaN) // true)
- ES6在Object原型上新增了assign()方法，用于对象新增属性或者多个对象合并
```
const target = { a: 1 };
const source1 = { b: 2 };
const source2 = { c: 3 };
Object.assign(target, source1, source2);
target // {a:1, b:2, c:3}
```
- 注意: assign合并的对象target只能合并source1、source2中的自身属性，并不会合并source1、source2中的继承属性，也不会合并不可枚举的属性，且无法正确复制get和set属性（会直接执行get/set函数，取return的值）

- ES6在Object原型上新增了getOwnPropertyDescriptors()方法，此方法增强了ES5中getOwnPropertyDescriptor()方法，可以获取指定对象所有自身属性的描述对象。结合defineProperties()方法，可以完美复制对象，包括复制get和set属性
- ES6在Object原型上新增了getPrototypeOf()和setPrototypeOf()方法，用来获取或设置当前对象的prototype对象。这个方法存在的意义在于，ES5中获取设置prototype对像是通过__proto__属性来实现的，然而__proto__属性并不是ES规范中的明文规定的属性，只是浏览器各大产商“私自”加上去的属性，只不过因为适用范围广而被默认使用了，再非浏览器环境中并不一定就可以使用，所以为了稳妥起见，获取或设置当前对象的prototype对象时，都应该采用ES6新增的标准用法
- ES6在Object原型上还新增了Object.keys()，Object.values()，Object.entries()方法，用来获取对象的所有键、所有值和所有键值对数组

#### 举一些ES6对Function函数类型做的常用升级优化
优化部分
- 箭头函数(核心)。箭头函数是ES6核心的升级项之一，箭头函数里没有自己的this,这改变了以往JS函数中最让人难以理解的this运行机制。主要优化点

- 箭头函数内的this指向的是函数定义时所在的对象，而不是函数执行时所在的对象。ES5函数里的this总是指向函数执行时所在的对象，这使得在很多情况下this的指向变得很难理解，尤其是非严格模式情况下，this有时候会指向全局对象，这甚至也可以归结为语言层面的bug之一。ES6的箭头函数优化了这一点，它的内部没有自己的this,这也就导致了this总是指向上一层的this，如果上一层还是箭头函数，则继续向上指，直到指向到有自己this的函数为止，并作为自己的this
- 箭头函数不能用作构造函数，因为它没有自己的this，无法实例化
- 也是因为箭头函数没有自己的this,所以箭头函数 内也不存在arguments对象。（可以用扩展运算符代替）
- 函数默认赋值。ES6之前，函数的形参是无法给默认值得，只能在函数内部通过变通方法实现。ES6以更简洁更明确的方式进行函数默认赋值
```
function es6Fuc (x, y = 'default') {
    console.log(x, y);
}
es6Fuc(4) // 4, default
```

升级部分
- ES6新增了双冒号运算符，用来取代以往的bind，call,和apply。(浏览器暂不支持，Babel已经支持转码)
```
foo::bar;
// 等同于
bar.bind(foo);

foo::bar(...arguments);
// 等同于
bar.apply(foo, arguments);
```

#### Symbol是什么，有什么作用
- Symbol是ES6引入的第七种原始数据类型（说法不准确，应该是第七种数据类型，Object不是原始数据类型之一，已更正），所有Symbol()生成的值都是独一无二的，可以从根本上解决对象属性太多导致属性名冲突覆盖的问题。对象中Symbol()属性不能被for...in遍历，但是也不是私有属性

symbol 有什么用处
- 可以用来表示一个独一无二的变量防止命名冲突。但是面试官问还有吗？我没想出其他的用处就直接答我不知道了，还可以利用 symbol 不会被常规的方法（除了 Object.getOwnPropertySymbols 外）遍历到，所以可以用来模拟私有变量。

- 主要用来提供遍历接口，布置了 symbol.iterator 的对象才可以使用 for···of 循环，可以统一处理数据结构。调用之后回返回一个遍历器对象，包含有一个 next 方法，使用 next 方法后有两个返回值 value 和 done 分别表示函数当前执行位置的值和是否遍历完毕。

- Symbol.for() 可以在全局访问 symbol

#### Set是什么，有什么作用
- Set是ES6引入的一种类似Array的新的数据结构，Set实例的成员类似于数组item成员，区别是Set实例的成员都是唯一，不重复的。这个特性可以轻松地实现数组去重

#### Map是什么，有什么作用
- Map是ES6引入的一种类似Object的新的数据结构，Map可以理解为是Object的超集，打破了以传统键值对形式定义对象，对象的key不再局限于字符串，也可以是Object。可以更加全面的描述对象的属性

#### 介绍下Set、Map、WeakSet和WeakMap的区别
- Set——对象允许你存储任何类型的唯一值，无论是原始值或者是对象引用
- WeakSet——成员都是对象；成员都是弱引用，可以被垃圾回收机制回收，可以用来保存 DOM 节点，不容易造成内存泄漏；
- Map——本质上是键值对的集合，类似集合；可以遍历，方法很多，可以跟各种数据格式转换。
- WeakMap——只接受对象最为键名（null 除外），不接受其他类型的值作为键名；键名是弱引用，键值可以是任意的，键名所指向的对象可以被垃圾回收，此时键名是无效的；不能遍历，方法有 get、set、has、delet

- Set
  - 成员不能重复
  - 只有健值，没有健名，有点类似数组
  - 可以遍历，方法有add, delete,has

- weakSet
  - 成员都是对象
  - 成员都是弱引用，随时可以消失。 可以用来保存DOM节点，不容易造成内存泄漏
  - 不能遍历，方法有add, delete,has

- Map
  - 本质上是健值对的集合，类似集合
  - 可以遍历，方法很多，可以干跟各种数据格式转换

- weakMap
  - 直接受对象作为健名（null除外），不接受其他类型的值作为健名
  - 健名所指向的对象，不计入垃圾回收机制
  - 不能遍历，方法同get,set,has,delete

#### Proxy是什么，有什么作用
- Proxy是ES6新增的一个构造函数，可以理解为JS语言的一个代理，用来改变JS默认的一些语言行为，包括拦截默认的get/set等底层方法，使得JS的使用自由度更高，可以最大限度的满足开发者的需求。比如通过拦截对象的get/set方法，可以轻松地定制自己想要的key或者value。下面的例子可以看到，随便定义一个myOwnObj的key,都可以变成自己想要的函数`
```
function createMyOwnObj() {
	//想把所有的key都变成函数，或者Promise,或者anything
	return new Proxy({}, {
		get(target, propKey, receiver) {
			return new Promise((resolve, reject) => {
				setTimeout(() => {
					let randomBoolean = Math.random() > 0.5;
					let Message;
					if (randomBoolean) {
						Message = `你的${propKey}运气不错，成功了`;
						resolve(Message);
					} else {
						Message = `你的${propKey}运气不行，失败了`;
						reject(Message);
					}
				}, 1000);
			});
		}
	});
}

let myOwnObj = createMyOwnObj();

myOwnObj.hahaha.then(result => {
	console.log(result) //你的hahaha运气不错，成功了
}).catch(error => {
	console.log(error) //你的hahaha运气不行，失败了
})

myOwnObj.wuwuwu.then(result => {
	console.log(result) //你的wuwuwu运气不错，成功了
}).catch(error => {
	console.log(error) //你的wuwuwu运气不行，失败了
})
```

#### Reflect是什么，有什么作用
- Reflect是ES6引入的一个新的对象，他的主要作用有两点，一是将原生的一些零散分布在Object、Function或者全局函数里的方法(如apply、delete、get、set等等)，统一整合到Reflect上，这样可以更加方便更加统一的管理一些原生API。其次就是因为Proxy可以改写默认的原生API，如果一旦原生API别改写可能就找不到了，所以Reflect也可以起到备份原生API的作用，使得即使原生API被改写了之后，也可以在被改写之后的API用上默认的API

#### Promise是什么，有什么作用
- Promise是ES6引入的一个新的对象，他的主要作用是用来解决JS异步机制里，回调机制产生的“回调地狱”。它并不是什么突破性的API，只是封装了异步回调形式，使得异步回调可以写的更加优雅，可读性更高，而且可以链式调用

- 依照 Promise/A+ 的定义，Promise 有四种状态：
  - pending: 初始状态, 非 fulfilled 或 rejected.
  - fulfilled: 成功的操作.
  - rejected: 失败的操作.
  - settled: Promise已被fulfilled或rejected，且不是pending
- 另外， fulfilled 与 rejected 一起合称 settled
- Promise 对象用来进行延迟(deferred) 和异步(asynchronous ) 计算
- 可以把 Promise看成一个状态机。初始是 pending 状态，可以通过函数 resolve 和 reject，将状态转变为 resolved 或者 rejected 状态，状态一旦改变就不能再次变化。
- then 函数会返回一个 Promise 实例，并且该返回值是一个新的实例而不是之前的实例。因为 Promise 规范规定除了 pending 状态，其他状态是不可以改变的，如果返回的是一个相同实例的话，多个 then调用就失去意义了

#### Promise的构造函数
构造一个 Promise，最基本的用法如下：
```
var promise = new Promise(function(resolve, reject) {

        if (...) {  // succeed

            resolve(result);

        } else {   // fails

            reject(Error(errMessage));

        }
    });
```
- Promise 实例拥有 then 方法（具有 then 方法的对象，通常被称为thenable）。它的使用方法如下：
```
promise.then(onFulfilled, onRejected)
```
- 接收两个函数作为参数，一个在 fulfilled 的时候被调用，一个在rejected的时候被调用，接收参数就是 future，onFulfilled 对应 resolve, onRejected 对应 reject

什么是 Promise ？
- Promise 就是一个对象，用来表示并传递异步操作的最终结果
- Promise 最主要的交互方式：将回调函数传入 then 方法来获得最终结果或出错原因
- Promise 代码书写上的表现：以“链式调用”代替回调函数层层嵌套（回调地狱）

  #### promise的用法和几种状态
```
var a = Math.random()
new Promise((resolve,reject)=>{
    if(a > 0.5){
        resolve(a)
    }else{
        reject(a)
    }
}).then((val)=>{
    console.log(val)
}).catch((val)=>{
    console.log(val)
}).finally(()=>{
    console.log("不管什么状态都会执行")
})
上述代码中，promise一共三种状态，在还没有生成a的
确定值的时候，promise处于pending状态。当生成了a的值，
如果a大于0.5，运行resolve即fulfilled状态，
如果a小雨0.5运行reject()即reject状态。
其中resolve对应then，reject对象catch。
finally无论是resolve或者reject都会执行。   
```

#### Promise.all()和Promise.allSettled()的比较
Promise.allSettled()
- 接受的结果与入参时的promise实例一一对应，且结果的每一项都是一个对象，告诉你结果和值，对象内都有一个属性叫“status”，用来明确知道对应的这个promise实例的状态（fulfilled或rejected），fulfilled时，对象有value属性，rejected时有reason属性，对应两种状态的返回值。
```
const resolved = Promise.resolve(42);
const rejected = Promise.reject(-1);

const allSettledPromise = Promise.allSettled([resolved, rejected]);

allSettledPromise.then(function (results) {
  console.log(results);
});
// [
//    { status: 'fulfilled', value: 42 },
//    { status: 'rejected', reason: -1 }
// ]
```
- 重要的一点是，他不论接受入参的promise本身的状态，会返回所有promise的结果，但这一点Promise.all做不到，如果你需要知道所有入参的异步操作的所有结果，或者需要知道这些异步操作是否全部结束，应该使用promise.allSettled()

Promise.all()
- 只有当所有入参的promise实例都是fulfilled状态，才会在Promise.all().then()方法中结果，返回结果也是与入参一一对应，结果中只包含实际的resolve的结果，不包含类似allSettled的status和value属性。

#### Iterator是什么，有什么作用
- Iterator是ES6中一个很重要概念，它并不是对象，也不是任何一种数据类型。因为ES6新增了Set、Map类型，他们和Array、Object类型很像，Array、Object都是可以遍历的，但是Set、Map都不能用for循环遍历，解决这个问题有两种方案，一种是为Set、Map单独新增一个用来遍历的API，另一种是为Set、Map、Array、Object新增一个统一的遍历API，显然，第二种更好，ES6也就顺其自然的需要一种设计标准，来统一所有可遍历类型的遍历方式。Iterator正是这样一种标准。或者说是一种规范理念
- 就好像JavaScript是ECMAScript标准的一种具体实现一样，Iterator标准的具体实现是Iterator遍历器。Iterator标准规定，所有部署了key值为[Symbol.iterator]，且[Symbol.iterator]的value是标准的Iterator接口函数(标准的Iterator接口函数: 该函数必须返回一个对象，且对象中包含next方法，且执行next()能返回包含value/done属性的Iterator对象)的对象，都称之为可遍历对象，next()后返回的Iterator对象也就是Iterator遍历器
```
//obj就是可遍历的，因为它遵循了Iterator标准，且包含[Symbol.iterator]方法，方法函数也符合标准的Iterator接口规范。
//obj.[Symbol.iterator]() 就是Iterator遍历器
let obj = {
  data: [ 'hello', 'world' ],
  [Symbol.iterator]() {
    const self = this;
    let index = 0;
    return {
      next() {
        if (index < self.data.length) {
          return {
            value: self.data[index++],
            done: false
          };
        } else {
          return { value: undefined, done: true };
        }
      }
    };
  }
};
```

- ES6给Set、Map、Array、String都加上了[Symbol.iterator]方法，且[Symbol.iterator]方法函数也符合标准的Iterator接口规范，所以Set、Map、Array、String默认都是可以遍历的

```
//Array
let array = ['red', 'green', 'blue'];
array[Symbol.iterator]() //Iterator遍历器
array[Symbol.iterator]().next() //{value: "red", done: false}

//String
let string = '1122334455';
string[Symbol.iterator]() //Iterator遍历器
string[Symbol.iterator]().next() //{value: "1", done: false}

//set
let set = new Set(['red', 'green', 'blue']);
set[Symbol.iterator]() //Iterator遍历器
set[Symbol.iterator]().next() //{value: "red", done: false}

//Map
let map = new Map();
let obj= {map: 'map'};
map.set(obj, 'mapValue');
map[Symbol.iterator]().next()  {value: Array(2), done: false}
```

#### for...in和for...of有什么区别
- ES6统一了遍历标准，制定了可遍历对象，那么用什么方法去遍历呢？答案就是用for...of。ES6规定，有所部署了载了Iterator接口的对象(可遍历对象)都可以通过for...of去遍历，而for..in仅仅可以遍历对象

- 这也就意味着，数组也可以用for...of遍历，这极大地方便了数组的取值，且避免了很多程序用for..in去遍历数组的恶习

#### Generator函数是什么，有什么作用
- 如果说JavaScript是ECMAScript标准的一种具体实现、Iterator遍历器是Iterator的具体实现，那么Generator函数可以说是Iterator接口的具体实现方式。
- 执行Generator函数会返回一个遍历器对象，每一次Generator函数里面的yield都相当一次遍历器对象的next()方法，并且可以通过next(value)方法传入自定义的value,来改变Generator函数的行为。
- Generator函数可以通过配合Thunk 函数更轻松更优雅的实现异步编程和控制流管理。

generator 原理
- Generator 是 ES6中新增的语法，和 Promise 一样，都可以用来异步编程
```
// 使用 * 表示这是一个 Generator 函数
// 内部可以通过 yield 暂停代码
// 通过调用 next 恢复执行
function* test() {
  let a = 1 + 2;
  yield 2;
  yield 3;
}
let b = test();
console.log(b.next()); // >  { value: 2, done: false }
console.log(b.next()); // >  { value: 3, done: false }
console.log(b.next()); // >  { value: undefined, done: true }
```
- 从以上代码可以发现，加上 *的函数执行后拥有了 next 函数，也就是说函数执行后返回了一个对象。每次调用 next 函数可以继续执行被暂停的代码。以下是 Generator 函数的简单实现
```
// cb 也就是编译过的 test 函数
function generator(cb) {
  return (function() {
    var object = {
      next: 0,
      stop: function() {}
    };

    return {
      next: function() {
        var ret = cb(object);
        if (ret === undefined) return { value: undefined, done: true };
        return {
          value: ret,
          done: false
        };
      }
    };
  })();
}
// 如果你使用 babel 编译后可以发现 test 函数变成了这样
function test() {
  var a;
  return generator(function(_context) {
    while (1) {
      switch ((_context.prev = _context.next)) {
        // 可以发现通过 yield 将代码分割成几块
        // 每次执行 next 函数就执行一块代码
        // 并且表明下次需要执行哪块代码
        case 0:
          a = 1 + 2;
          _context.next = 4;
          return 2;
        case 4:
          _context.next = 6;
          return 3;
		// 执行完毕
        case 6:
        case "end":
          return _context.stop();
      }
    }
  });
}
```

Generator 实现
- Generator 是 ES6中新增的语法，和 Promise 一样，都可以用来异步编程
```
// 使用 * 表示这是一个 Generator 函数
// 内部可以通过 yield 暂停代码
// 通过调用 next 恢复执行
function* test() {
  let a = 1 + 2;
  yield 2;
  yield 3;
}
let b = test();
console.log(b.next()); // >  { value: 2, done: false }
console.log(b.next()); // >  { value: 3, done: false }
console.log(b.next()); // >  { value: undefined, done: true }
从以上代码可以发现，加上 * 的函数执行后拥有了 next函数，也就是说函数执行后返回了一个对象。每次调用 next函数可以继续执行被暂停的代码。以下是 Generator 函数的简单实现

// cb 也就是编译过的 test 函数
function generator(cb) {
  return (function() {
    var object = {
      next: 0,
      stop: function() {}
    };

    return {
      next: function() {
        var ret = cb(object);
        if (ret === undefined) return { value: undefined, done: true };
        return {
          value: ret,
          done: false
        };
      }
    };
  })();
}
// 如果你使用 babel 编译后可以发现 test 函数变成了这样
function test() {
  var a;
  return generator(function(_context) {
    while (1) {
      switch ((_context.prev = _context.next)) {
        // 可以发现通过 yield 将代码分割成几块
        // 每次执行 next 函数就执行一块代码
        // 并且表明下次需要执行哪块代码
        case 0:
          a = 1 + 2;
          _context.next = 4;
          return 2;
        case 4:
          _context.next = 6;
          return 3;
		// 执行完毕
        case 6:
        case "end":
          return _context.stop();
      }
    }
  });
}
```

#### async函数是什么，有什么作用
- async函数可以理解为内置自动执行器的Generator函数语法糖，它配合ES6的Promise近乎完美的实现了异步编程解决方案

async、await 优缺点
- async 和 await 相比直接使用 Promise 来说，优势在于处理 then 的调用链，能够更清晰准确的写出代码。缺点在于滥用 await 可能会导致性能问题，因为 await 会阻塞代码，也许之后的异步代码并不依赖于前者，但仍然需要等待前者完成，导致代码失去了并发性

下面来看一个使用 await 的代码。
```
var a = 0
var b = async () => {
  a = a + await 10
  console.log('2', a) // -> '2' 10
  a = (await 10) + a
  console.log('3', a) // -> '3' 20
}
b()
a++
console.log('1', a) // -> '1' 1
```
- 首先函数b 先执行，在执行到 await 10 之前变量 a 还是 0，因为在 await 内部实现了 generators ，generators 会保留堆栈中东西，所以这时候 a = 0 被保存了下来
- 因为 await 是异步操作，遇到await就会立即返回一个pending状态的Promise对象，暂时返回执行代码的控制权，使得函数外的代码得以继续执行，所以会先执行 console.log('1', a)
- 这时候同步代码执行完毕，开始执行异步代码，将保存下来的值拿出来使用，这时候 a = 10
- 然后后面就是常规执行代码了

#### Class、extends是什么，有什么作用
- ES6 的class可以看作只是一个ES5生成实例对象的构造函数的语法糖。它参考了java语言，定义了一个类的概念，让对象原型写法更加清晰，对象实例化更像是一种面向对象编程。Class类可以通过extends实现继承。它和ES5构造函数的不同点

类的内部定义的所有方法，都是不可枚举的
```
///ES5
function ES5Fun (x, y) {
	this.x = x;
	this.y = y;
}
ES5Fun.prototype.toString = function () {
	 return '(' + this.x + ', ' + this.y + ')';
}
var p = new ES5Fun(1, 3);
p.toString();
Object.keys(ES5Fun.prototype); //['toString']

//ES6
class ES6Fun {
	constructor (x, y) {
		this.x = x;
		this.y = y;
	}
	toString () {
		return '(' + this.x + ', ' + this.y + ')';
	}
}

Object.keys(ES6Fun.prototype); //[]
```
- ES6的class类必须用new命令操作，而ES5的构造函数不用new也可以执行。
- ES6的class类不存在变量提升，必须先定义class之后才能实例化，不像ES5中可以将构造函数写在实例化之后。
- ES5 的继承，实质是先创造子类的实例对象this，然后再将父类的方法添加到this上面。ES6 的继承机制完全不同，实质是先将父类实例对象的属性和方法，加到this上面（所以必须先调用super方法），然后再用子类的构造函数修改this。

#### module、export、import是什么，有什么作用
- module、export、import是ES6用来统一前端模块化方案的设计思路和实现方案。export、import的出现统一了前端模块化的实现方案，整合规范了浏览器/服务端的模块化方法，用来取代传统的AMD/CMD、requireJS、seaJS、commondJS等等一系列前端模块不同的实现方案，使前端模块化更加统一规范，JS也能更加能实现大型的应用程序开发。
- import引入的模块是静态加载（编译阶段加载）而不是动态加载（运行时加载）。
- import引入export导出的接口值是动态绑定关系，即通过该接口，可以取到模块内部实时的值

#### 日常前端代码开发中，有哪些值得用ES6去改进的编程优化或者规范
- 常用箭头函数来取代var self = this;的做法。
- 常用let取代var命令。
- 常用数组/对象的结构赋值来命名变量，结构更清晰，语义更明确，可读性更好。
- 在长字符串多变量组合场合，用模板字符串来取代字符串累加，能取得更好地效果和阅读体验。
- 用Class类取代传统的构造函数，来生成实例化对象。
- 在大型应用开发中，要保持module模块化开发思维，分清模块之间的关系，- 常用import、export方法。

#### es6模块化
在有 Babel 的情况下，我们可以直接使用 ES6的模块化
```
// file a.js
export function a() {}
export function b() {}
// file b.js
export default function() {}

import {a, b} from './a.js'
import XXX from './b.js'
```
CommonJS
- CommonJs 是 Node 独有的规范，浏览器中使用就需要用到 Browserify解析了。
```
// a.js
module.exports = {
    a: 1
}
// or
exports.a = 1

// b.js
var module = require('./a.js')
module.a // -> log 1
```
- 在上述代码中，module.exports 和 exports 很容易混淆，让我们来看看大致内部实现
```
var module = require('./a.js')
module.a
// 这里其实就是包装了一层立即执行函数，这样就不会污染全局变量了，
// 重要的是 module 这里，module 是 Node 独有的一个变量
module.exports = {
    a: 1
}
// 基本实现
var module = {
  exports: {} // exports 就是个空对象
}
// 这个是为什么 exports 和 module.exports 用法相似的原因
var exports = module.exports
var load = function (module) {
    // 导出的东西
    var a = 1
    module.exports = a
    return module.exports
};
```
- 再来说说 module.exports 和exports，用法其实是相似的，但是不能对 exports 直接赋值，不会有任何效果。

- 对于 CommonJS 和 ES6 中的模块化的两者区别是：
  - 前者支持动态导入，也就是 require(${path}/xx.js)，后者目前不支持，但是已有提案,前者是同步导入，因为用于服务端，文件都在本地，同步导入即使卡住主线程影响也不大。
  - 而后者是异步导入，因为用于浏览器，需要下载文件，如果也采用同步导入会对渲染有很大影响
  - 前者在导出时都是值拷贝，就算导出的值变了，导入的值也不会改变，所以如果想更新值，必须重新导入一次。
  - 但是后者采用实时绑定的方式，导入导出的值都指向同一个内存地址，所以导入值会跟随导出值变化
  - 后者会编译成 require/exports 来执行的

AMD
- AMD 是由 RequireJS 提出的
```
// AMD
define(['./a', './b'], function(a, b) {
    a.do()
    b.do()
})
define(function(require, exports, module) {   
    var a = require('./a')  
    a.doSomething()   
    var b = require('./b')
    b.doSomething()
})
```

#### ES5/ES6的继承除了写法以外还有什么区别
- ES5 的继承实质上是先创建子类的实例对象，然后再将父类的方法添加到 this 上（Parent.apply(this)）
- ES6 的继承机制完全不同，实质上是先创建父类的实例对象 this（所以必须先调用父类的 super()方法），然后再用子类的构造函数修改 this。
- ES5 的继承时通过原型或构造函数机制来实现。
- ES6 通过 class 关键字定义类，里面有构造方法，类之间通过 extends 关键字实现继承。
- 子类必须在 constructor 方法中调用 super 方法，否则新建实例报错。因为子类没有自己的 this 对象，而是继承了父类的 this 对象，然后对其进行加工。如果不调用 super 方法，子类得不到 this 对象。
- 注意 super 关键字指代父类的实例，即父类的 this 对象。
- 注意：在子类构造函数中，调用 super 后，才可使用 this 关键字，否则报错。function 声明会提升，但不会初始化赋值。Foo 进入暂时性死区，类似于 let、const 声明变量








