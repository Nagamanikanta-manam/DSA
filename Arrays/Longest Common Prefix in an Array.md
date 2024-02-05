<h2>Solve it on <a href="https://www.geeksforgeeks.org/problems/longest-common-prefix-in-an-array5129/1">GFG</a></h2>
<h3>Solution:</h3>
<code>
class Solution:

    def longestCommonPrefix(self, arr, n):
        i=True
        k=0
        ans=''
        while i:
            if k>=len(arr[0]):
                break
            c=arr[0][k]
            for j in arr:
                #print(j)
                if  k>=len(j) or j[k]!=c  :
                    i=False
                    break
            if i==True:
                    ans=ans+c
                    k=k+1
            else:
                break
        if ans=='':
            return -1
        return ans            


</code>
