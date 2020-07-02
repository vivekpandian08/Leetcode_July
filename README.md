# Leetcode_July
#July_1 :  Arranging Coins



    class Solution:
    
    def arrangeCoins(self,n):
    
          res,i=0,0
          while res<=n:
            i+=1
            res+=i
          return i-1
          
          
          
          
 #July_2 : Binary Tree Level Order Traversal II
 
 
 
     # Definition for a binary tree node.
    # class TreeNode:
    #     def __init__(self, val=0, left=None, right=None):
    #         self.val = val
    #         self.left = left
    #         self.right = right
    class Solution:
         def levelOrderBottom(self, root: TreeNode) -> List[List[int]]:
            if root is None:
                return None

            result, current=[],[root]

            while current:
                next_level, value= [],[]
                for node in current:
                    value.append(node.val)
                    if node.left: 
                        next_level.append(node.left)
                    if node.right: 
                        next_level.append(node.right)

                current =next_level
                result.append(value)
            return result[::-1]
