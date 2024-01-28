<h1>Binary Heap Operations</h1>

Solve it on <a href="https://www.geeksforgeeks.org/problems/operations-on-binary-min-heap/1?utm_source=geeksforgeeks&utm_medium=ml_article_practice_tab&utm_campaign=article_practice_tab">gfg</a>
<h2>Solution</h2>
<code>
  #User function Template for python3

'''
heap = [0 for i in range(101)]  # our heap to be used
'''
#Function to insert a value in Heap.

def insertKey (x):

    global curr_size
    curr_size=curr_size+1
    heap[curr_size-1]=x
    k=curr_size-1
    while k>=1:
        if heap[(k-1)//2]>heap[k]:
            heap[k],heap[(k-1)//2]=heap[(k-1)//2],heap[k]
            k=(k-1)//2
        else:
           break
    

def heapify(i):
    
    global curr_size
    r_c=2*i+1
    l_c=2*i+2
    s=i
    if r_c<curr_size and heap[s]>heap[r_c]:
        s=r_c
    if l_c<curr_size and heap[s]>heap[l_c]:
        s=l_c
    if s!=i:
        heap[s],heap[i]=heap[i],heap[s]
        heapify(s)
    #print(heap)
def deleteKey (i):
    
    if i >= curr_size:
        return
    heap[i] = float('-inf')
    k=i
    while k>=1:
        if heap[(k-1)//2]>heap[k]:
            
            heap[k],heap[(k-1)//2]=heap[(k-1)//2],heap[k]
            k=(k-1)//2
            
        else:
            
            break
    
    
    extractMin()


def extractMin ():
    
    
    global curr_size
    if curr_size==0:
        return -1
    if curr_size==1:
          k=heap[0]
          heap.pop()
          curr_size=curr_size-1
          return k

          
    k=heap[0]
    
    last=heap[curr_size-1]
    heap[curr_size-1]=0
    heap.pop(0)

    
    
    curr_size=curr_size-1
    heap.insert(0,last)
    
    
    heapify(0)
    return k
</code>
