[![](https://img.shields.io/github/stars/LeetCode-Top-Interview-150/LeetCode-Top-Interview-150?label=Stars&style=flat-square)](https://github.com/LeetCode-Top-Interview-150/LeetCode-Top-Interview-150)
[![](https://img.shields.io/github/forks/LeetCode-Top-Interview-150/LeetCode-Top-Interview-150?label=Fork%20me%20on%20GitHub%20&style=flat-square)](https://github.com/LeetCode-Top-Interview-150/LeetCode-Top-Interview-150/fork)

## 22\. Generate Parentheses

Medium

Given `n` pairs of parentheses, write a function to _generate all combinations of well-formed parentheses_.

**Example 1:**

**Input:** n = 3

**Output:** ["((()))","(()())","(())()","()(())","()()()"]

**Example 2:**

**Input:** n = 1

**Output:** ["()"]

**Constraints:**

*   `1 <= n <= 8`

## Solution

```golang
func generateParenthesis(n int) []string {
	result := []string{}
	generate("", 0, 0, n, &result)
	return result
}

func generate(s string, start, close, n int, result *[]string) {
	if len(s) == 2*n {
		*result = append(*result, s)
		return
	}
	if start < n {
		generate(s+"(", start+1, close, n, result)
	}
	if close < start {
		generate(s+")", start, close+1, n, result)
	}
}
```