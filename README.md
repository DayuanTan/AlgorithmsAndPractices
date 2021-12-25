This re[p is about my notes and a record of my practicing of algorithms on Leetcode. 

(It is wrote mainly in English and little Chinese. Ignoring the Chinese parts doens't affect the understanding of this repo.)    

# 0. Steps for all questions

1. Confirm questions with interviewer, including input, output, examples; discuss about corner cases examples
2. Describe your idea/thoughts
3. Write your code while explaining it
4. Introduce your tests and run tests 
5. Time and space complexity analysis
6. Optimal solution or follow up


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
       - Easy [1. Two Sum](leetcode/1.twosum.md); 
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
       - Medium [912. Sort an Array](leetcode/912.sort_an_array.md)
       - merge sort. Easy [88. Merge Sorted Array](leetcode/88.Merge_Sorted_Array.md)
       - Easy [703. Kth Largest Element in a Stream](leetcode/703.Kth_Largest_Element_in_a_Stream.md)
       - Medium [215. Kth Largest Element in an Array](leetcode/215.Kth_Largest_Element_in_an_Array.md)
     - color sort.
2. Back to Back Two Pointers 背向双指针 （最长回文串）
3. Same Direction Two Pointers 同向双指针  
