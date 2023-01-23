# Intuition
<!-- Describe your first thoughts on how to solve this problem. -->
The goal of the solution is to detect any duplicates in the array. Not to produce back the duplicates to other as a result.

Iteration for small size array is acceptable but large array could be ineeficient. It could be O(n^2) time complexity. 

I opted to use built in HashSet<T> where I could insert the array elements inside the HashSet<T> and let the built-in function to eliminate the duplicates.

Then I could compare length of array with the count of HashSet<T> to detect whether the array has duplicates

# Approach
<!-- Describe your approach to solving the problem. -->
1 - Convert the array to HashSet<int>
2 - Compare the the length of the array with the HashSet<int> count
3 - if the length of the array is not equal to the count of the HashSet<int>, return true
4 - Else, return false.

# Complexity
- Time complexity:
<!-- Add your time complexity here, e.g. $$O(n)$$ -->
O(1) for Add and Lookup, O(n) if size of HashSet<int> is not more than 2 billion then it could increase the capacity and the O(n) should be consider. Fetching values between heap and stack could also affect the performance. Instead we could use C/C++ for small array size and use pointers to heap memory for better solution.

- Space complexity:
<!-- Add your space complexity here, e.g. $$O(n)$$ -->
As we convert the array to new HashSet<int>, it will increase the memory usage. O(n), where n = 2. We could use constraint to save the heap memory as both Array abd HeashSet<T> are reference type.

# Code C#
```
public class Solution {
    public bool ContainsDuplicate(int[] nums) {
        HashSet<int> set = new HashSet<int>(nums);
        if (nums.Length != set.Count) {
            return true;
        }
        return false;
    }
}
```
# Code Python3
```
class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        distinctSet = set(nums)
        if (len(distinctSet) != len(nums)):
            return True
        return False

```
