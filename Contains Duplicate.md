# Intuition
The key idea is: **if any number appears more than once, we should be able to detect it during one pass through the list**.  

Instead of comparing every number with every other (which is slow), we use a **set**. A set automatically handles uniqueness and gives us **fast lookups (O(1))**. So, as we go through the list:

- If the number **is already in the set**, it means we’ve seen it before → it's a duplicate.
- If not, we **add it to the set** and keep going.

This is more efficient than sorting or brute force comparison.


# Approach
1. Create an empty `set()` to store numbers we've seen.
2. Loop over the input list `nums`.
3. For each number:
   - Check if it exists in the set.
     - If yes → return `True` (duplicate found).
     - If no → add it to the set.
4. If the loop ends without returning, return `False` (no duplicates found).

This ensures:
- We only loop once over the list.
- Each lookup and insertion into the set is constant time.


# Complexity
- Time complexity: `O(n)` – one pass through the list with constant-time set operations.
- Space complexity:`O(n)` – in the worst case, all elements are unique and stored in the set.


# Code
```python3 []
class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        hashset = set()
        for i in nums:
            if i in hashset:
                return True
            hashset.add(i)
        return False
```
