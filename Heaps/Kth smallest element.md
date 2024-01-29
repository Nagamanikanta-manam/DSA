<h2 >Solve it on <a href="https://www.geeksforgeeks.org/problems/kth-smallest-element5635/1">GFG</a></h2>

<h2>For Solution by Love babbar <a href="https://www.geeksforgeeks.org/problems/kth-smallest-element5635/1">Click Here</a> </h2>
<h2>Solution:</h2>
<code>
  import heapq
class Solution:
    def kthSmallest(self,arr, l, r, k):
        '''
        arr : given array
        l : starting index of the array i.e 0
        r : ending index of the array i.e size-1
        k : find kth smallest element and return using this function
        '''
        s=[]
        for i in range(k):
            s.append(-1*arr[i])
        
        heapq.heapify(s)
        
        j=k
        while j<=r:
            if s[0]<-1*arr[j]:
                heapq.heappop(s)
                heapq.heappush(s, -1*arr[j])
            j=j+1
        
        return -1*s[0]
</code>
