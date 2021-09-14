31 Next Permutation

*link*: https://leetcode.com/problems/next-permutation/

```python
class Solution:
    def nextPermutation(self, nums: List[int]) -> None:
        """
        Do not return anything, modify nums in-place instead.
        """
        # find the pivot which nums[i + 1] > nums[i]
        i = len(nums) - 2
        while (i >= 0) and (nums[i+1] <= nums[i]):
            i -= 1
        
        # find the number just larger than nums[i]
        j = i
        while (j + 1 < len(nums)) and (nums[j+1] > nums[i]):
            j += 1
        
        # swap nums[i] and nums[j]
        if i >= 0 and j >= 0:
            nums[i], nums[j] = nums[j], nums[i]
        
        # reverse the right part of nums[i]
        start = i + 1
        end = len(nums) - 1
        while start < end:
            nums[start], nums[end] = nums[end], nums[start]
            start += 1
            end -= 1
```

### Explanation:
As the picture illusttrated by [TWiStErRob](https://leetcode.com/problems/next-permutation/discuss/13994/Readable-code-without-confusing-ij-and-with-explanation).

#### Step 1: Find the pivot pivot which nums[i + 1] > nums[i]
![e56a4c46f0e7e5c27df818d060270d27.png](image/f4e27fbc130542b98b6a766b37f15cc0.png)

#### Step 2: Find the number just larger than nums[i] (pivot in Step 1)
![ae82bc86bf4b1d37bde31690286114c6.png](image/bcef9d4850b14f30abe16603b7d992b4.png)

#### Step 3: Swap nums[i] (pivot in Step 1) and nums[j] (the number in Step 2)
![65b757b26cc93fb36a8a2294c50a64aa.png](image/1df07ff0a0ec4401958ea1eac2fb41a0.png)

#### Step 4: Reverse the part right after the pivot.
![785f2e17296bab9f302590ebfa9b3a28.png](image/e90163d59b2940c4b0f0320edac0fe95.png)


### Time Complexity
$$ O(n) $$

### Space Complexity
$$ O(1)$$

### Other solution or reference
1. Shared by [TWiStErRob](https://leetcode.com/problems/next-permutation/discuss/13994/Readable-code-without-confusing-ij-and-with-explanation)

