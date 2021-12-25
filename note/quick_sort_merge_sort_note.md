
# Quick sort

1. pick a pivot p
   - pivot need the value, not index
   - pivot selection: random() > middle point (lower possibility to be worst case) > start or end point (higher possibility to be worst case). 
2. partition:
   - put <=p left
   - put >=p right
3. Note "==p" be both left and right. This is used to avoid all left or all right extreme worst case. 
4. Partition之后对左右两部分递归。先整体有序，再局部有序。After partition we parition the left and right parts using recursion, this is thought firstly global sorted then local sorted.

# Quick sort Coding
- 三个要注意的点 看三个注释的地方：
- pivot建议选中点
- left和right比较是总是<=。 一共四个地方。
- A[]和pivot比较时总是<。一共两个地方。


# Merge sort

- 分治的思想 divide and conquer
- 先局部有序 再整体有序
- Space O(n) 额外O(n)的空间 是个很费时间的事情

# Divide and conquer

T(n) = 2 * T(n/2) + O(n)

- quick sort: fisrt do O(n) - partition, 
- merge sort: fisrt sort T(n/2), second merge O(n)


# Quick sort vs Merge sort
||Time Complexity|Space Complexity|Stability|Philosophy|
|-|-|-|-|-|
|quick sort| avg: O(nlogn). worst: O(n^2) (sorted with p=A[0])|O(1)|No|先整体有序再局部有序|
|merge sort|best & worst: O(nlogn)|O(n)|Yes|先局部有序再整体有序|



## stability
Like if you have 2', 1, 3, 2'',
after sorting, 
- if stable: 1, 2', 2'', 3
- if not stable: 1, 2'', 2', 3