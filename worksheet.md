# 02/12 Worksheet: Stacks & Queues and Binary Search
## Due date: *02/19 @11:59 PM*
Collaborators:

Answer the below questions, and make sure that you commit to your own branch.
When done, make a pull request on github. Don't forget to tag @Anh-Thuong-Vo.
Respond to my comments by making new commits to the same branch.

## Review
1. In your own words, what is a stack? Make sure to also define the term LIFO.
2. In your own words, what is a queue? Make sure to also define the term FIFO.
3. In your own words, explain how binary search on an array works.
4. In your own words, explain the worst-case time complexity of binary search on an array. Be sure to also explain why getting an element from an array has O(1) time.

## Exploration
1. In this question, we are going to implement the `push()`, `pop()`, and `peek()` methods for LinkedList based Stacks. Try to do this without referencing the video.
Starter code can be found in MyStack.java. You'll notice that MyStack extends IntLinkedList, which is provided to you as an abstract class in IntLinkedList.java. One of the benefits of using an abstract class is that we can use its implemented methods. Here, you may want to make use of methods like `add()`, `get()`, and `remove()`. You may refer to the LinkedList using the `this` keyword (e.g., `this.get(5)` or `this.head`).    

   a. At the first FIXME in MyStack.java, implement the `push()` method. Think about where the new element will need to be, in terms of the LinkedList and how the LinkedList will need to be adjusted (if at all).  
   
    b. At the second FIXME in MyStack.java, implement the `pop()` method. Think about where the element will be removed from, and how the LinkedList will need to be adjusted (if at all).  

    c. At the third FIXME in MyStack.java, implement the `peek()` method. Think about how this method differs from `pop()`.

2. In this question, we are going to implement the `push()`, `pop()`, and `peek()` methods for LinkedList based Queues. Try to do this without referencing the video. 

    Starter code can be found in MyQueue.java. You'll notice that it, too, extends IntLinkedList. As above, consider making use of its implemented methods.    
    
    a. At the first FIXME in MyStack.java, implement the `push()` method. Think about where the new element will need to be, in terms of the LinkedList and how the LinkedList will need to be adjusted (if at all).  
  
    b. At the second FIXME in MyStack.java, implement the `pop()` method. Think about where the element will be removed from, and how the LinkedList will need to be adjusted (if at all).  
  
    c. At the third FIXME in MyStack.java, implement the `peek()` method. Think about how this method differs from `pop()`.
   
The next few questions ask you to write two different versions of binary search, both based on the following (adapted) code from the textbook. A copy of this function is in `BinarySearch.java` as `origBinarySearch()`.

```java
int binarySearch(int[] array, int target) {
    int mid = 0;
    int low = 0;
    int high = array.length - 1;
    while (high >= low) {
        mid = (high + low) / 2;
        if (array[mid] < target) {
            low = mid + 1;
        } else if (array[mid] > target) {
            high = mid - 1;
        } else {
            return mid;
        }
    }
    return -1; // not found
}
```
3.     
    a. Modify the code above so that it returns the *first* instance (lowest index) of the `target`. Put your code in `firstBinarySearch` in `BinarySearch.java`. Submit your code to the autograder and *also* include your code in the pull request.  
    
    b. What is the worst-case time complexity of the function you just wrote? Justify your answer.  

    c. What is the worst-case memory complexity of the function you just wrote? Justify your answer.

4.      
    a. Using the process outlined in the 09/13 worksheet on recursion, convert `origBinarySearch()` into a tail-recursive function. Put your code in `recurBinarySearch` in `BinarySearch.java`. Submit your code to the autograder and *also* include your code in the pull request.  
    
    b. What is the worst-case time complexity of the tail-recursive function you just wrote? Justify your answer. 

    c. What is the worst-case memory complexity of the tail-recursive function you just wrote, assuming tail-recursion optimization on the stack? Justify your answer.

## Challenge
1. What is the runtime complexity (big-O) of `push()` and `pop()` for our implementation of MyStack?
2. What is the runtime complexity (big-O) of `push()` and `pop()` for our implementation of MyQueue?
3. We implemented MyStack and MyQueue via LinkedLists, but we could have just as easily used an ArrayList. Use what you have learned about the differences between ArrayLists and LinkedLists to answer the questions below. You should not implement any new code.    

    a. Without writing any code, explain how your implementation of `push()` be different for an MyStack if we used an ArrayList instead of a LinkedList. What would the complexity (big-O) be of the new implementation?
    
   b. Without writing any code, explain how your implementation of `pop()` be different for an MyStack if we used an ArrayList instead of a LinkedList. What would the complexity (big-O) be of the new implementation?  
   
   c. Without writing any code, explain how your implementation of `push()` be different for an MyQueue if we used an ArrayList instead of a LinkedList. What would the complexity (big-O) be of the new implementation?  
   
   d. Without writing any code, explain how your implementation of `pop()` be different for an MyQueue if we used an ArrayList instead of a LinkedList. What would the complexity (big-O) be of the new implementation?
   
4. Why did we implement MyStack and MyQueue via LinkedList, rather than ArrayList?
5. Consider the following version of binary search that works on an ArrayList:

    ```java
    Integer binarySearch(ArrayList<Integer> list, Integer target) {
        int mid = 0;
        int low = 0;
        int high = list.size() - 1;
        while (high >= low) {
            mid = (high + low) / 2;
            if (list.get(mid) < target) {
                low = mid + 1;
            } else if (list.get(mid) > target) {
                high = mid - 1;
            } else {
                return mid;
            }
        }
        return -1; // not found
    }
    ```

    What is the worst-case time complexity of this function? Justify your answer.
6. Consider the following version of binary search that works on a LinkedList:

    ```java
    Integer binarySearch(LinkedList<Integer> list, Integer target) {
        int mid = 0;
        int low = 0;
        int high = list.size() - 1;
        while (high >= low) {
            mid = (high + low) / 2;
            if (list.get(mid) < target) {
                low = mid + 1;
            } else if (list.get(mid) > target) {
                high = mid - 1;
            } else {
                return mid;
            }
        }
        return -1; // not found
    }
    ```

    What is the worst-case time complexity of this function? Justify your answer.
