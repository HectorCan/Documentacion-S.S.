# How to Solve - Double Linked Lists

## Mission 8 - Create a  Double Linked List

Make a program that simulates a Double Linked List

For this task you will use the following structure:

```json
{
    "value": 1.300,
}
```

Each time you insert one element you should have the list in ascendant order. So the expected result after putting three elements i.e. values 8, 5, 10, is to have the following structure:

```json
{
    {
        "value": 5,
    },
    {
        "value": 8,
    },
    {
        "value": 10
    }
}
```

Keep the previous structure as an example of which order must be, not how the data will be in reality.

### Exploration - Double Linked Lists

As you should remember Simply Linked Lists are an structure that connects one data structure with another data structure of the same type. With this Link you know which element is the following.

But as you can see in the previous exercises we don't know which element is behind. Knowin which element is behind helps us to update the semifinal element to act as the final element (point towards itself). Otherwise you need to keep a control for the previous element.

You can define a double linked list like the following:

```json
{
    ...// values of the structure
    "next": *,
    "previous": *,
}
```

As you can see this structure will help us to order the elements that will be inserted in the list.

### Objective 1.- Let's structure our new Stack

As always we will be using our dear node structure:

```json
{
    "value": 1
}
```

With that our code will look like this:

```c++
typedef struct point {
    float value = 0;
} point;

struct node {
    point p;
    struct node * next = NULL;
    struct node * previous = NULL;
};

typedef struct node* List;
```

First we will explain the first block, the first block refers to the element that we are storing in our list. Our element is a defined type, so this "point" can have other parameters, like an ID, or some Weight.

The following block refers to our double linked list structure. This structure will help us to create an adequate ordered list.

### Objective 2. Adding more nodes

Remember, we want our points ordered by value in ascendant. As always we want to know if we can add a new node.

```c++
bool createListItem(List &myList);
bool add(List &myList, point au);
bool isEmpty(List &myList);

bool createListItem(List &myList)
{
    List item = new (struct node);
    item->next = item;
    item->prev = item;

    myList = item;

    if (myList == NULL) {
        return false;
    }

    return true;
}

bool isEmpty(List &myList)
{
    if (myList == NULL || myList->next == myList) {
        return true;
    }

    return false;
}

bool add(List &myList, point au)
{
    List iterator = myList, item;

    if (!createListItem(item)) {
        return false;
    }

    item->p = au;

    if (isEmpty(myList)) {
        myList = item;
    } else {
        // Iterate until the current element is higher than 
        // the element to add
        // OR when you reach the end
        while (iterator->p->value < item->p->value && iterator->next != iterator) {
            iterator = iterator->next;
        }

        // The current element is higher than the element to add
        if (iterator->p->value <= item->p->value) {
            // put after iterator
            if (iterator->next != iterator) {
                item->next = iterator->next;
            }

            iterator->next = item;
            item->prev = iterator;
        } else {
            // put before iterator
            if (iterator->prev != iterator) {
                item->prev = iterator->prev;
            }

            iterator->prev = item;
            item->next     = iterator;
        }
    }

    return true;
}
```

Kind of messy right? On this case is better if you have a notepad with you, so you can test manually if the direction that you are creating is the correct.

### Objective 3. I want to see the order!

We need our beloved print function to be sure that we are adding new values in the correct order;

```c++
void print(point *sp);
void printAll(List &myList);

void print(point *sp)
{
    printf("value: %.2f\n", sp->value);
}

void printAll(List &myList)
{
    List iterator = myList;

    if (!isEmpty(myList)) {
        while (iterator->next != iterator) {
            print(iterator->p);
            iterator->next = iterator;
        }

        print(iterator->p);
    }
}
```

Maybe we lost some lines of code with this implementation, but its easier to understand what are trying to achieve.

### Objective 4. 3R <3

Redo, Reuse or Recycle.

Our control (main function) should contain the following instructuions:

1. Add
2. List
3. Exit

**NOTE**: In the exercises maybe are extra options, these options are quite easy once you understand the previous code, also these options tend to be print an item or a list of items. Quite easy, there is no need for being included in the manual.