<h1>Solve it on <a href="https://www.naukri.com/code360/problems/frog-jump_3621012?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf&leftPanelTabValue=SUBMISSION">Coding Ninjas</a></h1>
<code>
def frogJump(n: int, heights: List[int]) -> int:

    prev2=0
    prev1=0
    cur=0
    for i in range(1,n):
        fs=prev1+abs(heights[i-1]-heights[i])
        ss=float("inf")
        if i>1:
           ss=prev2+abs(heights[i-2]-heights[i])
        cur=min(fs,ss)
        prev2=prev1
        prev1=cur
    return prev1
</code>
