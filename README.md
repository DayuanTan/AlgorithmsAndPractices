This repo is about my notes and a record of my practicing of algorithms on Leetcode/lintcode. 

Parts of this note refer to Jiuzhang, Labuladong, and other internet recourses. Thanks to them.

(It is wrote mainly in English and barely Chinese. Ignoring the Chinese parts doens't affect the understanding of this repo.)    


## Contents

- [0. Before Starting](#0-before-starting)
  - [Recommended Steps:](#recommended-steps)
  - [Steps for all questions](#steps-for-all-questions)
  - [Data structure](#data-structure)
  - [Algorithms](#algorithms)
  - [Problems](#problems)
- [1. Two Pointers Method (most frequent) - O(n)](#1-two-pointers-method-most-frequent---on)
  - [1Theory:](#1theory)
  - [1Practice:](#1practice)
- [2. Recursion, Heap and Stack (Hardware), Tree](#2-recursion-heap-and-stack-hardware-tree)
  - [2Theory:](#2theory)
  - [2.1 Recursion 3 key elementts:](#21-recursion-3-key-elementts)
  - [2.2 Heap, stack and overflow](#22-heap-stack-and-overflow)
    - [Stack and Heap in Memory 内存中的堆栈](#stack-and-heap-in-memory-内存中的堆栈)
    - [Stack overflow](#stack-overflow)
  - [2.3 Pass by value vs Pass by reference  值传递与引用传递](#23-pass-by-value-vs-pass-by-reference--值传递与引用传递)
  - [2.4 Recursion with Tree, Binary Search递归版本](#24-recursion-with-tree-binary-search递归版本)
  - [2.5 Use Recursion V.S. Non-Recursion (Iteration)](#25-use-recursion-vs-non-recursion-iteration)
  - [2Practice:](#2practice)
- [3. Binary Search O(logn)](#3-binary-search-ologn)
  - [3Theory:](#3theory)
  - [3.0 Make question smaller 由大化小:](#30-make-question-smaller-由大化小)
  - [3.1 Prerequiste and BS Application:](#31-prerequiste-and-bs-application)
  - [3.2 Binary Search V.S. Regular Search](#32-binary-search-vs-regular-search)
  - [Implementation](#implementation)
  - [3.3 Binary Search Template](#33-binary-search-template)
  - [3Practice:](#3practice)
- [4. Queue/Stack, Set/Map/List](#4-queuestack-setmaplist)
  - [4Theory:](#4theory)
  - [4.1 Two ways to store elements internally for queue:](#41-two-ways-to-store-elements-internally-for-queue)
  - [4.2 Queue Implementation:](#42-queue-implementation)
  - [4.3 Java common Interfaces:](#43-java-common-interfaces)
  - [4.4 Interfaces VS Abstract Class](#44-interfaces-vs-abstract-class)
  - [4Practice:](#4practice)
- [5. BFS + Graph](#5-bfs--graph)
  - [5Theory](#5theory)
  - [5.1 Graph Data Structure](#51-graph-data-structure)
  - [5.2 Three scenarios BFS fits](#52-three-scenarios-bfs-fits)
  - [Min/Max -> use PriorityQueue in  Java / heapqueue in Python](#minmax---use-priorityqueue-in--java--heapqueue-in-python)
  - [5.3 Implementation](#53-implementation)
    - [5.3.1 Use Queue and hashset](#531-use-queue-and-hashset)
    - [5.3.2 Three implementation ways](#532-three-implementation-ways)
    - [5.3.3 layered or non-layered 分层还是不分层](#533-layered-or-non-layered-分层还是不分层)
    - [5.3.4 If BFS and DFS both work](#534-if-bfs-and-dfs-both-work)
  - [5.4 Other notable points:](#54-other-notable-points)
  - [5.5 BFS for “all plans” problems 使用宽度优先搜索找所有方案](#55-bfs-for-all-plans-problems-使用宽度优先搜索找所有方案)
  - [5.6 Bidirectional BFS 双向](#56-bidirectional-bfs-双向)
  - [5Practice](#5practice)
- [6. HashMap + Heap](#6-hashmap--heap)
  - [HashMap](#hashmap)
  - [Java - HashMap  vs HashSet](#java---hashmap--vs-hashset)
  - [Collision](#collision)
- [7. DFS](#7-dfs)
  - [7heory (记得用java再做一遍)](#7heory-记得用java再做一遍)
  - [7.1 Combination and Permutation BFS](#71-combination-and-permutation-bfs)
  - [7.2 All-plans problems](#72-all-plans-problems)
  - [7.3 When to use DFS vs BFS](#73-when-to-use-dfs-vs-bfs)
  - [7Practice](#7practice)
- [8. DC - Divide and Conquer](#8-dc---divide-and-conquer)
  - [8Theory](#8theory)
    - [8.1 Recursion V.S. DFS V.S. BackTracking](#81-recursion-vs-dfs-vs-backtracking)
  - [8Practice](#8practice)
- [9. Dynamic Programming - Memoization 记忆化搜索 动态规划](#9-dynamic-programming---memoization-记忆化搜索-动态规划)
  - [9Theory:](#9theory)
  - [9.1 DFS-Traverse -> DC -> DC-with-Hashmap/Memoization Search](#91-dfs-traverse---dc---dc-with-hashmapmemoization-search)
  - [9.2 Dynamic Programming](#92-dynamic-programming)
  - [9.3 DP usually used for 3 types of problems:](#93-dp-usually-used-for-3-types-of-problems)
  - [9Practice:](#9practice)


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

- Common Time Complexity:
  
|Time Complexity	|Possible corresponding Syntax|	Note|
|-|-|-|
|O(1)	|Bit Operation 位运算	|Usually won't be asked. 常数级复杂度，一般面试中不会有|
|O(logn)	|Binary Search 二分法, Doubling 倍增法, Fast exponentiation algorithm 快速幂算法, Euclidean algorithm 辗转相除法	|Mainly BS. 比O(n)更好几乎一定是BS。|
|O(sqrt(n))|Factorization/Decomposition prime factors 分解质因数|Barely 极少|
|O(n)	|Enumeration 枚举法, Two Pointers (w/o sorting) 双指针算法, Monotonic Stack Algorithm 单调栈算法, KMP KMP算法，Rabin Karp，Manacher's Algorithm|	A.k.a linear time complexity. 又称作线性时间复杂度|
|O(nlogn)	|Quick Sort 快速排序, Merge Sort 归并排序, Heap Sort 堆排序.	Or work on O(logn) data structure.| O(logn) Data Structure includes Balanced Tree, Heap, RB-tree.|
|O(n^2)	|Enumeration 枚举法, Dynamic Programming 动态规划, Dijkstra	||
|O(n^3)	|Enumeration 枚举法, Dynamic Programming 动态规划, Floyd ||
|O(2^n)	||Combination related search questions. 与组合有关的搜索问题	|
|O(n!)	||Permutation related search questions. 与排列有关的搜索问题|
||

## Problems
- Find all plans/solutions problems
  - paths == plans == nodes combinations/permutations
  - DFS (with recursion)
  - BFS
- Find amount of all plans 
  - DP
- Find best among all solutions problems
  - Iteration/loop
  - Greedy/ Eplison Greedy
  - Dynamic Programming
  - MDP/ Reinforcement Learning
- Shortest Path problems
  - BFS (simple Graph)
  - Floyd, Dijkstra, Bellman-ford, SPFA (complex graph)
- Longest Path problems
  - Graph can be layered: DP
  - Cannot: DFS





# 1. Two Pointers Method (most frequent) - O(n)

## 1Theory:

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



  
## 1Practice:

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




# 2. Recursion, Heap and Stack (Hardware), Tree

## 2Theory:


## 2.1 Recursion 3 key elementts:
  - Definition, Stopping Condition, Divide. 递归的定义，出口，拆解。
  - 递归的定义：接受什么参数，返回什么值，代表什么意思
  - 递归的拆解：每次递归都是为了让问题规模变⼩
  - 递归的出⼝：必须有⼀个明确的结束条件

=> 得到⼀个可供其他函数调⽤的递归函数

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
|Diff: copy content?|Yes. (more space/time, don't affect upper level)|No. (affect upper level)|
||



## 2.4 Recursion with Tree, Binary Search递归版本

- Binary Tree 
  - Inorder Traversal
  - Preorder Traversal
  - Postorder Traversal
- Construct binary tree from 2 traversals
  - from Inorder and (Preorder or Postorder Traversal)

## 2.5 Use Recursion V.S. Non-Recursion (Iteration)

|Use Recursion |Don't Use Recursion|
|-|-|
|If interviewer ask so.|If interviewer ask not.|
|Recursion depth is not big. No Stackoverflow would happen|Recutsion depth is deep. May stackoverflow.|
||Don't use recursion on LinkedList (Easy to have 100k nodes).
|Cannot implement using non-recursion.|Easy to implement using non-recursion (like binary rearch).|
|Common: DFS uses recursion.|Common: Binary tree inorder traversal uses non-recursion.|
||Other algorithms often use non-recursion.|
||

[Note recursion (more details inside if needed)](note/recursion.md) 

## 2Practice:



- ❗️Easy [509. Fibonacci, O(2^n) -> O(n)](leetcode/509.Fibonacci.md)  Recursion, Memorized Search, Rolling Array  
  - Easy [i771. Double Factorial](leetcode/i771.Double_Factorial.md) 
  - Easy [190. Reverse Bits](leetcode/190.Reverse_Bits.md) 抽空练习
  
  - Easy [104. Maximum Depth of Binary Tree](leetcode/104.Maximum_Depth_of_Binary_Tree.md)
  - Easy [704. Classical Binary Search](leetcode/704.Classical_Binary_Search.md) Recursion, BS
  - Medium [251. Flatten 2D Vector](leetcode/251.Flatten_2D_Vector.md)
- ❗️Easy [206. Reverse Linked List](leetcode/206.Reverse_linked_list.md) 
- ❗️Easy [94. Binary Tree Inorder Traversal](leetcode/94.Binary_Tree_Inorder_Traversal.md) Recursion/Stack
  - Easy [144. Binary Tree Preorder Traversal](leetcode/144.Binary_Tree_Preorder_Traversal.md) 
  - Easy [145. Binary Tree Postorder Traversal](leetcode/145.Binary_Tree_Postorder_Traversal.md)
- ❗️Medium [106. Construct Binary Tree from Inorder and Postorder Traversal](leetcode/106.Construct_Binary_Tree_from_Inorder_and_Postorder_Traversal.md)  
  - Medium [105. Construct Binary Tree from Preorder and Inorder Traversal](leetcode/105.Construct_Binary_Tree_from_Preorder_and_Inorder_Traversal.md)   
  - Medium [889. Construct Binary Tree from Preorder and Postorder Traversal](leetcode/889.Construct_Binary_Tree_from_Preorder_and_Postorder_Traversal.md) 
  - Medium [1008. Construct Binary Search Tree from Preorder Traversal](leetcode/1008.Construct_Binary_Tree_from_Preorder_Traversal.md) BST
- ❗️Medium [113. Path Sum II](leetcode/113.path_sum_ii.md) DFS, Backtrack 
  - Easy [112. Path Sum](leetcode/112.path_sum.md) 

# 3. Binary Search O(logn)

## 3Theory:

## 3.0 Make question smaller 由大化小:
- Recursion
- Binary Search
- Divide and Conqer
- Dynamic Programming

## 3.1 Prerequiste and BS Application: 
- For BS, the array must be sorted (ascending or descending).   
- BS also works for some question may not be sorted, like i585.Maximum_Number_in_Mountain_Sequence
- BS on answer-set instead of question-input.

## 3.2 Binary Search V.S. Regular Search

||Time Complexity|Space Complexity|Muse be sorted?|
|-|-|-|-|
|Binary Search|O(logn)|Same|Ask the array to be sorted.|
|For-loop Search|O(N)|Same|No|
|| 

## Implementation
- Recursion
- For-loop (best choice)
- Both

## 3.3 Binary Search Template
- Attention Point 1: start + 1 < end
- Attention Point 2: start + (end - start) / 2. Overflow if mid = (start + end ) / 2 in Java/C++. 
- Attention Point 3: Seperate cases for =, <, >. Don't change mid value.
- Attention Point 4: Deal with start and end after while-loop.
- Overall idea: Down the range from n to 2 (start or end); Deal with Start and End. (If use while start < end or start <= end, you may encounter dead-loop.)

```py
start, end = 0, len(nums) - 1     
while start + 1 < end: # point 1
    mid = start + (end - start) / 2 # point 2
    if nums[mid] < target: # point 3
        start = mid
    elif nums[mid] == target:
        end = mid # (if ask for first pos)  or return mid (if ask for exist)
    else: 
        end = mid

if nums[start] == target: # point 4. These 2 if may exchange
    return start
if nums[end] == target:
    return end
return -1
```

[Note Binary Search (more details inside if needed), **Template**](note/binarysearch.md) 


## 3Practice:
- ❗️Easy [704. Classical Binary Search](leetcode/704.Classical_Binary_Search.md) BS, Recursion
  - Easy [i458.Last_Position_of_Target](leetcode/i458.Last_Position_of_Target.md) 
  - Easy [i14.First_Position_of_Target.md](leetcode/i14.First_Position_of_Target.md) 

- **Split array to OO|XX two parts**. 
  - ❗️Medium [852. Peak Index in a Mountain Array](leetcode/852.Peak_Index_in_a_Mountain_Array.md)  Increase firstly and then decrease.
  - Medium [658. Find K Closest Elements](leetcode/658.Find_K_Closest_Elements.md)
  - ❗️Medium [153. Find Minimum in Rotated Sorted Array (Unique elements)](leetcode/153.Find_Minimum_in_Rotated_Sorted_Array.md) O(logn)
    - ❗️Hard [154. Find Minimum in Rotated Sorted Array II (duplicate elements)](leetcode/154.Find_Minimum_in_Rotated_Sorted_Array_II.md) O(logn)~ Worst O(n)
  - ❗️Medium [33. Search in Rotated Sorted Array (Unique elements)](leetcode/33.Search_in_Rotated_Sorted_Array.md) 2times BS, 1time BS
    - Medium [81. Search in Rotated Sorted Array II (duplicate elements)](leetcode/81.Search_in_Rotated_Sorted_Array_II.md)
- BS on unorderred array
  - ❗️Medium [162. Find Peak Element](leetcode/162.Find_Peak_Element.md)
    - Medium [1901. Find a Peak Element II](leetcode/1901.Find_Peak_Element_II.md) 还没做
- BS on answer set
  - ❗️Hard [i183. Wood Cut](leetcode/i183.wood_cut.md) O(n log MAX(L))
    - Easy [69. Sqrt(x)](leetcode/69.sqrt_x.md) 
    - Hard [302. Smallest Rectangle Enclosing Black Pixels](leetcode/302.Smallest_Rectangle_Enclosing_Black_Pixels.md) 还没做
- ❗️Medium [i447. Search in a Big Sorted Array](leetcode/i447.Search_in_a_Big_Sorted_Array.md) Exponential Backoff 倍增法
  - Other uses EB:
    - Dynamic Array (ArrayList in Java, Vector in C++)
    - Network Retry





# 4. Queue/Stack, Set/Map/List

## 4Theory:

- Queue: FIFO, abstract data type. Widely used for BFS.

## 4.1 Two ways to store elements internally for queue:
  - Array: Better performance for random access: O(1).
  - LinkedList: Better performance for insert and delete: O(1).

## 4.2 Queue Implementation:
  - Use Array
  - Use Array to implement Circular Queue
  - Use LinkedList
  - Use ArrayList
  - Java Interface Queue (Class PriorityQueue, AbstractQueue)
  - Java Interface Deque (Class ArrayDeque)

## 4.3 Java common Interfaces:
  - Set
  - Map
  - List
  - Queue

|Set|Duplicate|Null|Order|
|-|-|-|-|
|HashSet|No duplicate elements|Can have null|Non Order|
|TreeSet|No duplicate elements|Cannot have null|In Order (Default alphabet order)|
||

|Map|Duplicate|Null|Order|
|-|-|-|-|
|HashMap|key cannot duplicate，value can|key and value both can be null|Non order|
|TreeMap|key cannot duplicate，value can|no null|In Order (by key)|
||

|List|Better at|
|-|-|
|LinkedList|Random access: get, set. O(1)|
|ArrayList|Add, Delete (Given position). O(1)|
||

|Queue|Under Infrastructure|FIFO|
|-|-|-|
|PriorityQueue|Implement base on Heap|Non-FIFO (order by natural order (alphabet order) if no comparator designed, or order by priority if designed)|
|Queue|Implement base on LinkedList|FIFO|
||

## 4.4 Interfaces VS Abstract Class

||Interface|Abstract Class|
|-|-|-|
|Keyword|"implements"|"extends"|
|Methods|Abstract and non-abstract methods.  (Java 8 has default and static methods).|Only abstract methods.  Abstract methods in Abstract class must be implemented by sub-calss.|
|Class Variables|Final (default), static|Final, non-final, static, non-static|
|Class Members|Public (default)|Public, Private, Protected|
|Multiple Inheritance|Yes|No (C++: Yes)|
|Implementation of each other|Cannot impl Abstract Class|Can impl Interface|
|Extend|Can extend other interfaces|Can extend other one class and implement multiple interfaces|
|Java/C++|Partially Interexchangable in Java|C++ only has abstract class|


[Note Interface, Abstract Class (more details inside if needed)](note/queue.md) 


## 4Practice:


- ❗️Easy [232. Implement Queue](leetcode/232.implement_queue.md)
  - Java:
    - Using Array 
    - Array (Circular Queue) 
    - Class LinkedList 
    - Interface Queue (Class LinkedList) 
    - Abstract Class (AbstractQueue) 
    - Interface Deque (Class ArrayDeque) 
    - Class ArrayList
    - Implement Queue Using Stack (Use 2 stacks)
  - Python:
    - list (data type)
    - collections (module, containers datatypes) - Class deque
    - queue class (synchronized) -  Queue (no peek() method)
- ❗️Easy [225. Implement Stack](leetcode/225.implement_stack.md)
  - Java:
    - Class Stack 
    - Class LinkedList
    - Class ArrayList
    - Interface Deque (Class ArrayDeque) 
    - Implement Stack Using Queue (Sol1: use 2 queues; Sol2: use 1 queue)
  - Python:
    - list (data type)
    - collections (module, containers datatypes) - Class deque
    - queue class (synchronized) -  LifoQueue  (no peek() method)
    - Implement Stack Using Queue (use queue.Queue())


- If just use Queue/Stack:
> Java:
> 
> It's better to use ArrayDeque instead of LinkedList when implementing Stack and Queue in Java. ArrayDeque is likely to be faster than Stack interface (while Stack is thread-safe) when used as a stack, and faster than LinkedList when used as a queue. [Refer Link](https://stackoverflow.com/a/38078886/9593219).
> 
> ```Deque/Queue<E> myqueue = new ArrayDeque<E>();``` (interface Deque extends interface Queue )
> 
> ```Deque<E> mystack = new ArrayDeque<E>();``` (use like a stack) (ArrayDeque  is faster than LinkedList)

|Queue Method (Use this column methods directly)	|Equivalent Deque Method|Stack Method (Use this column methods directly)|Equivalent Deque Method|
|-:|-|-:|-|
|add(e)	|addLast(e)|push(e)|addFirst(e)|
|offer(e)|offerLast(e)|||
|remove()|removeFirst()|||
|poll()|pollFirst()|pop()|removeFirst()|
|element()|getFirst()|||
|peek()|peekFirst()|peek()|peekFirst()|



> Python:
> 
> ```from collections import deque```
> 
> ```mystack = deque()``` # left as top
>
> ```myqueue = deque()``` (left as head/first)(synchronize Queue is slower)


|Queue Method (Use this column methods directly)	|Equivalent collections.deque Method|Stack Method (Use this column methods directly)|Equivalent collections.deque Method|
|-:|-|-:|-|
|push|myqueue.append(x) |push| mystack.appendleft(x)|
|pop|myqueue.popleft()|pop| mystack.popleft()|
|peek|if myqueue:return myqueue[0] else: return -1|top| if mystack: return mystack[0]|
|empty|len(myqueue) == 0|empty| len(mystack) == 0|





# 5. BFS + Graph

## 5Theory

## 5.1 Graph Data Structure  

1. Adjacency Matrix 
   - ```int[][] matrix```; 2D array.
   - Space: O(n^2) 
```
[
[1,0,0,1],
[0,1,1,0],
[0,1,1,0],
[1,0,0,1]
]
```
2. Adjacency List (More frequently used) 
   - Each node records its neighbors.
   - Space O(E). Worst case O(n^2). 
   - Implement an Adjacency List:
     - Use self-defined Class 
       - more popular in Software Engineered, recommend if enough time
     - Use HashMap<T, HashSet>  
       - ```Map<Integer, Set<Integer>> myGraph = new HashMap<>(); myGraph.put(0, new HashSet<Integer>();``` 
       - (less code)

```
[
[1],
[0,2,3],
[1],
[1]
]
```


Java:
```java
class DirectedGraphNode {
  int label;
  List neighbors;
  ...
}
```
Python:
```python
def DirectedGraphNode:
  def init(self, label):
    self.label = label
    self.neighbors = [] # a list of DirectedGraphNode's
    ...
```

Java:
```java
Map<Integer, Set<Integer>> myGraph = new HashMap<Integer, HashSet>(); 
myGraph.put(0, new HashSet<Integer>();
```
Python:
```python
adjacency_list = {x:set() for x in nodes}
```
```python
adjacency_list = {}
for x in nodes:
  adjacency_list[x] = set()
```


## 5.2 Three scenarios BFS fits

- level order traversal 分层遍历
  - traversal hierarchical a Grapg, Tree, Matrix
    - BFS on tree
    - BFS on Graph: O(V+E) 
    - BFS on Matrix: O(row * col)
  - shortest path for simple Graph (all edge length are 1)
- connected component 连通块问题
  - find all connected cell
  - non-recursion implementation for find-all-plans problem
- topological sort 拓扑排序 ```（几乎每个公司面试都会有一道拓扑排序题）```
  - Can also be done using DFS. BFS much easier. (When both can, always use BFS).
  - TS must for DAG (Directed Acyclic Graph). If not DAG then no TS. If DG has not TS then it must be cyclic.
  - Examples: Course Select, Compile Order
  - Questions:
    - find any Topological order
    - whether there is TO (a graph may have #TO >= 0)
      - If len(the answer of previous one) == #nodes then exist. Or don't exist.
    - find whether only one TO
      - Yes if queue.size == 1 during whole process. (bc only one choose for next node)
      - If at some step queue.size > 1 then not only one. (more than 1 choose)
    - find the TO with min lexicographical order
      - Min/Max -> use PriorityQueue 
  
## Min/Max -> use PriorityQueue in  Java / heapqueue in Python
- Java: 
  - ```Queue<> myqueue = new PriorityQueue<>()``` 
  - ```myqueue.poll()``` 
  - ```myqueue.offer(newnode)```
- Python: 
  - ```myqueue = []``` 
  - ```heapify(myqueue)``` 
  - ```heappop(myqueue)``` 
  - ```heappush(myqueue, newnode)```
    

## 5.3 Implementation 
### 5.3.1 Use Queue and hashset
- Queue is used to record which nodes need to be process
- Hashtable to record visited nodes if necessary:
  - to avoid repeated calculation
  - to prune in tree 
  - to avlid cycle in graph
  - Java: HashSet/HashMap
  - Python: set/dict
  - C++: unordered_set/unordered_map

### 5.3.2 Three implementation ways
- Single Queue (simplest, recommend)
- Two Queues (easier understand)
- Dummy Node 哨兵节点
  - Usually point to first node in LinkedList
  - pop(): delete head node. ```DummyNode.next = DummyNode.next.next```
  - In BFS: used to indicate end of each level.
  - Advantage: reduce one for-loop.

### 5.3.3 layered or non-layered 分层还是不分层
  - ❗️[BFS Template](note/bfs_template.md) Queue record nodes to process. HashTable record visited node to prune or avoid cycle.
### 5.3.4 If BFS and DFS both work
  - Use BFS (always easier). 
    - DFS recursion easily stackoverflow.
    - DFS iteration is hard and interviewer may also don't understand. 
  - You barely write BFS wrongly  


## 5.4 Other notable points:
- BFS for shorted path
  - Simple graph: BFS
  - Complex graph: Floyd, Dijkstra, Bellman-ford, SPFA. (Usually not appear in interviews)
- Longest path:
  - The graph can be layered (directed, no cycle): DP
  - Cannot: DFS
- BFS for Binary Tree vs BFS for Graph
  - Tree is a special Graph
  - Tree has no circle so no need to record visited nodes
  - HashSet/dict/unordered_map  -> record visited nodes
    - Possible circle in graph, where one node will be enqueued more than 1 times -> olution: record visited nodes


## 5.5 BFS for “all plans” problems 使用宽度优先搜索找所有方案
- One plan == one path
  - All plans == find all paths (like connected-component problems)
  - Medium [78. Subsets](leetcode/78.subset.md) DFS/BFS
  - 序列化 Hard [297. Serialize and Deserialize Binary Tree](297.Serialize_and_Deserialize_Binary_Tree.md)  

## 5.6 Bidirectional BFS 双向
- 如果同时给了start and end point
- 图的话一般是无向图
- [Bi-BFS Template](note/bfs_template.md)

## 5Practice

- level order traversal 分层遍历
  - ❗️Medium [102. Binary Tree Level Order Traversal](leetcode/102.Binary_Tree_Level_Order_Traversal.md) 3 types BFS (1 queue, 2 queues, dummy node), DFS
    - ❗️探索Medium [1197. Minimum Knight Moves](leetcode/1197.Minimum_Knight_Moves.md) BFS + Pruning, bi-BFS, DP等多解法
    - ❗️总结[BFS Template](note/bfs_template.md) Queue record nodes to process. HashTable record visited node to prune or avoid cycle.
  - Simple graph shortest path 简单图最短路径
    - Hard [127. Word Ladder](leetcode/127.word_ladder.md) BFS分层/不分层, bi-BFS
- Connected component 连通块问题
  - ❗️Medium [133. Clone Graph](leetcode/133.clone_graph.md)
  - BFS on Matrix (Change coordinates)
    - ❗️Medium [200. Number of Islands](leetcode/200.number_of_islands.md) BFS / Union Find
    - Medium [1197. Minimum Knight Moves](leetcode/1197.Minimum_Knight_Moves.md) 上面做过
  - BFS on Graph
    - ❗️Medium [261. Graph Valid Tree](leetcode/261.graph_valid_tree.md)
    - Medium [323. Number of Connected Components in an Undirected Graph](leetcode/323.Number_of_Connected_Components_in_an_Undirected_Graph.md)

- Topological Sorting 拓扑排序 (BFS on Graph)
  - find any Topological order
    - ❗️Medium [i127 Topological Sorting](leetcode/i127.topological_sort.md)
    - Medium [207. Course Schedule](leetcode/207.course_schedule.md)
  - whether there is TO (a graph may have #TO >= 0)
    - ❗️Medium [210. Course Schedule II](leetcode/210.course_schedule_ii.md)
  - find whether only one TO
    - ❗️Medium [444. Sequence Reconstruction](leetcode/444.sequence_reconstruction.md)
  - find the TO with min lexicographical order
    - ❗️Hard [269. Alien Dictionary](leetcode/269.alien_dictionary.md)

- Bi-BFS
  - Medium [1197. Minimum Knight Moves](leetcode/1197.Minimum_Knight_Moves.md) bi-BFS
  - Hard [127. Word Ladder](leetcode/127.word_ladder.md) BFS分层/不分层, bi-BFS


[other](leetcode/bfs_other.md)



# 6. HashMap + Heap

## HashMap
- O(1) 
  - get(key), set(key, value)
  - actually O(size of keys)
- Capacity, load factor, rehash
  - Java HashMap: default initial capacity (16) and the default load factor (0.75).
  - HashSet: the backing HashMap instance has default initial capacity (16) and load factor (0.75).
  - rehash when size >= 16 * 0.75 = 12

## Java - HashMap  vs HashSet
|HashMap|	HashSet| HashTable|
|-|-|-|
|Implement Map interface|	Implement Set intergace|Implement Map interface. Inherits Dictionary class.|
|Store key-value pair|	Store object|Store key-value pair|
|Unique key|Unique element|Unique key|
|One null as key. Multiple null can be values.|One null element allowed|No null as key neither value|
|put() - add element|add() - add element|put() - add element|
|HashMap uses key to calculate Hashcode	|HashSet uses the member object to calculate the hashcode value. The hashcode may be the same for two objects, so use the equals() method to determine the equality of the objects. If the two objects are different, return false|HashTable uses key to calculate Hashcode	|
|It is not Thread-Safe because it is not Synchronized but it gives better performance.	|Like HashMap, it is not Thread-Safe because it is not Synchronized.|	It is Thread-Safe because it is Synchronized.|
||

|HashSet|	TreeSet	|LinkedHashSet|
|-|-|-|
|HashSet is fastest than LinkedHashSet and TreeSet|	TreeSet is slow when compared with both Hashset and LinkedHashSet	|LinkedHashSet is second fastest next to HashSet|
|HashSet does not maintain any order|	TreeSet maintains Sorting Order	|LinkedHashSet maintains insertion order|
|HashSet allows null|	TreeSet does not allow null	|LinkedHashSet allows null|
|HashSet uses equals() method	|TreeSet uses compareTo() method	|LinkedHashSet uses equals() method|
|HashSet backed by HashMap|	TreeSet backed by NavigableMap	|LinkedHashSet backed by HashSet|
||



- Python - set()/dict()
  - Collision: open-hashing.
- C++ - unordered_set() / unordered_map()

## Collision
- open hashing /  closed addressing / seperate chaining 
  - keys are stored in linked lists attached to cells of a hash table.
- closed hashing / open addressing/ linear probing
  - all keys are stored in the hash table itself without the use of linked lists.
  - tomb (deleted element flag)
  - double hashing (reduce hitting clumps possibility)

[Note Hash more](note/hash.md)

- Easy [706. Design HashMap](leetcode/706.design_hashmap.md)
- Easy [705. Design HashSet](leetcode/705.design_hashset.md)



# 7. DFS

## 7heory (记得用java再做一遍)

## 7.1 Combination and Permutation BFS  
- Except Binary Tree, 90% of DFS is combination or permutation problems. Especially combination. 
- DFS with Combinations
  - C(n, k) = n! / {k! (n-k)!}
  - Implicit graph search problem
    - If one problem doesn't tell you what are vertexes and edges but ask you to search, then it's implicit graph searching problem.
    - Firstly we need to figure out what are vertexes and edges.
    - ❗️Medium [78. Subset](leetcode/78.subset.md) 
      - Find all plans problem -> Use DFS
      - Solution 1 Combination Special DFS 分层
      - Solution 2 General DFS 不分层
      - Solution 3 BFS 
    - ❗️Medium [90. Subset ii](leetcode/90.subset_ii.md) Duplicate elements
      - Remove duplicate while searching
        - Sort and compare to avoid duplicate
        - Hash (Python: set/dict; Java: HashSet/HashMap)
- DFS with Permutations
  - Permutation considers order. P(n, k) = A(n, k) =  n factorial = n!
  - ❗️Medium [46. Permutations](leetcode/46.permutations.md) Distinct elements. 1.DFS-Permutation-Recursion; 2.Non-Recursion 
- Combination DFS vs Permutation DFS
  - Search Tree shape
  - Templates
- DFS Time Complexition
  - O(#all-plans * time-to-build-one-plan) 
    - Combinations: O(2^N * N)
    - Permutations: O(N! * N)
    - => small depth and may large width => DFS

## 7.2 All-plans problems
- Find all plans meet requirements 找所有满足某个条件的方案
- Find all paths 找到图中的所有满足条件的路径
  - 路径 == 方案 == 图中节点的排列组合
- Can be solved using BFS?
  - Yes
  - Need to convert find-all-paths to find-all-nodes

## 7.3 When to use DFS vs BFS

- The space complexity of BFS depends on its width 宽度优先搜索的空间复杂度取决于宽度 
- The space complexity of DFS depends on its depth 深度优先搜索的空间复杂度取决于深度
- If the search tree is deep but not wide then BFS
  - Matrix uses BFS
    - For example, in matrix, the width is <= sqrt(n) while depth is <= n^2 so it's better to use BFS.
- If the search tree is wide but not deep then DFS
  - Combinations/Permutations use DFS
    - They are O(2^n)/O(n!) so the n cannot be large => the depth won't be large but the width might be large => DFS





## 7Practice

- Combinations  
  - Medium [39. Combination Sum](leetcode/39.combination_sum.md) distinct, use multiple times
    - Medium [40. Combination Sum II](leetcode/40.combination_sum_ii.md) duplicate, use once
    - Medium [216. Combination Sum III](leetcode/216.combination_sum3.md) k members sum up to target (Medium ==i90. K Sum II), use once
    - Medium [377. Combination Sum IV](leetcode/377.combination_sum4.md) total amount of combinations  (== Hard i89. K Sum) - DP 以后再做
  - Medium [77. Combinations](leetcode/77.combinations.md) Recursion, Stack以后再做
  - Medium [17. Letter Combinations of a Phone Number](leetcode/17.Letter_Combinations_of_a_Phone_Number.md)
  
  
- DFS on Matrix
  - Medium [79. Word Search](leetcode/79.word_search.md) one target word
    - Hard [212. Word Search II](leetcode/212.Word_Search_II.md) multiple target words. Prefix map/Trie
      - Hard [i638. Boggle Game](leetcode/i638.boggle_game.md) same as 212
    - Hard [i1848. Word Search III](leetcode/i1848.Word_Search_III.md) multiple target words in continous sequence. Trie.
  

  - Hard [127. Word Ladder 求最优方案之一](leetcode/127.word_ladder.md) BFS分层/不分层, bi-BFS. (Review first先复习下这个方便和下一个对比)
    - Hard [126. Word Ladder II 求全部最优方案path](leetcode/126.word_ladder2.md) BFS+DFS

- Permutations
  - Medium [46. Permutations](leetcode/46.permutations.md) Distinct elements. 1.DFS-Permutation-Recursion; 2.Non-Recursion/Stack. 
  - Medium [47. Permutations II](leetcode/47.Permutations_II.md) duplicate elements.
  - Medium [31. Next Permutation](leetcode/31.Next_Permutation.md)

- Implicit Graph/Tree
  - Hard [51. N-Queens](leetcode/51.n_queens.md) Each possible move is a tree node. Ask all-plans.
    - Hard [52. N-Queens 2](leetcode/52.n_queens_2.md) Ask #all-plans. Almost same.
  - Hard [37.  Sudoku Solver](leetcode/37.sudoku_solver.md) DFS
    - Medium [36.  Valid Sudoku](leetcode/36.valid_sudoku.md) Array Traverse
  - Hard [980. Unique Paths III]() DFS, DP


TSP 
  DFS, pruning, DP
  1.   Shortest Path Visiting All Nodes
  2.    Minimum Time Visiting All Points

然后完成bfs bi-bfs
然后7dc
然后dp

# 8. DC - Divide and Conquer

## 8Theory

### 8.1 Recursion V.S. DFS V.S. BackTracking
|Recursion|DFS|BackTracking|
|-|-|-|
|Recursion function: One way to implement the program, i.e. a function calls itself.|DFS can be implemented by using Recursion fucntion.|Backtracking method: It is DFS algorithm.|
|Recursion algorithm: The result of bigger problems depend on the result of smaller problems. So use the recursion function to solve the smaller problems.|DFS can be implemented without using Recursion fucntion, for example you design a stack and operate by hand yourself. |Backtracking operation: when the recursion function return to its previous layer, some parameters need to be changed back to their previous values.|
|Usually when we say recursion, we mean the recursion function.|DFS is a traversal/searching algorithm.||
||


|Traversal 遍历法|DC 分治法|
|-|-|
|A helper guy stores all visited nodes |Ask your gangs to solve the sub-problem and you sum up their results yourself|
|Usually use a global variable or shared argument|Usually use return-value to store results of sub-problems|
||

- Easy [257. Binary Tree Paths (find all paths)](leetcode/257.Binary_Tree_Paths.md) DFS, 遍历法 vs 分治法 
- [Binary tree DC template](note/binary_tree_dc.md)
- Easy [110. Balanced Binary Tree](leetcode/110.Balanced_Binary_Tree.md) Traversal and DC
  - Easy [104. Maximum Depth of Binary Tree](leetcode/104.Maximum_Depth_of_Binary_Tree.md)
  - Meidum [1120. Maximum Average Subtree](leetcode/1120.Maximum_average_of_subtree.md)
  - Hard [4. Median of Two Sorted Arrays](leetcode/4.Median_of_Two_Sorted_Arrays.md)

## 8Practice


# 9. Dynamic Programming - Memoization 记忆化搜索 动态规划

## 9Theory:
## 9.1 DFS-Traverse -> DC -> DC-with-Hashmap/Memoization Search

- ❗️Easy [120 Triangle](leetcode/120.triangle.md) 
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

## 9.3 DP usually used for 3 types of problems:
- min value/max value 最值问题
- number of all plans 方案总数
- feasibility 可行性

|DP|一一对应|Recursion|
|-|-|-|
|DP State 动规的状态| ```dp[i]``` or ```dp[i][j]``` for sub-problems. 用 ```dp[i]``` 或者 ```dp[i][j]``` 代表在某些特定条件下某个规模更小的问题的答案。 规模更小用参数 i,j 之类的来划定|Recursion Definition 递归的定义|
|DP Function 动规的方程|How problems are divided into sub-problems. 大问题如何拆解为小问题.Use smaller scale state to derive ```dp[i][j]```. ```dp[i][j]``` = 通过规模更小的一些状态求 max / min / sum / or 来进行推导|Recursion Divide 递归的拆解|
|DP Initialize 动规的初始化|Base case. 设定无法再拆解的极限小的状态下的值. E.g. ```dp[i][0]``` or ```dp[0][i]```|Recursion Stop Condition 递归的出口|
|DP Answer 动规的答案|What is asked for? 最后要求的答案是什么. E.g. ```dp[n][m]``` or ```max(dp[n][0], dp[n][1] … dp[n][m])```|Recursion Calling 递归的调用|

  - This is why Memoization (using recursion) can be one implementation of DP.

  

[Note DP (more details inside if needed)](note/DP.md)

## 9Practice:
- Memoization
  - Easy [i1300 Bash Game](./leetcode/i1300.bashgame.md) 
- DP
