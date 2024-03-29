
# 空间复杂度 - 内存中的栈空间与堆空间

什么是 stack overflow呢，我们首先要来了解几个基础概念：内存中的栈空间和堆空间是什么？

为了分析这种写法的空间复杂度，我们需要了解一下内存中，栈和堆占用了多少空间

## 内存中的栈空间与堆空间

我们通常所说的内存空间，包含了两个部分：
- 栈空间（Stack space）和
- 堆空间（Heap space）

当一个程序在执行的时候，操作系统为了让进程可以使用一些固定的不被其他进程侵占的空间用于进行函数调用，递归等操作，会开辟一个固定大小的空间（比如 8M）给一个进程使用。这个空间不会太大，否则内存的利用率就很低。这个空间就是我们说的栈空间，Stack space。

我们通常所说的栈溢出（Stack Overflow）是指在函数调用，或者递归调用的时候，开辟了过多的内存，超过了操作系统余留的那个很小的固定空间导致的。那么哪些部分的空间会被纳入栈空间呢？栈空间主要包含如下几个部分：

- 函数的参数与返回值
- 函数的局部变量

我们来看下面的这段代码：

Java:
```Java
public int f(int n) {
    int[] nums = new int[n];
    int sum = 0;
    for (int i = 0; i < n; i++) {
        nums[i] = i;
        sum += i;
    }
    return sum;
}
```
python:
```Python
def f(n):
    nums = [0]*n  # 相当于Java中的new int[n]
    sum = 0
    for i in range(n):
        nums[i] = i
        sum += i
    return sum
```    
C++:
```C++
int f(int n) {
   int *nums = new int[n];
    int sum = 0;
    for (int i = 0; i < n; i++) {
        nums[i] = i;
        sum += i;
    }
    return sum;
}
```

根据我们的定义，参数 n，最后的函数返回值f，局部变量 sum 都很容易的可以确认是放在栈空间里的。那么主要的难点在 nums。

这里 nums 可以理解为两个部分：

- 一个名字叫做 nums 的局部变量，他存储了指向内存空间的一个地址（Reference），这个地址也就是 4 个字节（32位地址总线的计算机，地址大小为 4 字节）

- new 出来的，一共有 n 个位置的整数数组，int[n]。一共有 4 * n 个字节。

这里 nums 这个变量本身，是存储在栈空间的，因为他是一个局部变量。但是 nums 里存储的 n 个整数，是存储在堆空间里的，Heap space。他并不占用栈空间，并不会导致栈溢出。

在大多数的编程语言中，特别是 Java, Python 这样的语言中，万物皆对象，基本上每个变量都包含了变量自己和变量所指向的内存空间两个部分的逻辑含义。

来看这个例子：

Java:
```java
public int[] copy(int[] nums) {
    int[] arr = new int[nums.length];
    for (int i = 0; i < nums.length; i++) {
        arr[i] = nums[i]
    }
    return arr;
}

public void main() {
    int[] nums = new int[10];
    nums[0] = 1;
    int[] new_nums = copy(nums);
}
```
Python:
```python
def copy(nums):
    arr = [0]*len(nums)  # 相当于Java中的new int[nums.length]
		for i in range(len(nums)):
        arr[i] = nums[i]
    return arr
		
# 用list comprehension实现同样功能
def copy(nums):
    arr = [x for x in nums]
    return arr
		
# 以下相当于Java中的main函数
if __name__ == "__main__":
    nums = [0]*10
    nums[0] = 1
    new_nums = copy(nums)
```
C++:
```C++
int* copy(int nums[], int length) {
    int *arr = new int[length];
    for (int i = 0; i < length; i++) {
        arr[i] = nums[i];
    }
    return arr;
}

int main() {
    int *nums = new int[10];
    nums[0] = 1;
    int *new_nums = copy(nums, 10);
	return 0;
}
```

在 copy 这个函数中，arr 是一个局部变量，他在 copy 函数执行结束之后就会被销毁。但是里面 new 出来的新数组并不会被销毁。

这样，在 main 函数里，new_nums 里才会有被复制后的数组。所以可以发现一个特点：

- ***栈空间里存储的内容，会在函数执行结束的时候被撤回***

简而言之可以这么区别栈空间和堆空间：

- ***new 出来的就放在堆空间，其他都是栈空间***

# 什么是递归深度

递归深度与栈溢出的关系:

## 什么是递归深度

递归深度就是递归函数在内存中，同时存在的最大次数。

例如下面这段求阶乘的代码：

Java:
```java
int factorial(int n) {
    if (n == 1) {
        return 1;
    }
    return factorial(n - 1) * n;
}
```
Python:
```python
def factorial(n):
    if n == 1:
        return 1
    return factorial(n-1) * n
```
C++:
```C++
int factorial(int n) {
    if (n == 1) {
        return 1;
    }
    return factorial(n - 1) * n;
}
```


当n=100时，递归深度就是100。一般来说，我们更关心递归深度的数量级，在该阶乘函数中递归深度是O(n)，而在二分查找中，递归深度是O(log(n))。在后面的教程中，我们还会学到基于递归的快速排序、归并排序、以及平衡二叉树的遍历，这些的递归深度都是(O(log(n))。注意，此处说的是递归深度，而并非时间复杂度。

## 太深的递归会内存溢出

首先，函数本身也是在内存中占空间的，主要用于存储传递的参数，以及调用代码的返回地址。

函数的调用，会在内存的栈空间中开辟新空间，来存放子函数。递归函数更是会不断占用栈空间，例如该阶乘函数，展开到最后n=1时，内存中会存在factorial(100), factorial(99), factorial(98) ... factorial(1)这些函数，它们从栈底向栈顶方向不断扩展。

当递归过深时，栈空间会被耗尽，这时就无法开辟新的函数，会报出stack overflow这样的错误。

所以，在考虑空间复杂度时，递归函数的深度也是要考虑进去的。

### Follow up：

尾递归：若递归函数中，递归调用是整个函数体中最后的语句，且它的返回值不属于表达式的一部分时，这个递归调用就是尾递归。（上例factorial函数满足前者，但不满足后者，故不是尾递归函数）

尾递归函数的特点是：在递归展开后该函数不再做任何操作，这意味着该函数可以不等子函数执行完，自己直接销毁，这样就不再占用内存。一个递归深度O(n)的尾递归函数，可以做到只占用O(1)空间。这极大的优化了栈空间的利用。

但要注意，这种内存优化是由编译器决定是否要采取的，不过大多数现代的编译器会利用这种特点自动生成优化的代码。在实际工作当中，尽量写尾递归函数，是很好的习惯。

而在算法题当中，计算空间复杂度时，建议还是老老实实地算空间复杂度了，尾递归这种优化提一下也是可以，但别太在意。
