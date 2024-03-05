<h2>Solve it on <a href="https://www.geeksforgeeks.org/problems/topological-sort/1">GFG</a></h2>
<h3>Solution:</h3>
<code>
  class Solution:
  
    def __init__(self):
        self.vi=[]
        self.st=[]
    #Function to return list containing vertices in Topological order.
    def dfs(self,v,adj):
        self.vi[v]=True
        for i in adj[v]:
            if self.vi[i]==False:
                self.dfs(i,adj)
        self.st.append(v)
        
    def topoSort(self, V, adj):
        #print(adj)
        self.vi=[False]*V
        for i in range(V):
            if self.vi[i]==False:
                self.dfs(i,adj)
        k=self.st[::-1]
        #print(k)   
        return k

</code>
