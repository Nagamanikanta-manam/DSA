<h2 >Solve it on <a href="https://www.geeksforgeeks.org/problems/k-th-largest-sum-contiguous-subarray/1">GFG</a></h2>
<h3><b>Solution</b></h3>
<code>
from typing import List
import heapq
</code>
<code>
class Solution:
  
    def kthLargest(self, N : int, K : int, Arr : List[int]) -> int:
        # code here
        heap = []
        for i in range(len(Arr)):
            s = 0
            for j in range(i,len(Arr)):
                s+=Arr[j]
                heapq.heappush(heap,s)
                if len(heap)>K:
                    heapq.heappop(heap)
        return heapq.heappop(heap)

</code>
