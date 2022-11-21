# count_dp

````py
class Solution:
    def __init__(self):
        self.hmap = {}
        
    def count(self, coins, N, Sum):
        if Sum == 0:
            return 1
        if Sum <= 0:
            return 0
        if N <= 0:
            return 0
        
        if (N,Sum) in self.hmap:
            return self.hmap[(N,Sum)]
    
        included = self.count(coins, N, Sum-coins[N-1])
        excluded = self.count(coins, N-1, Sum)
        ans = included + excluded
        self.hmap[(N,Sum)] = ans
        return ans

````
