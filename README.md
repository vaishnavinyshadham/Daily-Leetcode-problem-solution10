# Daily-Leetcode-problem-solution10
PROBLEM

Given a binary tree with the following rules:

root.val == 0
For any treeNode:
If treeNode.val has a value x and treeNode.left != null, then treeNode.left.val == 2 * x + 1
If treeNode.val has a value x and treeNode.right != null, then treeNode.right.val == 2 * x + 2
Now the binary tree is contaminated, which means all treeNode.val have been changed to -1.

Implement the FindElements class:

FindElements(TreeNode* root) Initializes the object with a contaminated binary tree and recovers it.
bool find(int target) Returns true if the target value exists in the recovered binary tree.

Intuition

Recover the contaminated binary tree and efficiently supports the find operation using a unordered_set for fast lookups

Approach

Tree Recovery:

The recover function is a recursive function that assigns correct values to nodes based on the given rules.
It starts with the root node, setting its value to 0.
It recursively assigns values to left (2 * parent + 1) and right (2 * parent + 2) child nodes.
The values are stored in an unordered_set for efficient O(1) average-time complexity lookup.
Finding Elements:

The find function simply checks if the target exists in the unordered_set, returning true if found and false otherwise.

Complexity

Time complexity:

Recovery : O(n)
Finding query : O(1)

Space complexity:

Recovery : O(n)
Finding query : O(n)
 
