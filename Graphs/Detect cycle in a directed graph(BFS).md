<h2>Solve it on <a href="https://www.geeksforgeeks.org/problems/detect-cycle-in-a-directed-graph/1">GFG</a></h2>
<code>
  class Solution:
    
    #Function to detect cycle in a directed graph.
    def isCyclic(self, V, adj):
             ino=[0]*V
             
             
             for i in adj:        
                   for j in i:
                       ino[j]=ino[j]+1
             qu=[]
             ans=0
             for i in range(V):
                 if ino[i]==0:
                     qu.append(i)
             #print(qu)
             while(len(qu)!=0):
                 fr=qu[0]
                 qu.pop(0)
                 ans=ans+1
                 for i in adj[fr]:
                     ino[i]=ino[i]-1
                     if ino[i]==0:
                         qu.append(i)
             if ans==V:
                 return False
             else:
                 return True
</code>
