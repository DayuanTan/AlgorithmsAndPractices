# Part 1: Two Sum

## Use hashtable

- Time complexity O(n)
- Space complexity O(n)

## Use sort + 2 pointers


- Time complexity O(nlogn)
- Space complexity O(1) 




Note space complexity means the extra needed space, excluding input and output.

## follow up 1

- If it is sorted, which is better?
  - 2 pointers > hashtable

## follow up 2
- If ask you return the indices of the two found elements, which is better?
  - hashtable > 2 pointers

------

# Part 2: Two Sum Data Structure Design

||2 pointers just add|2 pointers add and keep sorted|hashtable|
|-|-|-|-|
|AddNumber|O(1)|O(n)|O(1)|
|FindTwoSum|O(nlogn)|O(n)|O(n)|

# Add() - Two Sum Data Structure Design

## Use 2 pointers 
- Just add: Time complexity O(1). (This is better for the situation wherer there are much more add than find.)
- Add and keep sorted: Insert sorting: O(n)

## Use hashtable 
- Time complexity O(1) 



# Find() - Two Sum Data Structure Design

## Use 2 pointers
- Just add in Add(): Time complexity O(nlogn)
- Add and keep sorted in Add(): O(n)

## Use hashtable
- Time complexity O(n) 

# Follow up: What if keep the data sorted when adding? Will this better?

## Opt 1. Binary search + Array Insert
- Time complexity O(logn) + O(n) = O(n)
  - Search (find place to insert) O(logn)
  - But insert O(n)

## Opt 2. Binary search + Linked List Insert
(Binary search is base on array, here just for discussion)
- Time complexity O(n) + O(1) = O(n)
  - Search (find place to insert) O(n)
  - But insert O(1)

## Opt 3. Heap 

- Heap is a tree structure. Elements are not sorted.
- Add/Insert O(logn)
- Find: need to get all elements (which takes O(nlogn)) and then put them all into a sorted array and then do two sum. 

## Opt 4. TreeMap (Red-Black Tree)

- Add O(logn)
- FindTwoSum O(n).  Need firstly Inorder Traversal to get all elements (the result is sorted already) which  takes O(n).
