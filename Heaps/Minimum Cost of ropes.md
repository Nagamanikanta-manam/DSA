<h2>Solve it on <a href="https://www.geeksforgeeks.org/problems/minimum-cost-of-ropes-1587115620/1">GFG</a></h2>
<h2>Solution</h2>
<code>
import heapq
</code>
<code>

#User function Template for python3

class Solution:

    #Function to return the minimum cost of connecting the ropes.
    def minCost(self,arr,n) :
        heapq.heapify(arr)
        ans=0
        ansf=0
        while len(arr)>1:
           ans=heapq.heappop(arr)+heapq.heappop(arr)
           ansf=ansf+ans
           heapq.heappush(arr,ans)
        return ansf
</code>
