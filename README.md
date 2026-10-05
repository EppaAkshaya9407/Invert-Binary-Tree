# Invert-Binary-Tree
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def invertTree(self, root: TreeNode | None) -> TreeNode | None:
        if root is None:
            return None
        def inverse(root):
            if root is None:
                return
            root.left,root.right=root.right,root.left
            inverse(root.left)
            inverse(root.right)
        inverse(root)
        return root
