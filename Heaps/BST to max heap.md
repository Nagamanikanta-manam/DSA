<h2>Solve it on <a href="https://www.geeksforgeeks.org/problems/bst-to-max-heap/1?utm_source=geeksforgeeks&utm_medium=ml_article_practice_tab&utm_campaign=article_practice_tab">GFG</a></h2>
<h2>Solution:</h2>
<code>

  class Solution:
  
    def __init__(self):
        self.d=[]
        self.index=0
    def des(self,root):
        if root==None:
            return
        self.des(root.right)
        self.d.append(root.data)
        self.des(root.left)
    def pre(self,root):
         if root==None:
             return
         #print(root.right.data)
         root.data=self.d[self.index]
         self.index=self.index+1
         self.pre(root.right)
         self.pre(root.left)
    def convertToMaxHeapUtil(self, root):
        self.des(root)
        
        self.pre(root)
        #print(self.index)
</code>
