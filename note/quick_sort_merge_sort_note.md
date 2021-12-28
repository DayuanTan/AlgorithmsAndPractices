
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
|quick sort| avg: O(nlogn). worst: O(n^2) (sorted with p=A[0])|O(1) in place|No|先整体有序再局部有序|
|merge sort|best & worst: O(nlogn)|O(n)|Yes|先局部有序再整体有序|



## stability
Like if you have 2', 1, 3, 2'',
after sorting, 
- if stable: 1, 2', 2'', 3
- if not stable: 1, 2'', 2', 3



# 引申Extend： Quick Select 

找到n个无序元素中的第K大元素，最简单的办法就是将所有元素排序，再去找第k个元素。但实际上，这个过程中会有许多冗余的操作，我们可以进行一些优化，也就是使用接下来要讲的quick select算法。

### 快速选择算法的 Partition 的实质：

快速选择/快速排序中的 partition 是 可左可右 的partition，也就是说，对于nums[i] == pivot 时，这个数字既可以放在左边，也可以放在右边。

### 为什么这样划分数组呢？

原因是为了避免出现类似 [1,1,1,1,1,1] 的数组中的元素，全部被分到一边的情况。我们让 nums[i] == pivot 的情况既不属于左边也不属于右边，这样就能够让 partition 之后的结果稍微平衡一些。
如果 quick select / quick sort 写成了nums[i] < pivot 在左侧，nums[i] >= pivot 在右侧这种形式，就会导致划分不平均，从而导致错误或者超时。

### 为什么问题《partition array》不能使用同样的代码？

对于问题《partition array》来说，题目的要求是将数组划分为两个部分，一部分满足一个条件，另外一部分不满足这个条件，所以可以严格的把 nums[i] < pivot 放在左侧，把 nums[i] >= pivot 放在右侧，这样子做完一次 partition 之后，就能够将这两部分分开。

### 总结

简单的说就是，quick select 和 quick sort 的 partition 目标不是将数组 严格的按照 nums[i] < pivot 和nums[i] >= pivot 去拆分开，而是只要能够让左半部分 <= 右半部分即可。这样子 nums[i] == pivot 放在哪儿都无所谓，两边都可以放。