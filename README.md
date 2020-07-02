# Leetcode_July
#July_1 :  Arranging Coins



class Solution:
    
    def arrangeCoins(self,n):
    
          res,i=0,0
          while res<=n:
            i+=1
            res+=i
          return i-1
