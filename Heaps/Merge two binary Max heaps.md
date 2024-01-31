<h2>Solve on <a href="https://www.geeksforgeeks.org/problems/merge-two-binary-max-heap0144/1">GFG</a></h2>
<h2>Solution:</h2>
<code>
  class Solution():
  
    def heapify(self,a,i):
        l_c=2*i+1
        r_c=2*i+2
        l=i
        if l_c<len(a) and a[l]<a[l_c]:
            l=l_c
            
        if r_c<len(a) and a[l]<a[r_c]:
            l=r_c
        if l!=i:
            a[l],a[i]=a[i],a[l]
            self.heapify(a,l)
            
    def mergeHeaps(self, a, b, n, m):
          for i in range(m):
              a.append(b[i])
          k=(len(a)//2)-1
          while k>=0:
              self.heapify(a,k)
              k=k-1
          return a
</code>
