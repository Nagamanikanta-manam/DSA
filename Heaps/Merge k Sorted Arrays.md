<h2>Solve it on <a href="https://www.geeksforgeeks.org/problems/merge-k-sorted-arrays/1">GFG</a></h2>

<code>
import heapq
class Node:

    def __init__(self,data,i,j):
        self.data=data
        self.i=i
        self.j=j
    def __lt__(self,other):
        return self.data<other.data
</code>
<code>

class Solution:

    #Function to merge k sorted arrays.
    def mergeKArrays(self, arr, K):
        heap=[]
        ans=[]
        for i in range(K):
            k=Node(arr[i][0],i,0)
            heapq.heappush(heap,k)
        
        while len(heap)>0:
            k=heapq.heappop(heap)
            #print("k-data")
            #print(k.data,k.i,k.j)
            #print("ans")
            
            ans.append(k.data)
            #print(ans)
            
            if k.j+1 <len(arr[k.i]):
                #print("***")
                n=Node(arr[k.i][k.j+1],k.i,k.j+1)
                heapq.heappush(heap,n)
        return ans
</code>
