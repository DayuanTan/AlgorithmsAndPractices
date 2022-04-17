
# 时间复杂度 - 用 T 函数表示法计算时间复杂度

一种计算时间复杂度的方法 --- 用 T 函数表示法计算时间复杂度。


## ***T函数推导法***


比如二分法。二分法是每次通过 O(1) 的时间将规模为 n 的问题降低为规模为 n/2的问题。

这里我们用 T(n) 来表示规模为 n 的问题在该算法下的时间复杂度，那么我们得出推导公式：

```
T(n) = T(n/2) + O(1)
```

我们来逐个说明一下这个公式的意义。

首先 T 代表的是 Time Complexity,n 代表的是问题规模（二分法里就是数组的大小）。

那么 T(n) 代表的就是：**求处理问题规模为n的数据的时间复杂度是多少**。注意这里是一个问句，不是一个答案。

T(n) 根据算法的不同可以是O(n), 也可以是 O(nlogn)或任何值，而 O(n) 就是 O(n)。

然后 O 代表的是时间复杂度。O(1) 就意味着，你大概用一个 if 语句，或者简单的加加减减，就可以完成。O 在这里的意思是数量级约等于。在 O 的世界里，我们只考虑最高项是什么，不考虑系数和常数项。比如：

O(100n) = O(n)

O(n^2 + n) = O(n^2)

O(2^n + n^2 + 10) = O(2^n)

## ***如何推导 T 函数***

我们可以使用不断展开的方法进行推导：
```
T(n) = T(n/2) + O(1)
     = T(n/4) + O(1) + O(1)
     = T(n/8) + O(1) * 3
     = T(n/16) + O(1) * 4
     ...
     = T(1) + O(1) * logn
     = O(logn)
```

在时间复杂度的领域里，有如下的一些性质：

1. T(1) = O(1)// 解决规模为1的问题通常时间复杂度为O(1)。这个不100%对，但是99.9%的情况下都是如此。
2. k * O(n) = O(kn)
3. O(n) + O(m) = O(n + m)


上面的方法，是采用 T 函数展开的方法，将二分法的时间复杂度最终用 O(...) 来表示


### **那我们了解时间复杂度有什么用呢？**

- 在做题过程中，如果知道题目的数据范围，我们可以通过数据范围估算时间复杂度，***再根据时间复杂度估计算法***。

# **算法中，常见的时间复杂度有：**

|复杂度	|可能对应的语法|	备注|
|-|-|-|
|O(1)	|位运算	|常数级复杂度，一般面试中不会有|
|O(logn)	|二分法，倍增法，快速幂算法，辗转相除法	||
|O(n)	|枚举法，双指针算法，单调栈算法，KMP算法，Rabin Karp，Manacher's Algorithm|	又称作线性时间复杂度|
|O(nlogn)	|快速排序，归并排序，堆排序	||
|O(n^2)	|枚举法，动态规划，Dijkstra	||
|O(n^3)	|枚举法，动态规划，Floyd	||
|O(2^n)	||与组合有关的搜索问题	|
|O(n!)	||与排列有关的搜索问题|
||

在面试中，经常会涉及到时间复杂度的计算。当你在对于一个问题给出一种解法之后，面试官常会进一步询问，是否有更优的方法。此时就是在问你是否有时间复杂度更小的方法（有的时候也要考虑空间复杂度更小的方法），这个时候需要你对常用的数据结构操作和算法的时间复杂度有清晰的认识，从而分析出可优化的部分，给出更优的算法。

例如，给定一个已经排序的数组，现在有多次询问，每次询问一个数字是否在这个数组中，返回True or False.
- 方法1： 每次扫描一遍数组，查看是否存在。
这个方法，每次查询的时间复杂度是: O(n)。

- 方法2：由于已经有序，可以使用二分查找的方法。
这个方法，每次查询的时间复杂度是: O(logn)。

- 方法3：将数组中的数存入Hashset。
这个方法，每次查询的时间复杂度是: O(1)。

可以看到，上述的三种方法是递进的，时间复杂度越来越小。

在面试中还有很多常见常用的方法，他们的时间复杂度并不是固定的，都需要掌握其时间复杂度的分析，要能够根据算法过程自己推算出时间复杂度。



# **二分法的模版**


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
                end = mid # if ask for first position 
                or return mid # if ask only found
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