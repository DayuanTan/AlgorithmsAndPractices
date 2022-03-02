# If ask for spefific plans 求具体方案 O(n^3)


```
Input: nums = [2,2,3,4]
Explanation: Valid combinations are: 
2,3,4 (using the first 2)
2,3,4 (using the second 2)
2,2,3
```

- Have to count one by one. 
- E.g. ask for all valid triangles and specific combination, it's O(n^3)


# If ask for plan count 求方案总数 可批量处理降维到 O(n^2)


```
Input: nums = [2,2,3,4]
Output: 3
```

- Can batch process similar situations. 
- If array[A] + array[B] > array[C] then array[any elem after A] + array[B] > array[C]


# Summary 求具体方案 vs 求方案数

If ask for specific plan combinations O(n^3)

求**具体方案**只能一个个数出来，时间复杂度 O(n^3) 

If ask for plans count and cannot repeat O(n^3)

求**不可以重复**的方案数也只能一个个数 

If ask for plans count but can repeat O(n^2)

求**可以重复**的方案数可以批量累加，时间复杂度 O(n^2)