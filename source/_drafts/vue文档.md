---
title: vue文档
date: 2017-11-20 21:45:30
tags: vue
---

## 计算属性和method的区别
计算属性是基于他们的依赖缓存的,计算属性只有在它依赖发生变化时才会重新求值;
定义在方法里面,每次渲染都会重新执行该函数;

为什么要使用缓存,举个例子,假设说有个性能开销比较大的计算属性A,他需要遍历一个巨大的数组并做大量的计算.然后我们可能有其他的计算属性依赖,如果没有缓存,我们将不可避免的多次执行A的setter,如果不希望使用缓存,请用方法来代替

## watch和计算属性的区别
两者使用的场景不一样
当你有一些数据需要随着其他数据变动而变动的,这种情况,很容易滥用watch,通常更好的方法是使用计算属性而不是命令式的watch回调:
watch是监听到某个数据的变化后做一些事情;
计算属性是一些数据随着其他数据变化而变化;