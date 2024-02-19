<h2>Solve it on <a href="https://www.geeksforgeeks.org/problems/solve-the-sudoku-1587115621/1">GFG</a></h2>
<code>
  class Solution:

    
    def isValid(self,n,row,col,grid):
        for i in range(9):
            if grid[row][i]==n:
                return False
            if grid[i][col]==n:
                return False
            if grid[3*(row//3)+(i//3)][3*(col//3)+(i%3)]==n:
                return False
        return True
    def SolveSudoku(self,grid):
      for i in range(9):
          for j in range(9):
              if grid[i][j]==0:
                  for k in range(9):
                      if self.isValid(k+1,i,j,grid):
                          grid[i][j]=k+1
                          if self.SolveSudoku(grid):
                              return True
                          else:
                               grid[i][j]=0
                  return False
      return True
                          
    
    #Function to print grids of the Sudoku.    
    def printGrid(self,arr):
        
        for i in range(9):
            for j in range(9):
                print(arr[i][j], end=" ")
        return arr
</code>
