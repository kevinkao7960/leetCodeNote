48 Rotate Image

*link*: https://leetcode.com/problems/rotate-image/ 

```python
class Solution:
    def rotate(self, matrix: List[List[int]]) -> None:
        """
        Do not return anything, modify matrix in-place instead.
        """
        n = len(matrix[0])
        # Transpose the matrix:
        """
        123    147
        456 -->258
        789    369
        """
        for i in range(0, n):
            for j in range(i, n):
                matrix[i][j], matrix[j][i] = matrix[j][i], matrix[i][j]
        
        # reflect the matrix with left and right
        """
        147    741
        258 -->852
        369    963
        """
        for i in range(0, n):
            for j in range(0, n // 2):
                matrix[i][j], matrix[i][-1-j] = matrix[i][-1-j], matrix[i][j]
```

### Explanation:
First do the trasnpose with the matrix along with the main diagonal.
Then reverse it from left to right

### Time Complexity
Each while loop we would took logn digits to calculate the square sum.
$$ O(n^2)$$

### Space Complexity
$$ O(1)$$

### Other solution
#### Rotate Groups of Four Cells: refer to LeetCode Solution

