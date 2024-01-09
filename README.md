# Leaf-Similar-Trees
Consider all the leaves of a binary tree, from left to right order, the values of those leaves form a leaf value sequence.

class Solution(object):
    def leafSimilar(self, root1, root2):
        """
        :type root1: TreeNode
        :type root2: TreeNode
        :rtype: bool
        """

        def findleaf(root):
            left = []
            right = []
            if root.left == None and root.right == None:
                return [root.val]
            else:
                if root.left != None:
                    left = findleaf(root.left)
                if root.right != None:
                    right = findleaf(root.right)
                return (left + right)

        leaf1 = findleaf(root1)
        leaf2 = findleaf(root2)

        return leaf1 == leaf2
