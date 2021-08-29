# Problem Solving


<b>Some problems that I solved.</b>

{{< admonition type=note title="Note" open=true >}}
<b>All the problems will be at this </b><a href="https://github.com/RaymondReddigton/Algorithms-and-Data-Structures-training---IEEE-CS-ZSB" target="_blank" >repo</a>.
{{< /admonition >}}


## Day 01
### array left rotation
```Python
'''
        CS21-Science-Day-1      
        name: Mahmoud Abdallah Hassan 
        task: array left rotation
        link: https://www.hackerrank.com/challenges/array-left-rotation/problem
'''

import math
import os
import random
import re
import sys

#
# Complete the 'rotateLeft' function below.
#
# The function is expected to return an INTEGER_ARRAY.
# The function accepts following parameters:
#  1. INTEGER d
#  2. INTEGER_ARRAY arr
#

def rotateLeft(d, arr):
    # Write your code here
    for i in range(d):
        arr.append(arr[i])
    for i in range(d):
        arr.remove(arr[0])    
        
    return arr
if __name__ == '__main__':


    #fptr = open(os.environ['OUTPUT_PATH'], 'w')

    first_multiple_input = input().rstrip().split()

    n = int(first_multiple_input[0])

    d = int(first_multiple_input[1])

    arr = list(map(int, input().rstrip().split()))

    result = rotateLeft(d, arr)
    print(' '.join(map(str, result)))
    input('press enter to exit...')
    # fptr.write(' '.join(map(str, result)))
    # fptr.write('\n')

    # fptr.close()

```
## Day 02
### Find merge point in two list 
```Python
# find merge point in two list 

#!/bin/python3

import math
import os
import random
import re
import sys

class SinglyLinkedListNode:
    def __init__(self, node_data):
        self.data = node_data
        self.next = None

class SinglyLinkedList:
    def __init__(self):
        self.head = None
        self.tail = None

    def insert_node(self, node_data):
        node = SinglyLinkedListNode(node_data)

        if not self.head:
            self.head = node
        else:
            self.tail.next = node


        self.tail = node

def print_singly_linked_list(node, sep, fptr):
    while node:
        fptr.write(str(node.data))

        node = node.next

        if node:
            fptr.write(sep)

def findMergeNode(head1, head2):
    # func to get the count 
    def getcount(head):
        c = 0
        while head.next != None:
            head = head.next
            c+=1
        return c
    
    # func to get the node 
    def getNode(dif, head1, head2):
        # iter. up to dif
        for i in range(dif):
            head1 = head1.next
            
        while head1 and head2:
            if head1 == head2:
                return head1.data
            else:
                head1 = head1.next
                head2 = head2.next
    
    c1 = getcount(head1)
    c2 = getcount(head2)
    
    # check the difference
    if c1 > c2:
        return getNode(c1 - c2, head1, head2)
    else:
        return getNode(c2 - c1, head2, head1)
        
if __name__ == '__main__':
    # fptr = open(os.environ['OUTPUT_PATH'], 'w')

    tests = int(input())

    for tests_itr in range(tests):
        index = int(input())

        llist1_count = int(input())

        llist1 = SinglyLinkedList()

        for _ in range(llist1_count):
            llist1_item = int(input())
            llist1.insert_node(llist1_item)
            
        llist2_count = int(input())

        llist2 = SinglyLinkedList()

        for _ in range(llist2_count):
            llist2_item = int(input())
            llist2.insert_node(llist2_item)
            
        ptr1 = llist1.head;
        ptr2 = llist2.head;

        for i in range(llist1_count):
            if i < index:
                ptr1 = ptr1.next
                
        for i in range(llist2_count):
            if i != llist2_count-1:
                ptr2 = ptr2.next

        ptr2.next = ptr1

        result = findMergeNode(llist1.head, llist2.head)
        print(result)
    #     fptr.write(str(result) + '\n')

    # fptr.close()
```
## Day 03

### Registration System
```Python
# 
# name: Mahmoud Abdallah Hassan
# link: https://codeforces.com/contest/4/problem/C
# 
# time complexity: O(n)

if __name__ == "__main__":
    
    n = int(input())
 
    database = {}
    for i in range(n):
        username = input()
        
        # check if username is in the dictionary
        if username in database:
            # note that the value of non-found username is none, So there will be no value.
            print(username+str(database[username]))
            database[username] += 1
        else:
            print("OK")
            database[username] = 1
```

## Day 04
### cycle Detection
```Python
#
#       CS21-Science-Day-05
#       name: Mahmoud Abdallah 
#       task: cycle detection
#       link: https://www.hackerrank.com/challenges/detect-whether-a-linked-list-contains-a-cycle/problem
#

#!/bin/python3

import math
import os
import random
import re
import sys

class SinglyLinkedListNode:
    def __init__(self, node_data):
        self.data = node_data
        self.next = None

class SinglyLinkedList:
    def __init__(self):
        self.head = None
        self.tail = None

    def insert_node(self, node_data):
        node = SinglyLinkedListNode(node_data)

        if not self.head:
            self.head = node
        else:
            self.tail.next = node


        self.tail = node

def print_singly_linked_list(node, sep, fptr):
    while node:
        fptr.write(str(node.data))

        node = node.next

        if node:
            fptr.write(sep)

# Complete the has_cycle function below.

#
# For your reference:
#
# SinglyLinkedListNode:
#     int data
#     SinglyLinkedListNode next
#
#
def has_cycle(head):
    # idea to create two pointers, make the logic and finially check if the two pointers are the same
    # note that head is a pointer
    pointer2 = pointer1 = head
    
    # make sure that the linkedlist is not empty or having a single node (in that case there will not be a cylce to detect)
    
    while pointer1 != None and pointer1.next != None:
        # set pointers
        pointer1 = pointer1.next.next 
        pointer2 = pointer2.next
        
        # check if the two pointers are same 
        if pointer1 == pointer2:
            return True
    return False
            
            
if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    tests = int(input())

    for tests_itr in range(tests):
        index = int(input())

        llist_count = int(input())

        llist = SinglyLinkedList()

        for _ in range(llist_count):
            llist_item = int(input())
            llist.insert_node(llist_item)

        extra = SinglyLinkedListNode(-1)
        temp = llist.head

        for i in range(llist_count):
            if i == index:
                extra = temp

            if i != llist_count-1:
                temp = temp.next

        temp.next = extra

        result = has_cycle(llist.head)
        
        print(str(int(result)))

        fptr.write(str(int(result)) + '\n')

    fptr.close()
```
## Day 05
### Flipping the matrix
```Python
#
#       CS21-Science-Day-05
#       name: Mahmoud Abdallah 
#       task: Flipping the Matrix
#       link: https://www.hackerrank.com/challenges/flipping-the-matrix/problem?isFullScreen=false
#


#!/bin/python3

import math
import os
import random
import re
import sys

# Complete the flippingMatrix function below.
def flippingMatrix(matrix):
    n = len(matrix[0])
    for i in range(n):
        for j in range(n):
            print(sum([max(matrix[i][j]), matrix[i][2*n - 1 - j], matrix[2*n - 1 - i][j], matrix[2*n -1 -i][2*n -1 -j]]))




if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    q = int(input())

    for q_itr in range(q):
        n = int(input())

        matrix = []

        for _ in range(2*n):
            # row by row; each row is a list
            matrix.append(list(map(int, input().rstrip().split())))

        result = flippingMatrix(matrix)

        print(str(result))

        fptr.write(str(result) + '\n')

    fptr.close()
```

## Day 06
### Tree Huffman Decoding
```Python
import queue as Queue

cntr = 0

class Node:
    def __init__(self, freq, data):
        self.freq = freq
        self.data = data
        self.left = None
        self.right = None
        global cntr
        self._count = cntr
        cntr = cntr + 1
        
    def __lt__(self, other):
        if self.freq != other.freq:
            return self.freq < other.freq
        return self._count < other._count

def huffman_hidden():#builds the tree and returns root
    q = Queue.PriorityQueue()

    
    for key in freq:
        q.put((freq[key], key, Node(freq[key], key) ))
    
    while q.qsize() != 1:
        a = q.get()
        b = q.get()
        obj = Node(a[0] + b[0], '\0' )
        obj.left = a[2]
        obj.right = b[2]
        q.put((obj.freq, obj.data, obj ))
        
    root = q.get()
    root = root[2]#contains root object
    return root

def dfs_hidden(obj, already):
    if(obj == None):
        return
    elif(obj.data != '\0'):
        code_hidden[obj.data] = already
        
    dfs_hidden(obj.right, already + "1")
    dfs_hidden(obj.left, already + "0")

"""class Node:
    def __init__(self, freq,data):
        self.freq= freq
        self.data=data
        self.left = None
        self.right = None
"""        

# Enter your code here. Read input from STDIN. Print output to STDOUT
def decodeHuff(root, s):
    #Enter Your Code Here
    temp = root
    
    result = []

    # traverse on string
    for char in s:
        if char == "1":
            temp = temp.right
        else:
            temp = temp.left
    # check if there is a leaf node
        if temp.left is None and temp.right is None:
            result.append(temp.data)
            temp = root 
        
    print(''.join(result))


ip = input()
freq = {}#maps each character to its frequency

cntr = 0

for ch in ip:
    if(freq.get(ch) == None):
        freq[ch] = 1
    else:
        freq[ch]+=1

root = huffman_hidden()#contains root of huffman tree

code_hidden = {}#contains code for each object

dfs_hidden(root, "")

if len(code_hidden) == 1:#if there is only one character in the i/p
    for key in code_hidden:
        code_hidden[key] = "0"

toBeDecoded = ""

for ch in ip:
   toBeDecoded += code_hidden[ch]

decodeHuff(root, toBeDecoded)
```


