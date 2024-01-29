<h2>Solve it on <a href="https://www.geeksforgeeks.org/problems/is-binary-tree-heap/1">GFG</a></h2>
<h3>For video solution by love babbar <a href="https://youtu.be/_9F2VgZcvdw?list=PLDzeHZWIZsTryvtXdMr6rPh4IDexB5NIA&t=1130">click here</a></h3>
<h2>Solution: </h2>
<code>
  class Solution:
  
    def count(self,root):
        if root==None:
            return 0
        l=self.count(root.left)
        r=self.count(root.right)
        return 1+l+r
    def iCbt(self,root,index,count):
        if root==None:
            return True
        if index>=count:
            return False
        l=self.iCbt(root.left,2*index+1,count)
        r=self.iCbt(root.right,2*index+2,count)
        return l and r
    def iMax(self,root):
        if root==None:
            return True
        if root.left==None and root.right==None:
            return True
        if root.right==None:
            
            return self.iMax(root.left) and root.data>root.left.data
        l=self.iMax(root.left)
        r=self.iMax(root.right)
        return l and r and root.data>root.left.data and root.data>root.right.data
    def isHeap(self, root):
        c=self.count(root)
        #print(c)
        d=self.iCbt(root,0,c)
        return d and self.iMax(root)
</code>
