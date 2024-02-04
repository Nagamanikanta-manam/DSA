<h2>Solve it on <a href="https://www.geeksforgeeks.org/problems/trie-insert-and-search0651/1"> GFG</a></h2>
<h3>Solution:</h3>
<code>
  class Solution:
  
    #Function to insert string into TRIE.
    def insert(self, root, key):
        if len(key)==0:
            root.isEndOfWord=True
            return
        index=ord(key[0])-ord('a')
        if root.children[index]!=None:
            self.insert(root.children[index],key[1:])
        else:
            t=TrieNode()
            root.children[index]=t
            self.insert(root.children[index],key[1:])
            
            
    
    #Function to use TRIE data structure and search the given string.
    def search(self, root, key):
        
        if len(key)==0:
            return root.isEndOfWord
        index=ord(key[0])-ord('a')
        if root.children[index]!=None:
            child=root.children[index]
        else:
            return False
        return self.search(child,key[1:])
</code>
