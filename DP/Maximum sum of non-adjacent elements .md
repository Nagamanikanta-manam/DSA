<h3>Solve it on <a href="https://www.naukri.com/code360/problems/maximum-sum-of-non-adjacent-elements_843261?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf"> Coding Ninjas </a></h3>
<h4 >Memorization Approach</h4>
<code>
  def solve(nums,ind,dp):
  
    if ind==0:
        return nums[ind]
    if ind<0:
        return 0
    if dp[ind]==-1:
     pick=nums[ind]+solve(nums,ind-2,dp)
     npick=0+solve(nums,ind-1,dp)
     dp[ind]=max(pick,npick)
     return dp[ind]
    else:
        return dp[ind]

def maximumNonAdjacentSum(nums):

     dp=[-1]*len(nums)  
     return solve(nums,len(nums)-1,dp)
</code>
<h4>Tabulation</h4>
<code>
  def solve(nums,ind,dp):
    
    prev=nums[0]
    prev2=0
    cur=0
    for i in range(1,len(nums)):

        pick=nums[i]
        if i>1:
            pick=pick+prev2
        npick=prev+0
        
            
        cur=max(pick,npick)
        prev2=prev
        prev=cur
    return prev



def maximumNonAdjacentSum(nums):  

     dp=[-1]*len(nums)  
     return solve(nums,len(nums)-1,dp)
</code>
