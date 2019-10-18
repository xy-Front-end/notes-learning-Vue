# Vue

# 学习重点目标

- Vue组件
- Vue CLI
- Vue route
- Vuex
- Vue网络封装

# 疑问

1. 使用Vue是不是要先定义文档的结构和表现？然后才能填充数据？Vue充其量也就做个填充数据用的？无法操作DOM？如何进行DOM的CRUD操作？
2. 是不是要写死HTML结构？
3. 每个操作的模块都要使用到选择器，不同的模块如何交互？
4. 

# 经验

1. 调用变量值：标签内使用{{变量名}}，v-html，v-text等属性使用变量值则用：v-text="变量名"

# Vue对象

## 属性

### el

### data

### methods

### computed

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
6. v-cloak，应用场景：js加载慢的时候，dom显示不友好

## 2，绑定属性

### v-bind，有语法糖

- 对象语法

  绑定style

  绑定class

- 数组语法

  绑定style

  绑定class

## 3，计算属性

