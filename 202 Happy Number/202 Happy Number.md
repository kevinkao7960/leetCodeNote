202 Happy Number

*link*: https://leetcode.com/problems/happy-number/

```python
class Solution:
    def isHappy(self, n: int) -> bool:
        result = False
        tmp = [int(x) for x in str(n)]
        
        history = [n]
        
        while 1:
            cur = 0
            for i in tmp:
                cur += i * i
            
            if cur == 1:
                result = True
                break
            
            if cur in history:
                break
            else:
                history.append(cur)
                
            tmp = [int(x) for x in str(cur)]
        
        return result
```

### Explanation:
History is an array to record the numbers in the whole process.
If there's the same integer value which has been reocrded in history during the while loop, then return false

### Time Complexity
Each while loop we would took logn digits to calculate the square sum.
$$ O(log n + loglog n + logloglog n + ...)$$
$$ O(log n) $$

### Space Complexity
$$ O(log n + loglog n + logloglog n + ... )$$
$$ O(log n) $$

### Other solution
#### HashSet: refer to LeetCode Solution
#### Floyd's Cycle-Finding Algorithm: refer to LeetCode Solution

