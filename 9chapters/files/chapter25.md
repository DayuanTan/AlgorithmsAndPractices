今天我们一起来学习『背包型动态规划入门』

在这一章中，我们就要来学习背包了，这一节课我们会讲到01背包与多重背包两种类型，其中01背包就是，每种物品只有一个的背包。而多重背包就是每种物品有几个，你可以选择其中的任意个放入背包。那么我们先来看看01背包问题的解法吧。

第二十五章【互动】背包型动态规划入门 1 01背包问题及实现

数据是否需要从小到大排序？
- A:
需要
- B:
不需要

在这里数据的先后顺序是没有关系的，就像你有一个苹果一个橙子，只要背包够大，先放苹果和先放橙子都能把这两个物品装进去。

正确答案是 B


我们刚才说，01背包还有另外一种状态方程的表示方法，我们也顺便一起来看一下吧。

第二十五章【互动】背包型动态规划入门 2 另一种01背包的实现方法

同时我们也会发现动态规划的时间复杂度是多项式级别的，而如果用我们之前学的深度优先搜索去做，时间复杂度是指数级别的，那么是不是动态规划一定比搜索要好呢？一起来看一下吧


第二十五章【互动】背包型动态规划入门 3 背包问题用动归还是搜索


总而言之，只有在m>>2^n的时候，动态规划才弱于搜索，所以大部分情况下，动态规划都是一个最优的选择。那么接下来我们就来看一下01背包的几种题型吧。


第二十五章【互动】背包型动态规划入门 4 01背包的三种变形题
第二十五章【互动】背包型动态规划入门 5 带价值的01背包

接下来，我们再来看一下一个01背包的变型版本，给定物品数量的背包——多重背包。

第二十五章【互动】背包型动态规划入门 6 多重背包及小结

那么以上就是背包型动态规划的所有内容了，我们可以做几道题来复习一下今天的内容哦

https://www.lintcode.com/problem/backpack/description

https://www.lintcode.com/problem/backpack-ii/description

https://www.lintcode.com/problem/backpack-v/description

