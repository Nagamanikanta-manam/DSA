<h2>Solve it on <a href="https://www.geeksforgeeks.org/problems/shortest-path-in-undirected-graph/1">GFG</a></h2>
<h3>Solution:</h3>
<code>
  
class Solution:

    def __init__(self):
        self.visited=[]
        self.topo=[]
    def dfs(self,i,adj):
        self.visited[i]=True
        for j in adj[i]:
            if self.visited[j[0]]==False:
                self.dfs(j[0],adj)
        self.topo.append(i)
            
    def shortestPath(self, n : int, m : int, edges : List[List[int]]) -> List[int]:
        adj=[]
        for i in range(n):
             adj.append([])
        for i in edges:
            parent=i[0]
            child=i[1]
            weight=i[2]
            adj[parent].append([child,weight])
        self.visited=[False]*n
        for i in range(n):
            if self.visited[i]==False:
                self.dfs(i,adj)
        src=0
        d=[float('inf')]*n
        d[src]=0
        while len(self.topo)!=0:
            top=self.topo[-1]
            self.topo.pop()
            if d[top]!=float('inf'):
                for i in adj[top]:
                    if d[top]+i[1]<d[i[0]]:
                        d[i[0]]=d[top]+i[1]
            
        for i in range(n):
            if d[i]==float('inf'):
                d[i]=-1
                 
        return d
</code>
