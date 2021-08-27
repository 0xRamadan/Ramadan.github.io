# NotesForGrokkingAlgorithms

{{< figure src="/images/GrokkingAlgorithmsNotes-small.jpg" alt="an image contain Grokking Algorithms Book and some code lines on a screen in the background" title="Grokking Algorithms">}}
<b>All my notes are going to be on my github account</b>
<a href="https://github.com/RaymondReddigton" target="_blank">My Github Account</a>
<div>

## Chapter 01
### Introduction to algorithms
Chapter 01: Introduction to algorithms

Some common Big O run times sorted from fastest to slowest:

• O(log n), also known as log time. Example: Binary search. 

• O(n), also known as linear time. Example: Simple search.

• O(n * log n). Example: A fast sorting algorithm, like quicksort.

• O(n2). Example: A slow sorting algorithm, like selection sort.

• O(n!). Example: A really slow algorithm, like the traveling Salesperson.

### Recap
Recap 

• Binary search is a lot faster than simple search. 

• O(log n) is faster than O(n), but it gets a lot faster once the list of items you’re searching through grows.

• Algorithm speed isn’t measured in seconds.

• Algorithm times are measured in terms of growth of an algorithm.

• Algorithm times are written in Big O notation.

## Chapter 02
### Selection Sort
Chapter 02: Selection Sort

•	Linked lists are great if you’re going to read all the items one at a time.

•	Arrays are great if you want to read random elements.

•	Lists are better if you want to insert elements into the middle.

•	A lot of use cases require random access, so arrays are used a lot. Arrays and lists are used to implement other data structures.

•	Selection sort is a neat algorithm, but it’s not very fast. Quicksort is a faster sorting algorithm that only takes O(n log n) time.

### Recap
Recap:

• When you want to store multiple elements, use an array or a list. 

• With an array, all your elements are stored right next to each other.

• With a list, elements are strewn all over, and one element stores the address of the next one.

• Arrays allow fast reads. 

• Linked lists allow fast inserts and deletes.

• All elements in the array should be the same type (all ints, all doubles, and so on).

```Python
    # A simple Selection sort Algorithm 
def findSmallest(arr):
    smallest = arr[0]
    smallest_index = 0
    for i in range(1, len(arr)):
        if arr[i] < smallest:
            smallest =arr[i]
            smallest_index = i
    return smallest_index

def selectionSort(arr):
    new_arr = []
    for i in range(len(arr)):
        smallest = findSmallest(arr)
        new_arr.append(arr.pop(smallest))
    return new_arr

if __name__ == '__main__':
    arr = list(map(int, input().split()))
    print(selectionSort(arr))

```
## Chapter 03
### Recursion
Chapter 03:  Recursion

-	Pseudocode is a high-level description of the problem you’re trying to solve, in code. It’s written like code, but it’s meant to be closer to human speech.

-	Recursion is where a function calls itself.

-	Quote by Leigh Caldwell on Stack Overflow:  “Loops may achieve a performance gain for your program. Recursion may achieve a performance gain for your programmer. Choose which is more important in your situation!”

-	every recursive function has two parts: the base case, and the recursive case.

{{< figure src="/images/Picture1.png" alt="a function in python handling base case and the recursive case" >}}

-	Using the stack is convenient because you don’t have to keep track of a pile of boxes yourself—the stack does it for you. but there’s a cost: saving all that info can take up a lot of memory.
### Recap
Recap 

• Recursion is when a function calls itself.

• Every recursive function has two cases: the base case and the recursive case.

• A stack has two operations: push and pop. 

• All function calls go onto the call stack.

• The call stack can get very large, which takes up a lot of memory.

## Chapter 04
### Quicksort
Chapter 04:  Quicksort

•	Quicksort is a sorting algorithm, and a much faster one than selection sort.

•	To solve a problem using D&C, there are two steps: 

    1. Figure out the base case. This should be the simplest possible case.

    2. Divide or decrease your problem until it becomes the base case.

•	Remember, recursion keeps track of the state.

•	When you’re writing a recursive function involving an array, the base case is often an empty array or an array with one element. If you’re stuck, try that first.

### Recap
Recap: 

•	D&C works by breaking a problem down into smaller and smaller pieces. If you’re using D&C on a list, the base case is probably an empty array or an array with one element.

•	If you’re implementing quicksort, choose a random element as the pivot. The average runtime of quicksort is O(n log n)!

•	 The constant in Big O notation can matter sometimes. That’s why quicksort is faster than merge sort.

•	The constant almost never matters for simple search versus binary search, because O(log n) is so much faster than O(n) when your list gets big.

</div>





