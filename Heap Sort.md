<h1>Heap Sort</h1>

Solve it on <a href="https://www.geeksforgeeks.org/problems/heap-sort/1">GFG</a>

<h2>Solution</h2>
<code>
class Solution:
    #Heapify function to maintain heap property.
    def heapify(self,arr, n, i):
        l_c=2*i+1
        r_c=2*i+2
        s=i
        if l_c<n and arr[s]<arr[l_c]:
                s=l_c
        if r_c<n and arr[s]<arr[r_c]:
            s=r_c
        if s!=i:
           arr[s],arr[i]=arr[i],arr[s]
           self.heapify(arr,n,s)
    
    #Function to build a Heap from array.
    def buildHeap(self,arr,n):
        #print("//")
        k=(n//2)-1
        while k>=0:
            self.heapify(arr,n,k)
            k=k-1
        #print("***")
        #print(arr)      
    
    #Function to sort an array using Heap Sort.    
    def HeapSort(self, arr, n):
      self.buildHeap(arr,n)
      while n>0:
        arr[0],arr[n-1]=arr[n-1],arr[0]
        n=n-1
        self.heapify(arr,n,0)
  
</code>
