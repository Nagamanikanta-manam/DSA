<h2>Solve it on <a href="https://www.geeksforgeeks.org/problems/bfs-traversal-of-graph/1">GFG</a></h2>
<code>
from typing import List
from queue import Queue
</code>
<code>
class Solution:
  
    #Function to return Breadth First Traversal of given graph.
    def bfsOfGraph(self, V: int, adj: List[List[int]]) -> List[int]:
      vi=[]
      ans=[]
      que=[]
      for i in range(V):
          vi.append(False)
      que.append(0)
      vi[0]=True
      
      while len(que)!=0:
           top=que.pop(0)
           
           ans.append(top)
           for i in adj[top]:
               if not vi[i]:
                   que.append(i)
                   vi[i]=True
      return ans
</code>
