# Instructions

## Mission

Make a program that use the structures and functions of Stacks ADT to manage a set of point in the bidimensional plane.

The points entity must have the following structure:

```json
// TPoint
{
    "ID": "P01",
    "x": 1.3,
    "y": 2.0
}
```

While the stack entity must have the following structure:

```json
// Stack
{
    "points": [/* TPoint, TPoint, ..., TPoint */]
}
```

If the Stack is full or empty, it must print the following messages:

* Stack is full
* Stack is empty

## Objectives

### Objective 1. Make a Structure

First of all you need to make an structure, as intended we know that the **Stack Structure depends on the TPoint Structure**, so we can't make a Stack Structure without the TPoint Structure.

Remember, a structure can be defined as follows:

```c++
#include <stdio.h>

typedef struct {
    char title[50];
    char author[50];
    char subject[50];
} Book;

using namespace std;

int main() {
    // Using them as a type of variable.
    Book hp;

    scanf("%s", hp.title);
    scanf("%s", hp.author);
    scanf("%s", hp.subject);

    return 0;
}
```

#### Tasks to fulfill the Objective

1. Create a TPoint Structure
2. Using TPoint Structure create a Stack Structure
    1. **Note**: Create many TPoint Structure variables to test that you stack is storing TPoint's correctly.
    2. **Recommendation**: It is a good idea to keep in mind how it works a Stack. It has a maximum size, but it can have less items, so it's a good idea to keep a track of the maximum and how many items are in the list (max_size and count), so further functions can use full advantage of this.

Once you have TPoint and Stack Structure, you are ready to start with the following step.

### Objective 2. Initialize your stack

Remember, you need that you stack stores many TPoints, the maximum quantity will be defined as an input.

For this mission you need to complete the following function:

```c++
/**
 * Function to initialize an stack
 * @param Stack *sp
 * @param int size
 */
void initialize(Stack *sp, int size) {
    // Set the size of the array of TPoints allocated in Stack.
}
```

### Objective 3. Create a TPoint and add it to the Stack

For the moment you have an empty stack, so we need to create a TPoint and add it to the Stack, in this mission you will need to complete the following function:

```c++
void push(Stack *sp, char *id, float x, float y) {
    // Step 1. Create a TPoint using id, x and y.
    // Step 2. Insert TPoint in Stack
        
    // Consider what happens if the stack has reached its limit
}
```

### Objective 4. Extract a TPoint from the Stack

You must know this, but a Stack implements an structure called **FILO** (**F**irst **I**nput **L**ast **O**utput), so the first item will always be the las one extracted.

For this objective you must complete the following function:

```c++
void pop(Stack *sp) {
    // Step 1. Get the last item added to the stack
    // Step 2. Remove it from the stack.
    // Step 3. Print the item.

    // Consider what happens if the stack is empty.
}
```

### Objective 5. We need Control!

As you may noticed, you are testing individual functions, we need to control what we want to do (add, remove, initialize, exit). So we need to add a little control to our main function, this time will be on my count the control logic, complement with all your work!

```c++
int main() {

    int order;

    do {
        // Get Order from the user
        scanf("%d", &order);

        switch (order) {
            case 1: // Use Initialize()
                // size = Get from user
                break;
            case 2: // Use Push()
                // ID = "ID" + index of item (Generate yourself)
                // x = Get from user
                // y = Get from user
                break;
            case 3: // Use Pop()
                break;
            default: // print "Unknown Order"
                break;
        }
    } while (order != 4);

    return 0;
}
```

Once it's done.

Congratulations you have finished all the Stack Objectives!