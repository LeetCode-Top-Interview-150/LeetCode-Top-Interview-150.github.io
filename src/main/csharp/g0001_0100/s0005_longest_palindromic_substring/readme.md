[![](https://img.shields.io/github/stars/LeetCode-Top-Interview-150/LeetCode-Top-Interview-150?label=Stars&style=flat-square)](https://github.com/LeetCode-Top-Interview-150/LeetCode-Top-Interview-150)
[![](https://img.shields.io/github/forks/LeetCode-Top-Interview-150/LeetCode-Top-Interview-150?label=Fork%20me%20on%20GitHub%20&style=flat-square)](https://github.com/LeetCode-Top-Interview-150/LeetCode-Top-Interview-150/fork)

## 5\. Longest Palindromic Substring

Medium

Given a string `s`, return _the longest palindromic substring_ in `s`.

**Example 1:**

**Input:** s = "babad"

**Output:** "bab" **Note:** "aba" is also a valid answer. 

**Example 2:**

**Input:** s = "cbbd"

**Output:** "bb" 

**Example 3:**

**Input:** s = "a"

**Output:** "a" 

**Example 4:**

**Input:** s = "ac"

**Output:** "a" 

**Constraints:**

*   `1 <= s.length <= 1000`
*   `s` consist of only digits and English letters.

## Solution

```csharp
public class Solution {
    public string LongestPalindrome(string s) {
        if (s.Length == 1) return s;
        int res = 0;
        int l = 0;
        int r = 0;
        int len = s.Length;
        for (int i = 0; i < len; i ++) {
            for (int diff = 1; i - diff + 1 >= 0 && i + diff < len; diff ++) {
                if (s[i - diff + 1] != s[i + diff]) break;
                else if (res < diff * 2) {
                    res = diff * 2;
                    l = i - diff + 1;
                    r = i + diff;
                }
            }
        }
        for (int i = 0; i < len; i ++) {
            for (int diff = 1; i - diff >= 0 && i + diff < len; diff ++) {
                if (s[i - diff] != s[i + diff]) break;
                else if (res < diff * 2 + 1) {
                    res = diff * 2 + 1;
                    l = i - diff;
                    r = i + diff;
                }
            }
        }
        return s.Substring(l, r - l + 1);
    }
}
```