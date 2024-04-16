<h3>Solve it on <a href="https://www.naukri.com/code360/problems/minimal-cost_8180930?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf&leftPanelTabValue=SUBMISSION">Coding Ninjas</a></h3>
<code>
  
from typing import *

def solveUnit(dp,heights,k,n):

    dp[0]=0
    for i in range(1,n):
      minsteps=float('inf')
      for j in range(1,k+1):
        
        if i-j>=0:
            s=dp[i-j]+abs(heights[i]-heights[i-j])
            minsteps=min(s,minsteps)
      dp[i]=minsteps
    return dp[-1]
    
def solve(heights,k,n):

    dp=[-1]*n
    return solveUnit(dp,heights,k,n)
    
def minimizeCost(n : int, k : int, heights : List[int]) -> int:

    return solve(heights,k,n)
</code>
