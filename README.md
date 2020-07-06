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


#July_3: Prison Cells After N Days

        class Solution:
    def prisonAfterNDays(self, cells: List[int], N: int):
        record=[]
        seen,count=0,0
        while seen==0:
            temp=[]
            temp.append(0)
            for i in range(1,7):
                if cells[i-1]==cells[i+1]:
                    val=1
                else:
                    val=0
                temp.append(val)
            temp.append(0)
            cells=tuple(temp)
            if cells in record:
                seen=1
            else:
                record.append(cells)
                count+=1
        
        return record[(N-1)%count]

# July_4 : Ugly Number II

        class Solution:
            def nthUglyNumber(self, n):
                ugly = [1]
                i2, i3, i5 = 0, 0, 0
                while n > 1:
                    u2, u3, u5 = 2 * ugly[i2], 3 * ugly[i3], 5 * ugly[i5]
                    mini = min(u2, u3, u5)
                    if mini == u2:
                        i2 += 1
                    if mini == u3:
                        i3 += 1
                    if mini == u5:
                        i5 += 1
                    ugly.append(mini)
                    n -= 1
                return ugly[-1]
                
#July_5: Hamming Distance:

    class Solution:
        def hammingDistance(self, x: int, y: int) -> int:
            res = 0
            for i in bin(x^y)[2:]:
                if i == '1':
                    res += 1
            return res
                
                
