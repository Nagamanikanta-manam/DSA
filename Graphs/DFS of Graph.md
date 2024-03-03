<h2>Solve It on <a href="https://www.geeksforgeeks.org/problems/depth-first-traversal-for-a-graph/1">GFG</a></h2>
<h3>Solution:</h3>
<code>
  class Solution:
  
    def __init__(self):
        self.visited=[]
        self.ans=[]
    def dfs(self,V,adj,ver):
        
        self.ans.append(ver)
        self.visited[ver]=True
        for i in adj[ver]:
            
            if self.visited[i]==False:
                self.dfs(V,adj,i)
        
    def dfsOfGraph(self, V, adj):
        #print(adj)
        #print(V)
        self.visited=[False]*V
        self.dfs(V,adj,0)
        return self.ans
</code>
