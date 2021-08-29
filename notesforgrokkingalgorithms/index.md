# NotesForGrokkingAlgorithms


{{< admonition type=note title="Note" open=true >}}
<b>All my notes are going to be on my github account</b>
<a href="https://github.com/RaymondReddigton" target="_blank">My Github Account</a>
{{< /admonition >}}

{{< figure src="/images/GrokkingAlgorithmsNotes-small.jpg" alt="an image contain Grokking Algorithms Book and some code lines on a screen in the background" title="Grokking Algorithms">}}


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

•	D&C works by breaking a problem down into smaller and smaller pieces. If you’re using D&C on a list, the base case is probably an empty array or an array with one element.

•	If you’re implementing quicksort, choose a random element as the pivot. The average runtime of quicksort is O(n log n)!

•	 The constant in Big O notation can matter sometimes. That’s why quicksort is faster than merge sort.

•	The constant almost never matters for simple search versus binary search, because O(log n) is so much faster than O(n) when your list gets big.

## Chapter 05
### Hash Tables
Chapter 05:  Hash Tables 

→ Using hash tables for lookups
Hash tables are great when you want to 

• Create a mapping from one thing to another thing.

• Look something up.

→ Preventing duplicate entries.

{{< figure src="/images/Picture2.png" alt="Preventing duplicate entries" >}}

→ Using hash tables as a cache

you’d just remember and answer. This is how caching works: websites remember the data instead of recalculating it.

{{< figure src="/images/Picture3.png" alt="Using hash tables as a cache" >}}

When you visit a page on Facebook, it first checks whether the page is stored in the hash. 

{{< mermaid >}}graph TD;
    A[request a url from Facebook.] --> C{Is this url in the cache?}
    C --> D[Yes: send the data in the cache.]
    C --> E[No: make the server do some work.]
{{< /mermaid >}}

```Python
    cache = {} 
    def get_page(url): 
        if cache.get(url): 
            return cache[url]    # returned cached data
        else: 
            data = get_data_from_server(url)
            cache[url] = data    # saves this data in your cache first.
        return data
```
Here, you make the server do work only if the URL isn’t in the cache. Before you return the data, though, you save it in the cache. The next time someone requests this URL, you can send the data from the cache
instead of making the server do the work.
### Recap

 To recap, hashes are good for 

• Modeling relationships from one thing to another thing.

• Filtering out duplicates.

• Caching/memorizing data instead of making your server do work.

### Collisions

Def: 
an event of two or more records being assigned the same identifier or location in memory.

Simplest way to deal with collisions is this: if multiple keys map to the same slot, start a linked list at that slot.

{{< figure src="/images/Picture4.png" alt="Linked list picture" >}}

{{< figure src="/images/Picture5.png" alt="slot wasted in a linked list picture." >}}

There is a problem here, The entire hash table is totally empty except for one slot. And that slot has a giant linked list! Every single element in this hash table is in the linked list. That’s as bad as putting everything in a linked list to begin with. It’s going to slow down your hash table.

<!-- styling using shortcode of DoIt theme -->
{{< style "color: yellow" >}}
A good hash function will give you very few collisions.
{{< /style >}}

### Performance
{{< figure src="/images/Picture6.png" alt="the difference among linked list, arrays and hash tabels" >}}
In the average case, hash tables take O(1) for everything. O(1) is called constant time. You haven’t seen constant time before. It doesn’t mean instant. It means the time taken will stay the same, regardless of how big the hash table is.

It’s important that you don’t hit worst-case performance with hash tables. And to do that, you need to avoid collisions. To avoid collisions, you need:

• A low load factor.

• A good hash function.
### Load factor

Load factor measures how many empty slots remain in your hash table

Having a load factor greater than 1 means you have more items than slots in your array.
{{< figure src="/images/Picture7.png" >}}
{{< figure src="/images/Picture8.png" >}}

Once the load factor starts to grow, you need to add more slots to your hash table. This is called resizing.

{{< style "color: yellow" >}}
A good rule of thumb is, resize when your load factor is greater than 0.7.
{{< /style >}}

A good hash function:

•	A good hash function distributes values in the array evenly.

•	A bad hash function groups values together and produces a lot of collisions.

### Recap

You’ll almost never have to implement a hash table yourself. The programming language you use should provide an implementation for you.
 You can use Python’s hash tables and assume that you’ll get the average case performance: constant time.

Hash tables are a powerful data structure because they’re so fast and they let you model data in a different way.
You might soon find that you’re using them all the time:

• You can make a hash table by combining a hash function with an array.

• Collisions are bad. You need a hash function that minimizes collisions.

• Hash tables have really fast search, insert, and delete.

• Hash tables are good for modeling relationships from one item to another item.

• Once your load factor is greater than .07, it’s time to resize your hash table.

• Hash tables are used for caching data (for example, with a web server).

• Hash tables are great for catching duplicates.






