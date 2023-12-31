---
{"dg-publish":true,"permalink":"/20-29-software-engineering/23-technical-fundamentals/23-03-leetcode/5-longest-palindromic-substring/","tags":["dsa/string"],"created":"2023-10-10T07:01:10.026-05:00","updated":"2023-10-17T07:56:33.541-05:00"}
---

# 5 Longest Palindromic Substring
## Problem Statement
Given a string `s`, return _the longest palindromic substring_ in `s`.

**Input:** s = "babad"
**Output:** "bab"
**Explanation:** "aba" is also a valid answer.
## Approach
**BF:** Loop through every character in the string, get all substrings and check for being palindrome. O(N * N2)
**Optimized:** We can use a center based approach where we expand via a helper function from each characters center outward. The expand happens via a while function respecting the bounds from our pointers (incoming indexes) and checking if the two characters are the same. If so we assign the sliced string to longest. At the end of every iteration we decrease the left pointer and increase the right pointer.
## Solution
```javascript
const longestPalindrome = (s) => {
  let longest = "";

  const expandAroundCenter = (l, r) => {
    while (l >= 0 && r < s.length && s[l] === s[r]) {
      if (r - l + 1 > longest.length) {
        longest = s.slice(l, r + 1);
      }
      l--;
      r++;
    }
  };

  for (let i = 0; i < s.length; i++) {
    expandAroundCenter(i, i); // Odd-length palindromes
    expandAroundCenter(i, i + 1); // Even-length palindromes
  }

  return longest;
};
```
## Questions
## References
[LC](https://leetcode.com/problems/longest-palindromic-substring/description/)
## Related
[[20-29 Software Engineering/23 Technical Fundamentals/23.01 Data Structures/Strings\|Strings]]
[[20-29 Software Engineering/23 Technical Fundamentals/23.06 Techniques for DSA/Two Pointers\|Two Pointers]]