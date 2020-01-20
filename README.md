# 前端面试题目整理

2020 春节训练营
## 一. Vue 中v-if和v-for哪个优先级高？如果两个同时出现，应该怎么优化得到更好的性能？

当 v-if 与 v-for 同时作用于同一个节点时， v-for 的优先级更高。<br>
v-if和v-for在模版编译后会执行函数 `_l`（渲染列表，即renderList），第一个参数为数组arr，
第二个参数为函数，函数返回值即 v-if 产生的三目运算。参数为v-for遍历的参数<br>
格式如下： `_l((arr),function(e,i){return (arr.length)?_c(...):_e(), 0})`

v-if和v-for同时存在一般有两种情形，第一种是对列表项的值过滤，第二种是判断列表隐藏/显示<br>
第二种情形可以在外层加标签判断v-if，就能避免对每一项检查，代码逻辑也更明确<br>
第一种情形可以使用计算属性对数组进行过滤，使用过滤后的数组直接遍历


