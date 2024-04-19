<h2>Solve it on <a href="https://www.naukri.com/code360/problems/house-robber-ii_839733?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf&leftPanelTabValue=SUBMISSION">Coding Ninjas</a> </h2>
<code>
  def solve(arr):
  
    prev=arr[0]
    prev2=0
    for i in range(1,len(arr)):
           pick=arr[i]+prev2
           npick=prev
           cur=max(pick,npick)
           prev2=prev
           prev=cur
    return prev
  
def houseRobber(valueInHouse):
     if len(valueInHouse)==1:
         return valueInHouse[0]

     return max(solve(valueInHouse[1:]),solve(valueInHouse[:-1]))

</code>
