<h2>Solve it on <a href="https://www.geeksforgeeks.org/problems/trie-delete/1">GFG</a></h2>
<h3>Solution:</h3>
<code>
  class Solution():
  
    def deleteKey(self, root, key):
          
          if len(key)==0:
              root.isEndOfWord=False
              return
          else:
           ind=ord(key[0])-ord('a')
           self.deleteKey(root.children[ind],key[1:])
</code>
