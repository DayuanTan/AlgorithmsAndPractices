This repo is about my notes and a record of my practicing of algorithms on Leetcode/lintcode. 

(It is wrote mainly in English and barely Chinese. Ignoring the Chinese parts doens't affect the understanding of this repo.)    

# 0. Before Starting

## Recommended Steps:
1. Read through this whole README.md. Get fimilar with "Theory" subsection of each section. No need to dive into those linked files.
2. Go through those problems marked with "❗️".
3. Go through left problems.

## Steps for all questions

1. Clarification. Confirm questions with interviewer, including input, output, examples; discuss about corner cases examples.
2. Think out loud. Describe your idea/thoughts before coding. Talk before write.
3. Point out your assumption. Like arguments/inputs are in memory, are they sorted already or not.
4. Talk through. Write your code while explaining it.
5. Introduce your tests and run tests and error handling. Test in real time, use examples given, then edge cases. 
6. Time and space complexity analysis. Scale analysis.
7. Optimal solution or follow up.

## Data structure

- Underlying storage methods: only array (sequential storage) and linked list (chain storage). 
- VS
- Operations: traversing and accessing. More specifically, add, delete, search, alter. 
- Must-master data structures:
  - Arrays, Linked list, Stacks, Queues, Sets, Maps, Binary tress, Heaps, Graphs ([Google Code Interview 2:38](https://www.youtube.com/watch?v=6ZZX9iIgFoo))    


## Algorithms 
- Must-master algorithms: ([Google Code Interview 3:04](https://www.youtube.com/watch?v=6ZZX9iIgFoo)) 
  - Sorting, searching, binary searching
  - Divide and conquer
  - Dynamic programming and memorizaiton
  - Greedy algorithms
  - Recursion
  - Graph traversal, breadth- depth-first  

- Algorithms with Time complexity O(n):
  - 考得频率Test freq.: 2 pointers (without sort) >> 打擂台算法 ~= 单调栈算法 ~= 单调队列算法

# 1. Two Pointers Method (most frequent) - O(n)

## Theory:

1. Face to Face Two Pointers 相向双指针 (**most frequently asked**) 
   - Two Sum type
     - sum of two numbers. 
     - sum of three numbers. 
   - Reverse type     
     - 判断回文串 palindrome. 
     - 翻转字符串 flip string. 
   - Partition type
     - quick sort. 
     - color sort.
2. Back to Back Two Pointers 背向双指针 (only below 3 tyeps:)
   - Longest Palindromic Substring 最长回文子串 - 中心线枚举算法
   - Find K closet elements (also in binary search)
   - Square of sorted array
3. Same Direction Two Pointers 同向双指针  
   - Sliding Window 滑动窗口类
   - Fast & Slow pointers 快慢指针类 




||Time Complexity|Space Complexity|
|-|-|-|
|Use hashmap| O(n)|O(n)|
|Use [sort O(nlogn)+] 2 pointers O(n)|O(nlogn)|O(1)|



  
## Practice:

1. Face to Face Two Pointers 相向双指针 (**most frequently asked**)
   - Two Sum type
     - sum of two numbers.  
       - ❗️Easy [1. Two Sum](leetcode/1.twosum.md) (2 pointer base - O(nlogn), hashmap O(n)); **2pointers template**
       - ❗️Easy [170. Two Sum III - Data structure design](leetcode/170.Two_Sum_III-Data_structure_design.md)
       - ❗️[Two sum note, 2 pointers VS hashmap](note/twosumnote.md)
       - Easy [167. Two Sum II - Input array is sorted](leetcode/167.Two_Sum_II_Input_array_is_sorted.md);  
       - Easy [1099. Two Sum - Less than or equal to target](leetcode/1099.Two_Sum_Less_than_or_equal_to_target.md) 
       - Medium [611. Valid Triangle Number](leetcode/611.Valid_Triangle_Number.md) 
       - [Note ask for plan combinations and plans count 求具体方案和方案个数](note/plancombinations_and_plans_count.md)
     - sum of three numbers. 
       - Medium [15. 3 Sum](leetcode/15.3sum.md)
       - Medium [18. 4 sum](leetcode/18.4sum.md), same array, ask for plan combinations
       - Medium [454. 4sum_II.md](leetcode/454.4sum_II.md), 1 arrays, ask for plans count. Barely meet. 折半搜索. O(n^k) -> O(n^(k/2))
       - Hard [i89. K sum](leetcode/i89.ksum.md) DFS DP 抽空练习
   - Reverse type     
     - palindrome 判断回文串. 
       - Easy [125. Valid Palindrome (corner cases, help func)](leetcode/125.Valid_Palindrome.md) 
       - Easy [680. Valid Palindrome II (repeated code)](leetcode/680.Valid_Palindrome_II.md) 
     - flip string 翻转字符串. 
   - Partition type (**Must partition if ask for no extra mem**)
     - quick sort. 
       - ❗️[Quick sort merge sort quick select note](note/quick_sort_merge_sort_note.md)  **Partition template**
       - ❗️Medium [912. Sort an Array (quick & merge sort)](leetcode/912.sort_an_array.md)
       - merge sort. Easy [88. Merge Sorted Array](leetcode/88.Merge_Sorted_Array.md)
       - Hard [493. Reverse Pairs](leetcode/493.Reverse_Pairs.md) MS 抽空练习
       - Medium [i144. Interleaving Positive and Negative Numbers](leetcode/i144.Interleaving_Positive_and_Negative_Numbers.md)
       - Easy [i373. Partition Array by Odd and Even](leetcode/i373.Partition_Array_by_Odd_and_Even.md)
       - Medium [i49. Sort Letters by Case](leetcode/i49.Sort_Letters_by_Case.md)
     - quick select
       - ❗️Medium [215. Kth Largest Element in an Array](leetcode/215.Kth_Largest_Element_in_an_Array.md) sort/partition/priority queue/heap
       - Easy [703. Kth Largest Element in a Stream](leetcode/703.Kth_Largest_Element_in_a_Stream.md) 抽空练习
       - Medium [1985. Find the Kth Largest Integer in the Array](leetcode/1985.Find_the_Kth_Largest_Integer_in_the_Array.md) 抽空练习
     - color sort  
       - ❗️Medium [75. sort colors](leetcode/75.sort_colors.md) O(n)
       - Medium [i143. rainbow sort, k-colors sort](leetcode/i143.rainbow_sort_kcolors_sort.md) O(nlogk) 抽空练习
       - Easy 
       - Hard [295. Find Median from Data Stream](leetcode/295.Find_Median_from_Data_Stream.md) 抽空练习
2. Back to Back Two Pointers 背向双指针 (only below 3 tyeps:)
   - Longest Palindromic Substring 最长回文子串 - 中心线枚举算法
   - Find K closet elements (also in binary search)
   - Square of sorted array
3. Same Direction Two Pointers 同向双指针  
   - Sliding Window 滑动窗口类
   - Fast & Slow pointers 快慢指针类 
     - Easy [283. Move zeroes](leetcode/283.move_zeroes.md)




# 2. Recursion, Heap and Stack (Hardware), Tree 整理中

## Theory:


## 2.1 Recursion 3 key elementts:
  - Definition, Stopping Condition, Divide. 递归的定义，出口，拆解。

## 2.2 Heap, stack and overflow

### Stack and Heap in Memory 内存中的堆栈 



||Heap:| Stack:|
|-|-|-|
|Store what?|store the object got by "new" |  store the reference to object, variables, arrays, function calls|
|Size|No limit. All left mem space.|Limited. Usually as small as few MB. (Stack Overflow, Segment Fault if recursion depth is big)|
||

 
### Stack overflow

- Java: About 18615 recursion delpth. 
- C/C++: About 262009 recursion delpth. 
- Python: About 998 recursion delpth. Not stackoverflow. But “RuntimeError: maximum recursion depth exceeded” which is a setting.

## 2.3 Pass by value vs Pass by reference  值传递与引用传递 

||Pass by value|Pass by reference|
|-|-|-|
|Java|Java Primitive Data Types (byte, short, int, long, float, double, char, boolean)|Java Class Instances|
||Those class elements with 'final'.||
|Python|Python Value types. Similar to Java|Python Reference types. Similar to Java|
|C++|Default|Parameters with '&'|



## 2.4 Recursion with Tree, Binary Search递归版本

- Binary Tree 
  - Inorder Traversal
  - Preorder Traversal
  - Postorder Traversal
- Construct binary tree from 2 traversals
  - from Inorder and (Preorder or Postorder Traversal)


[Note recursion (more details inside if needed)](note/recursion.md) 

## Practice:



- ❗️Easy [509. Fibonacci, O(2^n) -> O(n)](leetcode/509.Fibonacci.md)  Recursion, Memorized Search, Rolling Array  
  - Easy [i771. Double Factorial](leetcode/i771.Double_Factorial.md) 
  - Easy [190. Reverse Bits](leetcode/190.Reverse_Bits.md) 抽空练习
  - Easy   [206. Reverse Linked List](leetcode/206.Reverse_linked_list.md) 
  - Easy [104. Maximum Depth of Binary Tree](leetcode/104.Maximum_Depth_of_Binary_Tree.md)
  - Easy [704. Classical Binary Search](leetcode/704.Classical_Binary_Search.md)
  - Medium [251. Flatten 2D Vector](leetcode/251.Flatten_2D_Vector.md)
- ❗️Easy [94. Binary Tree Inorder Traversal](leetcode/94.Binary_Tree_Inorder_Traversal.md) Recursion/Stack
  - Easy [144. Binary Tree Preorder Traversal](leetcode/144.Binary_Tree_Preorder_Traversal.md) 
  - Easy [145. Binary Tree Postorder Traversal](leetcode/145.Binary_Tree_Postorder_Traversal.md)
- ❗️Medium [106. Construct Binary Tree from Inorder and Postorder Traversal](leetcode/106.Construct_Binary_Tree_from_Inorder_and_Postorder_Traversal.md)  
  - Medium [105. Construct Binary Tree from Preorder and Inorder Traversal](leetcode/105.Construct_Binary_Tree_from_Preorder_and_Inorder_Traversal.md)   |

Medium [1593/889. Construct Binary Tree from Preorder and Postorder Traversal](../lintcode/1593.889.md) 


Medium [none/1008. Construct Binary Search Tree from Preorder Traversal](../lintcode/none.1008.md)



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
Medium [376 · Binary Tree Path Sum 113. Path Sum II](9chapters/lintcode/376.113.md) 

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



# 9. Dynamic Programming - Memoization 记忆化搜索 动态规划

## Theory:
## 9.1 DFS-Traverse -> DC -> DC-with-Hashmap/Memoization Search

- ❗️Easy [120 Triangle](120.triangle.md) 
  - DFS-Traverse O(2^n), 
  - Divide & Conquer O(2^n), 
  - DC-with-Hashmap/Memoization Search O(n^2)
  - 以后还待加上DP

- Memoization Search 记忆化搜索
  - Use Hashmap/Dict to record intermidiate results of searching process, to avoid repeated calculation
  - Record the result of calculation, so next time meet same arguments, directly return record withoug calculating again
  - Reduce exponential time complexity to polynomial lelve (O(2^n) to O(n^2))

- Memoization Search Usage Limit 对这个函数的限制
  - The function must have argument and return value. If not then cannot hashmap it. 
  - The function need to  be pure function, which  means the return value is only affected by the arguments
  - Like cache in Architecture/System Design

- Memoization Search Essence: is DP 记忆化搜索的本质就是动态规划
  - MS is an implementation method of DP
  - DP implementation  methods:
    - Memoization Search
    - Non-recursion/Multi-level for loop
    - see more in below subsection
- MS vs DC
  - Key difference is: whether has repeated computing
  - After Divide step:
    - If left and right sub-parts have overlap => is DP
    - If not => is DC
- MS advantages and disadvantages:
  - cons
    - If Time complexity is O(n) and Recursion Depth is O(n) then it will stackoverflow
      - Recursion Depth should < 100,000
      - Easy [i1300 Bash Game](./leetcode/i1300.bashgame.md) 
    - If Time complexity is O(n^2) and Recursion Depth is O(n) then it will not stackoverflow
    - MS is not suitable for O(n) problems becuase of the risk of stackoverflow
  - pros
    - Add few lines from DC
    - State Transition is simple
  
## 9.2 Dynamic Programming
- DP is a thought, not an algorithm
  - Key: Divide big problems into smaller problem 核心思想：由大化小
  - Algorithms using same thought:
    - Recursion
    - Divide and Conquer (DC)
- DP vs DC 
  - whether there is overlap subproblems 
    - For example:
      - Binary tree, left sub-tree and right sub-tree: on overlap => DC
      - Triangle problem: left child and right child: have overlap => DP
    - also see "MS vs DC" above    
- DP vs Greedy
  - DP would loss of current benefits for long-term benefits
  - Greedy always pursue the maximization of current benefits
- DP implementation
  - Memoization
  - For-loop
    - Top-down
    - Bottom-up
- DP 4 elements:
  - State 动规的状态
  - Function (state transition function) 动规的方程
  - Initialize (base case) 动规的初始化
  - Answer 动规的答案
- DP 4 elements ***1-to-1 correspond*** with Recursion 3 elements 一一对应

|DP|一一对应|Recursion|
|-|-|-|
|DP State 动规的状态| ```dp[i]``` or ```dp[i][j]``` for sub-problems. 用 ```dp[i]``` 或者 ```dp[i][j]``` 代表在某些特定条件下某个规模更小的问题的答案。 规模更小用参数 i,j 之类的来划定|Recursion Definition 递归的定义|
|DP Function 动规的方程|How problems are divided into sub-problems. 大问题如何拆解为小问题.Use smaller scale state to derive ```dp[i][j]```. ```dp[i][j]``` = 通过规模更小的一些状态求 max / min / sum / or 来进行推导|Recursion Divide 递归的拆解|
|DP Initialize 动规的初始化|Base case. 设定无法再拆解的极限小的状态下的值. E.g. ```dp[i][0]``` or ```dp[0][i]```|Recursion Stop Condition 递归的出口|
|DP Answer 动规的答案|What is asked for? 最后要求的答案是什么. E.g. ```dp[n][m]``` or ```max(dp[n][0], dp[n][1] … dp[n][m])```|Recursion Calling 递归的调用|

  - This is why Memoization (using recursion) can be one implementation of DP.

  

[Note DP (more details inside if needed)](note/DP.md)

## Practice:
- Memoization
  - Easy [i1300 Bash Game](./leetcode/i1300.bashgame.md) 
- DP