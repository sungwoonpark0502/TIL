# Queue

* FIFO (First In First Out)
* Used in BFS
* LinkedList, ArrayBlockingQueue and PriorityQueue are the most frequently used implementations
* All Queues except the Deques supports insertion and removal at the tail and head of the queue respectively. The Deques support element insertion and removal at both ends. 

Declaring Queue Interface
```java
public interface Queue extends Collection
```

```java
import java.util.Queue
import java.util.LinkedList;

// LinkedList implementation of Queue
Queue<Integer> queue = new LinkedList<>();
Queue<String> queue2 = new LinkedList<>();

// Array implementation of Queue
Queue<String> queue3 = new ArrayDeque<>();

// Priority Queue implementation of Queue
Queue<String> queue4 = new PriorityQueue<>();

// adding items
queue.add(1);
OR
queue.offer(1);

// removing items
queue.remove() // removes the first element
OR
queue.poll(); // removes the first element; if empty, null

// remove everything
queue.clear();

// Head of the Queue
queue.element(); // Retrieves, but does not remove, the head of this queue
OR
queue.peek(); // Retrieves and removes the head of this queue, or returns null if this queue is empty.

// size of Queue
int size = queue.size();

// get specific item
queue.get();

// index of an item
queue.indexOf("somegthing");

// check if empty
queue.isEmpty();

// check to see if Queue contains
queue.contains("item");

// Iterating through Queue
Iterator iterator = queue.iterator();
while(iterator.hasNext()){
    System.out.println(iterator.next() + " ");
}
```

![Queue-Deque-PriorityQueue-In-Java](https://user-images.githubusercontent.com/93812258/184536920-d0f22ced-dfdc-43ce-ada8-6e542735d587.png)
