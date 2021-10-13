# How to Solve - Dynamic Queues

Queue with Simply Sentinel-Linked List

**Description:** Make a program in C or C++ language that use the structures and functions of dynamic queues ADT to manage a set of points in the bidimensional plane.

The **Point Entity** must have the following structure:

```json
{ 
    "ID": "P01",
    "x": 1.300, // 3 floating points.
    "y": 1.250
}
```

The code must have the following functions:

1. Add a Point
2. Remove a Point
3. Print the Point
4. Clean the Queue

The program must have the following options:

1. Insert a point in the Queue
2. Dispatch a Point of the Queue (and Display It)
3. Clean the Queue
4. Exit

## The Point Structure, Again...

As you previously coded you have the code to instatiate an structure.

```c++
// Declare the Node
struct node {
    int x;

    // We need to simply link each node
    struct node *next;
};

// Secondly we declare another structure as a Queue
typedef struct node *Queue;

int main () {
    Queue myQueue = NULL;

    return 0;
}
```

Ok, now we are set and ready to start the challenge.

## Houston, something is behind me

Queues, are another data structure, they are an ordered collection of elements in which we can delete elements at the start, or we can add elements to the end.

Nowadays this data structure is something that everyone is accostumed, i.e. when you buy in any Super Market you do a queue to pay, the first in the queue is the first to be dispatched, and when someone needs to pay he stars at the end of the Queue.

Queues are a data structure FIFO (First In First Out).

For this moment the first thing that we need to do is to add an element to the end of the Queue. For that you must complete the following function:

```c++
void push(Queue &myQueue, int n) {
    // Create a new node and add it to myQueue
}
```

In the function above there is two ways, you can use *next* to determine who is behind or you can use *next* to determine who is in front. As you can see the Queues are FIFO (First In First Out), so we can use the first element as the Head and the last element as the Tail, but can be reversed, the only difference is that *push* or *pop* one of them must iterate all elements.

For this example we will use the first element as the Head, and the last element as the tail.

First what we need is a function that determines if the Queue is empty:

```c++
bool isTail(Queue &myQueue)
{
    // check if myQueue->next is the same as myQueue
}
```

Next, is a coding tip. One expression can substitute an if structure. Keep that in mind so you can write less code ;)

```c++
bool isTrue(int n) {
    if (n > 1) {
        return true;
    }

    return false;
}

bool isTrue2(int n) {
    return n > 1; // Return true if n > 1, otherwise return false.
}
```

Now you have a function that checks if in the Queue is the last element. Now we must work on how to add one element to the Queue.

```c++
void push(Queue &myQueue, int n) {
    // We need an iterator and a item to store the N value
    Queue iterator = myQueue, item = new (struct node);

    // NOTE: As you remember, previously we initialize myQueue as NULL,
    // We are using NULL ONLY to determine that the Queue is empty

    // If myQueue is Empty
    // --> myQueue will be the item
    // If the Queue is not Empty
    // --> Iterate until you reach the tail of the queue
    // --> iterator->next will be the item
}
```

You have some pseudocode so you can fullfill this task, remember, you have a isTail function use it wisely.

## Popcorns DO POP!

Now we have how to add an item to the Queue, but we need to dispatch the first element of the queue.

Your first task is to print the first element, so complete the function below, there will not be any extra comments for this function, why? it's an easy task you only need to print.

```c++
void printPoint(Queue &myQueue) {

}
```

Now that you have how to print the element, we need to dispatch the element with the following function:

```c++
void pop(Queue &myQueue) {
    // We need a temporal variable for the queue
    Queue temp = myQueue;

    // NOTE: It is set as the first element, because this will be the element to dispatch.

    // If temp is Empty
    // --> print "Queue is empty\n" and finish this function.

    // If temp is not Empty
    // --> If temp is the tail
    // ---->  myQueue will be set as Empty
    // --> If temp is not the tail
    // ----> myQueue will be temp->next;
    // --> print the temp
    // --> delete temp
}
```

Once you can do push, push, pop, pop, pop, you are a few steps nearby the end. The next you need to do is to clear all the queue without printing the values.

## All Clear, Sir!

For cleaning the Queue you need to complete the following function:
```c++
void cleanQueue(Queue &myQueue) {
    Queue iterator = myQueue; // We need an iterator to dispatch all the items.

    // if the iterator is Empty, we dont need to dispatch.

    // If the iterator is not Empty
    // --> Delete each element from start to tail

    // Once you have deleted all the elements remember to set myQueue to empty.
}
```

## Don't lose control

Following code is a copy-paste, for you not to write (again).

```c++
int main() {
    int order;

    do {
        // Get Order from the user
        scanf("%d", &order);

        switch (order) {
            case 1: // Use Push()
                break;
            case 2: // Use Pop()
                break;
            case 3: // Use CleanQueue()
                break;
            default: // print "Unknown Order"
                break;
        }
    } while (order != 4);

    return 0;
}
```

As you can see Queues, are simpler than Stacks, they don't need to be iterated twice.

With all this, I only hope Good Luck For You!