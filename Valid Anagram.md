# Intuition
Two strings are anagrams if they contain the same characters with the same frequencies.

# Approach
Compare the frequency count of each character in both strings using dictionaries. If the lengths differ, they cannot be anagrams. Otherwise, build frequency maps for both and compare them.

# Complexity
- Time complexity: `O(n)` - Iterate over the strings of length n once.

- Space complexity: `O(1)` - Maximum 26 lowercase English letters, so constant space.


# Code
```python3 []
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        if len(s) != len(t):
            return False

        countS, countT = {}, {}

        for i in range(len(s)):
            countS[s[i]] = 1 + countS.get(s[i], 0)
            countT[t[i]] = 1 + countT.get(t[i], 0)
        return countS == countT
```
