[![](https://img.shields.io/github/stars/LeetCode-Top-Interview-150/LeetCode-Top-Interview-150?label=Stars&style=flat-square)](https://github.com/LeetCode-Top-Interview-150/LeetCode-Top-Interview-150)
[![](https://img.shields.io/github/forks/LeetCode-Top-Interview-150/LeetCode-Top-Interview-150?label=Fork%20me%20on%20GitHub%20&style=flat-square)](https://github.com/LeetCode-Top-Interview-150/LeetCode-Top-Interview-150/fork)

## 125\. Valid Palindrome

Easy

A phrase is a **palindrome** if, after converting all uppercase letters into lowercase letters and removing all non-alphanumeric characters, it reads the same forward and backward. Alphanumeric characters include letters and numbers.

Given a string `s`, return `true` _if it is a **palindrome**, or_ `false` _otherwise_.

**Example 1:**

**Input:** s = "A man, a plan, a canal: Panama"

**Output:** true

**Explanation:** "amanaplanacanalpanama" is a palindrome. 

**Example 2:**

**Input:** s = "race a car"

**Output:** false

**Explanation:** "raceacar" is not a palindrome. 

**Example 3:**

**Input:** s = " "

**Output:** true

**Explanation:** s is an empty string "" after removing non-alphanumeric characters. Since an empty string reads the same forward and backward, it is a palindrome. 

**Constraints:**

*   <code>1 <= s.length <= 2 * 10<sup>5</sup></code>
*   `s` consists only of printable ASCII characters.

## Solution

```typescript
function isPalindrome(s: string): boolean {
    if (s.length < 2) {
        return true
    }
    let sFormated = s.toLowerCase().replace(/[^a-zA-Z0-9]/g, '')
    let reversed = sFormated.split('').reverse().join('').replace(',', '')
    return sFormated === reversed
}

export { isPalindrome }
```