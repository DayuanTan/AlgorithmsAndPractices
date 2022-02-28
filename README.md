This repo is about my notes and a record of my practicing of algorithms on Leetcode. 

(It is wrote mainly in English and little Chinese. Ignoring the Chinese parts doens't affect the understanding of this repo.)    

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
  - 考得频率Test freq.: 2 pointers >> 打擂台算法 ~= 单调栈算法 ~= 单调队列算法

# 1. Two Pointers Method

## Theory:

1. Face to Face Two Pointers 相向双指针 
   - Two Sum type
     - sum of two numbers. 
     - sum of three numbers. 
   - Reverse type     
     - 判断回文串 palindrome. 
     - 翻转字符串 flip string. 
   - Partition type
     - quick sort. 
     - color sort.
2. Back to Back Two Pointers 背向双指针 （最长回文串）
3. Same Direction Two Pointers 同向双指针  


||Time Complexity|Space Complexity|
|-|-|-|
|Use HashTable| O(n)|O(n)|
|USe (sort +) 2 pointers|O(nlogn)|O(1)|



  
## Practice:

1. Face to Face Two Pointers 相向双指针 
   - Two Sum type
     - sum of two numbers.  
       - Easy [1. Two Sum](leetcode/1.twosum.md) (2 pointer base - O(nlogn), hashtable O(n)); 
       - [Two sum note](note/twosumnote.md)
       - Easy [167. Two Sum II - Input array is sorted](leetcode/167.Two_Sum_II_Input_array_is_sorted.md);  
       - Easy [1099. Two Sum - Less than or equal to target](leetcode/1099.Two_Sum_Less_than_or_equal_to_target.md) 
       - Easy [611. Valid Triangle Number](leetcode/611.Valid_Triangle_Number.md) 
     - sum of three numbers. 
       - Medium [15. 3 Sum](leetcode/15.3sum.md)
   - Reverse type     
     - palindrome 判断回文串. 
       - Easy [125. Valid Palindrome (corner cases, help func)](leetcode/125.Valid_Palindrome.md) 
       - Easy [680. Valid Palindrome II (repeated code)](leetcode/680.Valid_Palindrome_II.md) 
     - flip string 翻转字符串. 
   - Partition type
     - quick sort. 
       - [Quick sort merge sort note](note/quick_sort_merge_sort_note.md)
       - Medium [912. Sort an Array (quick & merge sort)](leetcode/912.sort_an_array.md)
       - merge sort. Easy [88. Merge Sorted Array](leetcode/88.Merge_Sorted_Array.md)
       - Hard [493. Reverse Pairs](leetcode/493.Reverse_Pairs.md)
     - quick select
       - Easy [703. Kth Largest Element in a Stream](leetcode/703.Kth_Largest_Element_in_a_Stream.md)
       - Medium [215. Kth Largest Element in an Array](leetcode/215.Kth_Largest_Element_in_an_Array.md)
       - Medium [75. sort colors](leetcode/75.sort_colors.md)
2. Back to Back Two Pointers 背向双指针 （最长回文串）
3. Same Direction Two Pointers 同向双指针  


# 2. Recursion, Heap and Stack (Hardware), Tree

## Theory

## Practice

