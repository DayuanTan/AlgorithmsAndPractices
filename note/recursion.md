

[More about stack and heap and stackoverflow 更多关于栈、堆和溢出](recursion_stackheap_more.md)

# 3. 值传递与引用传递 Pass by value vs Pass by reference 

## 函数调用时值的传递：

- Java 值传递, 引⽤传递

- C++ 值传递, 引⽤传递, 地址传递

- Python 值传递, 引⽤传递

## 值传递：
- “盗梦空间” 中, 下层梦境中的⼈的⽣死与上层梦境⽆关

- 创建⼀个新的变量, 把值拷⻉ —— 相当于⼀个副本
```java
void func(int x){
	x ++;
	print(x);
}
int x=0;
func(x);
print(x);
```

- Java 基本数据类型 (byte, short, int, long, float, double, char, boolean)

- C++ 默认值传递

- Python 值类型 (类似于 Java)

- Java 类成员中, 若有 final 修饰, 可以认为具有值传递的特性

## 引用传递

- Java 类的实例

- C++ 在参数列表中加 & 修饰

- Python 引⽤类型 (类似于 Java, ⽐如列表, 类的实例)

- Java 类成员中, 若有 final 修饰, 可以认为是值传递

|值传递|引用传递|
|-|-|
|Java 基本数据类型 (byte, short, int, long, float, double, char, boolean)|Java 类的实例|
|C++ 默认值传递|C++ 在参数列表中加 & 修饰|
|Python 值类型 (类似于 Java)|Python 引⽤类型 (类似于 Java, ⽐如列表, 类的实例)|
|Java 类成员中, 若有 final 修饰, 可以认为具有值传递的特性||
||

## 递归与值传递/引⽤传递的关系

- 值传递和引⽤传递的主要区别: 内容是否复制

  - 空间占⽤ / 时间消耗

  - 修改是否影响上⼀层

- 递归要在保证正确性的前提下, 尽可能提⾼效率

- 需要考虑不仅仅参数传递, 还有返回值



# 4. 递归和tree, binary search 二分法递归版本


# Binary Tree

## Traversal
- Binary Tree Inorder Traversal
- Binary Tree Preorder Traversal
- Binary Tree Postorder Traversal

### 确定⼀棵⼆叉树
- 三种遍历序列, 其中⼀个相同, ⼆叉树不⼀定相同
  - 中序序列相同, 前序序列相同, ⼆叉树相同
  - 中序序列相同, 后序序列相同, ⼆叉树相同
  - 由⼆叉树的中序序列再加上前/后序序列之⼀即可确定⼀棵⼆叉树 (⽆重复节点)



# 其他题目 记得做呀！


251类似题目 以后联系

Flatten Nested List Iterator
https://leetcode-cn.com/problems/flatten-nested-list-iterator/

Flatten Binary Tree to Linked List
https://leetcode-cn.com/problems/flatten-binary-tree-to-linked-list/




这里继续

Flatten list 列表扁平化
[22.Flatten list 列表扁平化 2解法](../lintcode/22.flatten_list.md)




这里继续



  


---
还没做:


Hard [94. 124. Binary Tree Maximum Path Sum](9chapters/lintcode/94.124.md) 

---

551
1.   Nested List Weight Sum

Judge: https://www.lintcode.com/problem/nested-list-weight-sum/description

Solution: https://www.jiuzhang.com/solution/nested-list-weight-sum/

1.    Convert Sorted Array to Binary Search Tree

Judge: https://www.lintcode.com/problem/convert-sorted-array-to-binary-search-tree/description

Solution: https://www.jiuzhang.com/solution/convert-sorted-array-to-binary-search-tree/

coding...

1.    Maximum Binary Tree

Judge: https://www.lintcode.com/problem/maximum-binary-tree/description

Solution: https://www.jiuzhang.com/solution/maximum-binary-tree/

coding...

1.   Same Tree

Judge: https://www.lintcode.com/problem/same-tree/description

Solution: https://www.jiuzhang.com/solution/same-tree/

coding...


1.   Tweaked Identical Binary Tree

Judge: https://www.lintcode.com/problem/tweaked-identical-binary-tree/description

Solution: https://www.jiuzhang.com/solution/tweaked-identical-binary-tree/

coding...

1.   Tower of Hanoi

Judge: https://www.lintcode.com/problem/tower-of-hanoi/description

Solution: https://www.jiuzhang.com/solution/tower-of-hanoi/

coding...

