[![](https://img.shields.io/github/stars/LeetCode-Top-Interview-150/LeetCode-Top-Interview-150?label=Stars&style=flat-square)](https://github.com/LeetCode-Top-Interview-150/LeetCode-Top-Interview-150)
[![](https://img.shields.io/github/forks/LeetCode-Top-Interview-150/LeetCode-Top-Interview-150?label=Fork%20me%20on%20GitHub%20&style=flat-square)](https://github.com/LeetCode-Top-Interview-150/LeetCode-Top-Interview-150/fork)

## 172\. Factorial Trailing Zeroes

Medium

Given an integer `n`, return _the number of trailing zeroes in_ `n!`.

Note that `n! = n * (n - 1) * (n - 2) * ... * 3 * 2 * 1`.

**Example 1:**

**Input:** n = 3

**Output:** 0

**Explanation:** 3! = 6, no trailing zero. 

**Example 2:**

**Input:** n = 5

**Output:** 1

**Explanation:** 5! = 120, one trailing zero. 

**Example 3:**

**Input:** n = 0

**Output:** 0 

**Constraints:**

*   <code>0 <= n <= 10<sup>4</sup></code>

**Follow up:** Could you write a solution that works in logarithmic time complexity?

## Solution

```golang
func trailingZeroes(n int) int {
	base := 5
	count := 0
	for n >= base {
		count += n / base
		base = base * 5
	}
	return count
}
```