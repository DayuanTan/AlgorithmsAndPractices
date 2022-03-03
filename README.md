This repo is about my notes and a record of my practicing of algorithms on Leetcode. 

(It is wrote mainly in English and barely Chinese. Ignoring the Chinese parts doens't affect the understanding of this repo.)    

# 0. Steps for all questions

1. Clarification. Confirm questions with interviewer, including input, output, examples; discuss about corner cases examples.
2. Think out loud. Describe your idea/thoughts before coding. Talk before write.
3. Point out your assumption. Like arguments/inputs are in memory, are they sorted already or not.
4. Talk through. Write your code while explaining it.
5. Introduce your tests and run tests. Test in real time, use examples given, then edge cases. 
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
  - sorting, searching, binary searching
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
       - ❗️Easy [1. Two Sum](leetcode/1.twosum.md) (2 pointer base - O(nlogn), hashmap O(n)); 
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
     - quick select
       - ❗️Medium [215. Kth Largest Element in an Array](leetcode/215.Kth_Largest_Element_in_an_Array.md) sort/partition/priority queue/heap
       - Easy [703. Kth Largest Element in a Stream](leetcode/703.Kth_Largest_Element_in_a_Stream.md) 抽空练习
       - Medium [1985. Find the Kth Largest Integer in the Array](leetcode/1985.Find_the_Kth_Largest_Integer_in_the_Array.md) 抽空练习
       - Medium [75. sort colors](leetcode/75.sort_colors.md) 抽空练习
       - Hard [295. Find Median from Data Stream](leetcode/295.Find_Median_from_Data_Stream.md) 抽空练习
2. Back to Back Two Pointers 背向双指针 (only below 3 tyeps:)
   - Longest Palindromic Substring 最长回文子串 - 中心线枚举算法
   - Find K closet elements (also in binary search)
   - Square of sorted array
3. Same Direction Two Pointers 同向双指针  
   - Sliding Window 滑动窗口类
   - Fast & Slow pointers 快慢指针类 




# 2. Recursion, Heap and Stack (Hardware), Tree

## Theory

## Practice

