# 1 Memoization  Search

## 记忆化搜索Memoization Search
- 使用HashMap/Dict记录搜索的中间结果从而避免重复计算的算法
- 将函数的计算结果保存起来，下次通过同样的参数访问时，直接返回保存下来的结果
- 将指数级别的时间复杂度降到多项式级别 O(2^n) to O(n^2)


因为我们已经以一种方式（HashMap）记录了所有路径。所以每一对x和y只出现了一次，也就是 n^2 级别，相当于每一对起点终点都计算了一次，也就是 O(n^2) 。


## 对这个函数的限制？
- 函数需要有参数和返回值，没有则无法hashmap （DC中的返回值那样）
- 函数需要时pure function，即结果只和传入参数有关和其他无关
- 和系统设计中的cache很像

## 记忆化搜索-本质：动态规划
动态规划 和分治 的区别： 重复计算 （triangle中有重复部分，和binary tree不一样）
- 分完之后左右部分有交集=》动态规划
- 分完之后左右部分没有交集=》分治法

## 记忆化搜索是动态规划的一种 实现方式
搜索实现方式 ：
- BFS
- DFS 
  - Recursion
  - Stack/non-recursion
  
动态规划实现方式：
- Memoization search
- non-recursion/for loop  
 

