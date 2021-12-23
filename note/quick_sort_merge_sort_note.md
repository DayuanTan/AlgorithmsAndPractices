
# Quick sort

1. pick a pivot p
   - pivot need the value, not index
   - pivot selection: random() > middle point (lower possibility to be worst case) > start or end point (higher possibility to be worst case). 
2. partition:
   - put <=p left
   - put >=p right
3. Note "==p" be both left and right. This is used to avoid all left or all right extreme worst case. 