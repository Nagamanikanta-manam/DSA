<h2>Solve it on <a href="https://www.geeksforgeeks.org/problems/detect-cycle-in-an-undirected-graph/1">GFG</a></h2>
<h3>Solution</h3>
<code>
  from typing import List
</code>
<code>
  class Solution:
  
    def __init__(self):
        self.visited=[]
        self.parent=[]
    def isCy(self,V,adj,c):
        self.visited[c]=True
        self.parent[c]=None
        q=[]
        q.append(c)
        while len(q)!=0:
            t=q.pop()
            for i in adj[t]:
               if self.visited[i]==True and i!=self.parent[t]:
                   return True
               elif self.visited[i]==False:
                   q.append(i)
                   self.visited[i]=True
                   self.parent[i]=t
        return False
                   
	def isCycle(self, V: int, adj: List[List[int]]) -> bool:
	     self.visited=[False]*V
	     self.parent=[None]*V
	     for i in range(V):
	        if self.visited[i]==False:
	            if self.isCy(V,adj,i):
	                return 1
	     return 0
</code>
