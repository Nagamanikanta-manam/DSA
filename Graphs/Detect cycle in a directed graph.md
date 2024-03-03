<h2>Solve it on <a href="https://www.geeksforgeeks.org/problems/detect-cycle-in-a-directed-graph/1?utm_source=geeksforgeeks&utm_medium=ml_article_practice_tab&utm_campaign=article_practice_tab">GFG</a></h2>
<h3>Solution:</h3>
<code>
  class Solution:
  
    def __init__(self):
        self.vi=[]
        self.dfs=[]
    #Function to detect cycle in a directed graph.
    def isC(self,V,adj,ver):
        self.vi[ver]=True
        self.dfs[ver]=True
        for i in adj[ver]:
            if self.vi[i]==False:
                if self.isC(V,adj,i):
                    return True
            elif self.dfs[i]==True:
                return True
        self.dfs[ver]=False
        return False
     
    def isCyclic(self, V, adj):
        self.vi=[False]*V
        self.dfs=[False]*V
        for i in range(V):
              if self.vi[i]==False:
                  if self.isC(V,adj,i):
                      return True
        return False
</code>
