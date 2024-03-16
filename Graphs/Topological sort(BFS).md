<h2>Solve it on <a href="https://www.geeksforgeeks.org/problems/topological-sort/1">GFG</a></h2>
<code>
  class Solution:
    
    #Function to return list containing vertices in Topological order.
    def topoSort(self, V, adj):
            
             ino=[0]*V
             
             
             for i in adj:        
                   for j in i:
                       ino[j]=ino[j]+1
             qu=[]
             ans=[]
             for i in range(V):
                 if ino[i]==0:
                     qu.append(i)
             #print(qu)
             while(len(qu)!=0):
                 fr=qu[0]
                 qu.pop(0)
                 ans.append(fr)
                 for i in adj[fr]:
                     ino[i]=ino[i]-1
                     if ino[i]==0:
                         qu.append(i)
             #print(ans)      
             return ans
</code>
