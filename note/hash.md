哈希表的原理

哈希表原理、冲突、扩容



# HashMap和HashSet的区别？

java最基本的两种数据结构：数组和链表的区别：
- 数组易于快速读取（通过for循环），不便存储（数组长度有限制）；
- 链表易于存储，不易于快速读取。
- 哈希表的出现是为了解决链表访问不快速的弱点，哈希表也称散列表。


HashSet是通过HashMap来实现的，HashMap的输入参数有Key、Value两个组成，在实现HashSet的时候，保持HashMap的Value为常量，相当于在HashMap中只对Key对象进行处理。

HashMap的底层是一个数组结构，数组中的每一项对应了一个链表，这种结构称“链表散列”的数据结构，即数组和链表的结合体；也叫散列表、哈希表。

了解HashMap和HashSet这样两个不同存储结构的区别，要熟知他们的存储过程

# 一、HashMap存储对象的过程
1. 对HashMap的Key调用hashCode()方法，返回int值，即对应的hashCode；
2. 把此hashCode作为哈希表的索引，查找哈希表的相应位置，若当前位置内容为NULL，则把HashMap的Key、Value包装成Entry数组，放入当前位置；
3. 若当前位置内容不为空，则继续查找当前索引处存放的链表，利用equals方法，找到Key相同的Entry数组，则用当前Value去替换旧的Value；
4. 若未找到与当前Key值相同的对象，则把当前位置的链表后移（Entry数组持有一个指向下一个元素的引用），把新的Entry数组放到链表表头；

# 二、HashSet存储对象的过程
1. 往HashSet添加元素的时候，HashSet会先调用元素的hashCode方法得到元素的哈希值 ，
2. 然后通过元素 的哈希值经过移位等运算，就可以算出该元素在哈希表中 的存储位置。
   - 情况1： 如果算出元素存储的位置目前没有任何元素存储，那么该元素可以直接存储到该位置上。
   - 情况2： 如果算出该元素的存储位置目前已经存在有其他的元素了，那么会调用该元素的equals方法与该位置的元素再比较一次，如果equals返回的是true，那么该元素与这个位置上的元素就视为重复元素，不允许添加，如果equals方法返回的是false，那么该元素运行添加。

# 总结：HashSet和HashMap的区别
|HashMap|	HashSet|
|-|-|
|实现了Map接口|	实现Set接口|
|存储键值对|	仅存储对象|
|调用put（）向map中添加元素	|调用add（）方法向Set中添加元素|
|HashMap使用键（Key）计算Hashcode	|HashSet使用成员对象来计算hashcode值，对于两个对象来说hashcode可能相同，所以equals()方法用来判断对象的相等性，如果两个对象不同的话，那么返回false|
||

# 哈希表主要考点
哈希表（Java 中的 HashSet / HashMap，C++ 中的 unordered_map，Python 中的 dict）是面试中非常常见的数据结构。它的主要考点有两个：
1. 是否会灵活的使用哈希表解决问题
2. 是否熟练掌握哈希表的基本原理

HashSet实现了Set接口，其内部不允许出现重复的值，如果我们将一个对象存入HashSet，必须重写equals()和hashCode()方法，这样才能确保集合中不存在同一个元素。HashSet的内部是无序的，因此不能使用 hashset.get(index) 来获取元素。

HashMap实现了Map接口，其内容是键值对的映射（key->value），不允许出现相同的键（key）。在查询的时候会根据给出的键来查询对应的值。

我们可以认为，HashSet和HashMap增查操作的时间复杂度都是常数级的。


# 冲突（Collision）

冲突（Collision），是说两个不同的 key 经过哈希函数的计算后，得到了两个相同的值。解决冲突的方法，主要有两种：

1. 开散列法（Open Hashing）。是指哈希表所基于的数组中，每个位置是一个 Linked List 的头结点。这样冲突的 <key, value> 二元组，就都放在同一个链表中。
2. 闭散列法（Closed Hashing）。是指在发生冲突的时候，后来的元素，往下一个位置去找空位。


[more collision](hash/)

# capacity, load factor

Java HashMap: default initial capacity (16) and the default load factor (0.75).

HashSet: the backing HashMap instance has default initial capacity (16) and load factor (0.75).


