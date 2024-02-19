<h2>Solve it on <a href="https://www.geeksforgeeks.org/problems/print-adjacency-list-1587115620/1?utm_source=geeksforgeeks&utm_medium=ml_article_practice_tab&utm_campaign=article_practice_tab">GFG</a></h2>
<code>
  from typing import List
</code>
<code>
  


class Solution:
    
    def printGraph(self, V : int, edges : List[List[int]]) -> List[List[int]]:
        ans=[]
        for i in range(V):
            ans.append([])
        for i in edges:
            ans[i[0]].append(i[1])
            ans[i[1]].append(i[0])
        return ans

</code>
