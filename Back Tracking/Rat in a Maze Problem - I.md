<h2>Solve it on <a href="https://www.geeksforgeeks.org/problems/rat-in-a-maze-problem/1">Hacker Rank</a></h2>
<code>
class Solution:

    def __init__(self):
        self.ans=[]
        self.v=[]
        
        
                
                
        
        
    def path(self, m, n, i, j,ans):
        
        if i == n-1 and j == n-1:
            self.ans.append(ans)
            
            return
        
        if i+1 < n and m[i+1][j] == 1 and self.v[i+1][j] == 0:
            
            
            self.v[i][j]=1
            self.path(m, n, i+1, j,ans+'D')
            
            self.v[i][j]=0
            
        
        if j-1 >= 0 and m[i][j-1] == 1 and self.v[i][j-1] == 0:
            
            self.v[i][j]=1
            self.path(m, n, i, j-1,ans+'L')
            
            self.v[i][j]=0
            
            
        if j+1 < n and m[i][j+1] == 1 and self.v[i][j+1] == 0:
            
            self.v[i][j]=1
            self.path(m, n, i, j+1,ans+'R')
            
            self.v[i][j]=0
            
        if i-1 >= 0 and m[i-1][j] == 1 and self.v[i-1][j] == 0:
            
            self.v[i][j]=1
            self.path(m, n, i-1, j,ans+'U')
            
            self.v[i][j]=0
           
            
    def findPath(self, m, n):
        visited=[]
        for i in range(n):
            k=[]
            for j in range(n):
                k.append(0)
            self.v.append(k)
        if m[0][0]==0:
            return [-1]
            
        self.path(m, n, 0, 0,'')
        
        return self.ans

</code>
