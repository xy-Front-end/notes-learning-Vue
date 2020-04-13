# Vue

参考视频：https://www.bilibili.com/video/BV15741177Eh

# 学习重点目标

## Vue组件

## Vue CLI

## Vue route

## Vuex

## Vue网络封装

# 疑问

1. 使用Vue是不是要先定义文档的结构和表现？然后才能填充数据？Vue充其量也就做个填充数据用的？无法操作DOM？如何进行DOM的CRUD操作？
2. 是不是要写死HTML结构？
3. 每个操作的模块都要使用到选择器，不同的模块如何交互？
4. computed计算属性与methods的对比，相同功能建议使用computed，因为只调用一次
5. 方法什么时候加（），什么时候不加？
6. 登录切换，input复用问题，只要key不一样才不会复用
7. v-if与v-show如何选择？
8. Vue只能操作Js，无法做到Bootstrap那样操作CSS+UI？
9. 命令式编程与声明式编程的区别
10. Vue如何像ajax那样与服务器进行数据的交互
11. 为什么组件的data是一个function？关键：对象的内存 。
12. JS模块化之后，如果只是部分模块化，是否还会冲突？
13. 

# 经验

1. 调用变量值：标签内使用{{变量名}}，v-html，v-text等属性使用变量值则用：v-text="变量名"
2. 标签中的方法调用，如果实参是常量，需要加上双引号，否则会被Vue当成变量到data中查找。



# 案例

1. 购物车小案例

# ES6补充

1. var&let

   var没有块级作用域，定义的变量容易引起脏读，而let有明确的作用域。

   注意：

   1. ES5函数function(){}有自己的作用域，而if、for没有自己的块作用域，所以很多时候都是使用function解决（也就是闭包）。

2. const

   不能被修改，必须初始化，指向的对象不能被修改，类似Java的final，引用不可变。

3. 对象的增强写法

   

4. 1

# Vue对象

## 属性

### el

### data

### methods

### computed

### components，注册组件

# 1，了解Vue

## 渐进式开发

比如在重构中，使用Vue逐步代替其他技术，代替之前可以共存。

## Vue option

el:

data:

methods:

computed：计算属性

## Vue 生命周期

。。。。。

# 2，基础语法

## 1，插值语法

1. Mustache，双大括号语法，{{变量名}}，中文翻译胡须，最重要的，下面的基础
2. v-text
3. v-html
4. v-pre
5. v-once
6. v-cloak，应用场景：js加载慢的时候，变量名显示不友好，需要结合style

## 2，绑定属性

### v-bind，有语法糖

- 对象语法

  绑定style

  绑定class

- 数组语法

  绑定style

  绑定class

- 绑定基本属性

目前不支持驼峰

## 3，计算属性

### computed

## 4，事件监听

### v-on

#### 使用

- 方法中如果没有形式参数，则可以在调用中省略括号。
- 如果方法中有一个形参，调用中不写括号，则方法中的形参默认为事件Event。专业的说法是Vue会将浏览器生成的事件Event作为形参传入，作为第一个参数。
- 实参中要有Event，形参中也有Event，则实参中的事件Event应该这样写:$event。

#### 修饰符

- stop：@click.stop="xxx"，阻止冒泡。
- prevent：@click.prevent="stopSubmit"，例如阻止表单的默认点击按钮自动提交
- 

## 5，条件判断

### 1，if else

如果是false不会出现在DOM树中，如果改为true，会重新创造DOM节点

- v-if
- v-else-if
- v-else

### 2，v-show

false只是把元素的display设置为none，但是依然存在DOM树中。





## 6，循环遍历

### 1，v-for

- 遍历数组

  - 不使用下标索引：v-for="itme in vars"
  - 使用下标索引：v-for="(item,index) in vars"

- 遍历对象

  - v-for="(value,key,index) in obj"，值在前

  官方推荐使用的时候，在元素内添加key属性，为了更好的复用

## 7，表单绑定

### v-model

双向绑定，js->html，html->js。

### v-radio

### v-model checkbox

### v-model select

# 3，组件化

**必须在new Vue()之前注册**

使用组件，必须是在全局或者局部中注册过的

使用组件步骤：

1. 创建组件构造器，在js中
2. 注册组件，在js中
3. 使用组件，在html中

## 全局组件

可以让多个Vue实例共同使用的。

Vue.component("my-cpn",组件构造器)，这种就是全局组件

## 局部组件

实际使用较多。

在Vue实例内注册的

## 父组件&子组件

父组件可以使用子组件的内容，父组件可以注册为全局、局部组件。子组件在父组件的compnents属性中注册。

最顶层的组件是Vue，可以认为是root组件。

子组件无法**直接**使用父组件/Vue实例的数据。

## 父子组件的数据通信

基本都是大组件与服务器进行通信，然后把数据传输给小组件，小组件进行数据的展示。

### 单向：

方式：

- props：父传给子

  字符串数组

  对象

  坑：子组件用驼峰，模板html调用的时候用横线分割

- 事件：子传给父

  例如：子组件被点击了，需要告诉父组件，子组件被点击了哪里，然后父组件向服务器请求数据。

  子组件发送事件：this.$emit("click-item",data)

  父组件监听事件：@click-item="itemfunction"

### 双向：

核心：v-modal实现原理

方法1

1. 父传子
2. 子监听，然后传给父

方法2:

wacht

## 父子组件相互访问属性

比如方法，对象。

### 父组件访问子组件

- $children，多个
- $ref，单个

### 子组件访问父组件

$parent

一般不建议使用。因为这样耦合性太高，就打破了子组件的独立、复用！

## 插槽slot

组件一个插槽对应html一个标签，但是如果组件多个插槽，html一个标签，则多个插槽都会被替换为该标签。

### 具名插槽

具体的一个插槽对应一个HTML标签

### 编译作用域

父组件模板都会在父级作用域编译，子组件都会在子组件作用域编译，无法做到跨域访问。

# 4，模块化

## AMD/CMD/CommonJS

浏览器不支持，需要webpack支持

## ES6 modules

### 导出

export 变量

export函数&类

export default，一个js文件只能有一个，可以供import自定义命名

### 导入

import {变量，函数，类} from "js文件"

## webpack

依赖Node.js，需要安装Node.js

核心：现代js应用的模块打包工具。可以打包js，图片，css，模块化。

webpack.config.js

语法：

### 处理js

```javas
const path=require("path");//用到Node.js npm相关环境配置
module.export={
  entry:"./src/main.js",
  output:{
    path:path.resolve(__dirname,"dist"),//绝对路劲
    name:"bundle.js"
  }
}
```

项目中一般使用局部webpack

###   处理css

需要loader，分为style-loader，css-loader

module配置易错：loder是从右边到左边加载

### 处理less



### 处理图片

最重要的URL有可能需要配置publicPath:"dist/"

### 处理ES6->ES5

webpack把es6写法转为es5

使用label

### webpack配置vue



