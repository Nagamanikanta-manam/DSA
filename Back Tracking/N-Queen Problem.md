<h2>Solve it on <a="https://www.geeksforgeeks.org/problems/n-queen-problem0315/1">GFG</a></h2>
<code>
  class Solution:
  
    def __init__(self):
        self.board=[]
        self.ans=[]
    def isSafe(self,c,r,n):
        
        col=c
        row=r
        while(col>=0):
            if self.board[row][col]==1:
               return False
            else:
                col=col-1
        col=c
        row=r
        while(col>=0 and row>=0):
            if self.board[row][col]==1:
                return False
            else:
                row=row-1
                col=col-1
        row=r
        col=c
        while(row<n and col>=0):
            if self.board[row][col]==1:
              return False
            else:
                row=row+1
                col=col-1
        return True
               
    def solve(self,c,ans):
        #print("col",c)
        if c==n:
            self.ans.append(ans[:])
            return
        for i in range(n):
            #print("row",i)
            if self.isSafe(c,i,n):
                self.board[i][c]=1
                ans.append(i+1)
                self.solve(c+1,ans)
                ans.pop()
                self.board[i][c]=0
        
    def nQueen(self, n):
        for i in range(n):
            k=[]
            for j in range(n):
                k.append(0)
            self.board.append(k[:])
        #print(self.board)
        self.solve(0,[])
        return self.ans
</code>
