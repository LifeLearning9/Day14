# Day14 Given a m x n 2D matrix, print all elements in spiral order starting from the top-left corner.
First go left → right (top row),
Then top → bottom (right column),
Then right → left (bottom row),
Then bottom → top (left column),
Repeat until all elements are visited.

**Test Cases**

Input:

3 3
1 2 3
4 5 6
7 8 9

Output:

1 2 3 6 9 8 7 4 5

**Intuition**

1. We "peel" the matrix layer by layer.

2. Imagine the matrix as an onion → remove one boundary (top row, right column, bottom row, left column) at a time.

3. After each peel, move the boundaries inward (top++, bottom--, left++, right--).

4. Continue until all elements are covered.


**Algorithm Flow**
1.Initialize four boundaries:
  top = 0
  bottom = m-1
  left = 0
  right = n-1
2. While top <= bottom and left <= right:
   Traverse top row → from left to right, then top++.
   Traverse right column → from top to bottom, then right--.
   If top <= bottom, traverse bottom row → from right to left, then bottom--.
   If left <= right, traverse left column → from bottom to top, then left++.
7. Repeat until all elements are printed.

**Complexity Analysis**
Time Complexity: O(m * n)  Each element is visited exactly once.
Space Complexity: O(1)
Only boundary variables (top, bottom, left, right) are used, no extra space (ignoring input matrix).
