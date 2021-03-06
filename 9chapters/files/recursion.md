- Part 1 递归三要素 Recursion 3 key parts 
- Part 2 递归调用栈 (内存的堆栈 函数调用栈) Recursion with stack and heap 
- Part 3 值传递与引用传递 Pass by value vs Pass by reference 
- Part 4 综合训练 More practices 


# 递归定义

- 当函数直接或者间接调⽤⾃⼰时，则发⽣了递归.
- 递归的定义: 参⻅ "递归的定义".
- 递归缩写:

    • Bing - Bing Is Not Google

    • GNU - GNU's Not Unix

    • PHP - PHP: Hypertext Preprocessor

# 递归三要素

- 递归的定义：接受什么参数，返回什么值，代表什么意思

- 递归的拆解：每次递归都是为了让问题规模变⼩

- 递归的出⼝：必须有⼀个明确的结束条件

=> 得到⼀个可供其他函数调⽤的递归函数

## 例子 斐波那契数列

- 定义: 斐波那契数列指的是这样⼀个数列 0, 1, 1, 2, 3, 5, 8, 13, 21, 34........这个数列从第3项 开始, 每⼀项都等于前两项之和.

- 关系式: F i= F i−1 + F i−2

<img src="recursion1.png">

[1807. Fibonacci easy](../lintcode/1807.Fibonacci_easy.md)

[366. Fibonacci](../lintcode/366.Fibonacci.md)

[771. Double Factorial](../lintcode/771.Double_Factorial.md)

[1333. Reverse Bits](../lintcode/1333.Reverse_Bits.md)

[97. Maximum Depth of Binary Tree] https://www.lintcode.com/problem/maximum-depth-of-binary-tree/description 

# 内存中的堆栈 Stack and Heap in Memory

- 递归深度太⼤容易 “爆栈” Stack Overflow, Segment Fault
  - 堆空间:
  - 存放 new 得到的对象
  - ⽆限制 (剩余内存⼤⼩)
- 栈空间:
  - 存放对象的引⽤, 值类型变量(Java), 数组(C/C++), 以及函数调⽤信息
  - 有限制, ⼀般很⼩, MB量级

# 函数调用栈

- 想象⼀个 “圆筒”, 调⽤的函数需要放到筒⾥
- 第⼀个进⼊ “圆筒” 的是 main() 函数
- 每发⽣⼀次新的函数调⽤, 就会有⼀个新函数进⼊ “圆筒”
- 正在执⾏的就是最上⾯的函数
- ⼀个函数执⾏完毕, 就会被拿出来
- ⼀个函数占⽤ “圆筒” 的空间与参数, 局部变量的数量有关

## Stack overflow

- Java 
  - About 18615 recursion delpth. (18073 recursion delpth when more varibales)
- C/C++ 
  - About 262009 recursion delpth. (174672 recursion delpth when more varibales)
- Python 
  - About 998 recursion delpth. (998 recursion delpth when more varibales)
  - Not stackoverflow. 
  - “RuntimeError: maximum recursion depth exceeded”. 
  - Inside the setting of python, the max levels of recursion is set as about 999. 



