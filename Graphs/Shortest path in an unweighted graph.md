<h2>Solve it on <a href="https://www.codingninjas.com/studio/problems/shortest-path-in-an-unweighted-graph_981297?leftPanelTab=0&utm_source=youtube&utm_medium=affiliate&utm_campaign=Lovebabbar&leftPanelTabValue=PROBLEM">codingninjas</a></h2>
<h3>Solution:</h3>
<code>
  def shortestPath(edges, n, m, s, t):
  
        s=s-1
        adj=[]
        for i in range(n):
            adj.append([])
        #print("***")
        #print(edges)
        
        
        for i in edges:
            adj[i[0]-1].append(i[1]-1)
            adj[i[1]-1].append(i[0]-1)
        
        vi=[False]*n
        parent=[None]*n
        qu=[]
        qu.append(s)
        vi[s]=True
        #print("**")
        while len(qu)!=0:
            fro=qu[0]
            qu.pop(0)
            #print(fro)
            for i in adj[fro]:
                if vi[i]==False:
                    qu.append(i)
                    parent[i]=fro
                    vi[i]=True
        #print("**")
        #print(parent)
        ans=[]
        c=t-1
        
        #print("*")
        ans.append(c+1)
        while c!=s:
           #print("*")
           c=parent[c]
           ans.append(c+1)
        #print(ans[::-1])
        return ans[::-1]
</code>
