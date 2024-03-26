<h2>Solve it on <a href="https://www.geeksforgeeks.org/problems/minimum-spanning-tree/1?utm_source=youtube&utm_medium=collab_striver_ytdescription&utm_campaign=minimum-spanning-tree">GFG</a></h2>
<h3>Solution:</h3>
<code>
import heapq
class Solution:
    
    #Function to find sum of weights of edges of the Minimum Spanning Tree.
    def spanningTree(self, V, adj):
        vi=[0]*V
        #print(adj)
        p=[]
        heapq.heappush(p, [0,0])

        ans=0
        while len(p)!=0:
            
            [l,n]=heapq.heappop(p)

            if vi[n]==1:
                continue
            else:
                vi[n]=1
                ans=ans+l
                for i in adj[n]:
                    if vi[i[0]]==0:
                        heapq.heappush(p,[i[1],i[0]])
                      
        return ans
</code>
