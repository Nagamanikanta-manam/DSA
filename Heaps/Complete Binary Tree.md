<h2>Solve it on <a href="https://www.geeksforgeeks.org/problems/complete-binary-tree/1?utm_source=geeksforgeeks&utm_medium=ml_article_practice_tab&utm_campaign=article_practice_tab">GFG</a></h2>
<h2>Solution:</h2>
<code>
  
  class Solution():
  
    def count(self,root):
        if root==None:
            return 0
        l=self.count(root.left)
        r=self.count(root.right)
        return 1+l+r
    def isC(self,root,index,c):
        if root==None:
            return True
        if index>=c:
            return False
        r=self.isC(root.left,2*index+1,c)
        l=self.isC(root.right,2*index+2,c)
        return r and l
    
    def isCompleteBT(self, root):
    
        c=self.count(root)
        #print(c)
        j=self.isC(root,0,c)
        #print(j)
        if j:
            return True
        else:
            return False
              
</code>
</code>
