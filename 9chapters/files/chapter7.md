Part 1 

----
([Go back to respository ReadMe](../../README.md))


今天我们一起来学习『一个不会出现死循环的通用二分法模板』

在上一节课中，我们学习了时间复杂度和空间复杂度分析的相关知识。这一节课，我们就来学习算法课程中一个入门级别的算法——二分算法，首先我们来看一下这个算法的基本原理以及为什么我们要用这个算法。

## 为什么要使用二分查找？

-  普通查找花费的时间较多


## 在数组中二分搜索一个数字，这个数组
- 必须是有序的，递增和递减无所谓


二分搜索的有点就是时间复杂度是O(logn)的，而普通的查找时间复杂度是O(N)的。但他们所消耗的空间是一样的。同时普通查找不需要数组有序，直接for循环即可，但是二分查找需要数组有一定的顺序。

||时间复杂度|空间复杂度|是否要求有序|
|-|-|-|-|
|二分搜索|O(logn)|一样|需要数组有一定的顺序|
|普通查找|O(N)|一样|不需要数组有序|
||




## **二分法的模版**


- 要点1: start + 1 < end
- 要点2：start + (end - start) / 2. 如果是mid = (start + end ) / 2 那么当两者都为2^31会溢出.
- 要点3：=, <, > 分开讨论，mid 不+1也不-1. 如果target存在，不能加，如果不存在，需要加；总结cover全部情况的，不加。
- 要点4: 循环结束后，单独处理start和end

Java 版本
```java
public class Solution {
    /**
     * @param A an integer array sorted in ascending order
     * @param target an integer
     * @return an integer
     */
    public int findPosition(int[] nums, int target) {
        if (nums == null || nums.length == 0) {
            return -1;
        }

        int start = 0, end = nums.length - 1;
        // 要点1: start + 1 < end
        while (start + 1 < end) {
        // 要点2：start + (end - start) / 2. 如果是mid = (start + end ) / 2 那么当两者都为2^31会溢出.
            int mid = start + (end - start) / 2;
            // 要点3：=, <, > 分开讨论，mid 不+1也不-1. 如果target存在，不能加，如果不存在，需要加；总结cover全部情况的，不加。
            if (nums[mid] == target) {
                return mid;
            } else if (nums[mid] < target) {
                start = mid;
            } else {
                end = mid;
            }
        }

        // 要点4: 循环结束后，单独处理start和end
        if (nums[start] == target) {
            return start;
        }
        if (nums[end] == target) {
            return end;
        }
        return -1;
    }
}
```

Python 版本
```python
class Solution:
    # @param nums: The integer array
    # @param target: Target number to find
    # @return the first position of target in nums, position start from 0 
    def binarySearch(self, nums, target):
        if not nums:
            return -1

        start, end = 0, len(nums) - 1
        # 用 start + 1 < end 而不是 start < end 的目的是为了避免死循环
        # 在 first position of target 的情况下不会出现死循环
        # 但是在 last position of target 的情况下会出现死循环
        # 样例：nums=[1，1] target = 1
        # 为了统一模板，我们就都采用 start + 1 < end，就保证不会出现死循环
        while start + 1 < end:
            # python 没有 overflow 的问题，直接 // 2 就可以了
            # java和C++ 最好写成 mid = start + (end - start) / 2
            # 防止在 start = 2^31 - 1, end = 2^31 - 1 的情况下出现加法 overflow
            mid = (start + end) // 2

            # > , =, < 的逻辑先分开写，然后在看看 = 的情况是否能合并到其他分支里
            if nums[mid] < target:
                start = mid
            elif nums[mid] == target:
                end = mid
            else: 
                end = mid

        # 因为上面的循环退出条件是 start + 1 < end
        # 因此这里循环结束的时候，start 和 end 的关系是相邻关系（1和2，3和4这种）
        # 因此需要再单独判断 start 和 end 这两个数谁是我们要的答案
        # 如果是找 first position of target 就先看 start，否则就先看 end
        if nums[start] == target:
            return start
        if nums[end] == target:
            return end

        return -1
```


## 死循环

如果你之前写过二分的题目，你会发现在二分问题中，最常见的错误就是死循环。而这个模版一定不会出现死循环。为什么呢？

因为我们这边使用了start + 1 < end, 而不是start < end 或者 start <= end

二分法的模板中，整个程序架构分为两个部分：
- 通过 while 循环，将区间范围从 n 缩小到 2 （只有 start 和 end 两个点）。
- 在 start 和 end 中判断是否有解。

而普通的start < end 或者 start <= end 在寻找目标最后一次出现的位置的时候，可能出现死循环。

## LC

[457. Classical Binary Search](../lintcode/457.Classical_Binary_Search.md) 

三个思路：
|思路|时间复杂度|问题|
|-|-|-|
|遍历|O(N)|太慢|
|HashTable|O(1)|是在内存上操作，当数据集较大时，无法全放到内存上，那么就不能用了。|
|二分查找|O(logN)|磁盘上操作|
||



[458. Last Position of Target](../lintcode/458.Last_Position_of_Target.md)

[14. First Position of Target](../lintcode/14.First_Position_of_Target.md)

但二分算法仍然有许多考点，我们现在来出一道不一样一点的题目，看看你能否用二分算法解决它。

[585. Maximum Number in Mountain Sequence](../lintcode/585.Maximum_Number_in_Mountain_Sequence.md)

如果你解决了585这道题，你会发现，二分问题其实并不需要要求数组一定是严格有序的，我们不能根据数组是否有序来判断是否是二分问题。

那我们该如何判断这个问题是否是二分问题呢？大家可以先思考一下。

不知道大家还记不记得，我们在上一节课就讲了一个判断算法的技巧——通过时间复杂度判断算法。在这里就能用到这个技巧。我们知道二分答案的时间复杂度是O(logn)的。所以当你发现有一个问题，用O(N)的时间复杂度非常好做，或者面试官说：“你给我优化一下这个算法。”那么你优化的思路就是优化到O(logn)，也就是尝试使用二分去做，这就是二分算法的判断条件.