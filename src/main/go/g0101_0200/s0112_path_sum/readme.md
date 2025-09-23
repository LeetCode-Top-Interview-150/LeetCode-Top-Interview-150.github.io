[![](https://img.shields.io/github/stars/LeetCode-Top-Interview-150/LeetCode-Top-Interview-150?label=Stars&style=flat-square)](https://github.com/LeetCode-Top-Interview-150/LeetCode-Top-Interview-150)
[![](https://img.shields.io/github/forks/LeetCode-Top-Interview-150/LeetCode-Top-Interview-150?label=Fork%20me%20on%20GitHub%20&style=flat-square)](https://github.com/LeetCode-Top-Interview-150/LeetCode-Top-Interview-150/fork)

## 112\. Path Sum

Easy

Given the `root` of a binary tree and an integer `targetSum`, return `true` if the tree has a **root-to-leaf** path such that adding up all the values along the path equals `targetSum`.

A **leaf** is a node with no children.

**Example 1:**

![](https://assets.leetcode.com/uploads/2021/01/18/pathsum1.jpg)

**Input:** root = [5,4,8,11,null,13,4,7,2,null,null,null,1], targetSum = 22

**Output:** true 

**Example 2:**

![](https://assets.leetcode.com/uploads/2021/01/18/pathsum2.jpg)

**Input:** root = [1,2,3], targetSum = 5

**Output:** false 

**Example 3:**

**Input:** root = [1,2], targetSum = 0

**Output:** false 

**Constraints:**

*   The number of nodes in the tree is in the range `[0, 5000]`.
*   `-1000 <= Node.val <= 1000`
*   `-1000 <= targetSum <= 1000`

## Solution

```golang
/**
 * Definition for a binary tree node.
 * type TreeNode struct {
 *     Val int
 *     Left *TreeNode
 *     Right *TreeNode
 * }
 */
func hasPathSum(root *TreeNode, sum int) bool {
	if root == nil {
		return false
	}
	if sum == root.Val && root.Left == nil && root.Right == nil {
		return true
	}
	return hasPathSum(root.Left, sum-root.Val) || hasPathSum(root.Right, sum-root.Val)
}
```