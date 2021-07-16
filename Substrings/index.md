# Instructions

**Problem**: Given two strings _**SA**_ and _**SB**_, make a function that return the position of _**SA**_ where the string _**SB**_ is substring of _**SA**_ for the first time, or -1 in other case.

**Note**: The function must be case sensitive.

**Definition**:
```
A string is considered as a substring if all their elements are in other string in the same order.
```

**Example**:

Given the following string, let's call it _**SA**_:

```
Hello world!
```

and the following string _**SB**_:

```
world
```


| H | e | l | l | o |  | w | o | r | l | d | ! |
|---|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|--:|
| 0 | 1 | 2 | 3 | 4 | 5 |`6`| 7 | 8 | 9 | 10 | 11 |


We can tell that _**SB**_ is a substring of _**SA**_, and it starts in position 6.

## Decompose

Sure you are wondering how I can get the position where _**SB**_ is located in _**SA**_.

The algorithm is the following:

1. Get the complete string (_**SA**_)
2. Get the string to search (_**SB**_)
3. Search _**SB**_ in _**SA**_.
    1. If found return the position of start.
    2. If not found return -1.

Steps 1 and 2 are easy, and can be accomplished with the following instruction:

```c
// Declarations
const ML = 100;
char sa[ML];

// Get string using scanf
scanf("%s", &sa);

// Get string using string.h (Note #include must be in their corresponding section)
#include <string.h> 

fgets(sa, ML, stdin);
```

To search the string, there are a few considerations:

1. You can be storing "\n" in your strings, keep only the string, and avoid further problems.
2. At the end of each string there is Null Character
3. The search is case sensitive, so world != WORLD.
4. You must return only the first occurrence.

A simple search algorithm would be:

1. Get the `length A` of _**SA**_.
2. Get the `length B` of _**SB**_.
3. if `length A` is lower than `
4. For each `index` of _**SA**_:
    1. Create a string _**SC**_ from _**SA**_ in position `index` to `index` + `length B`.
    2. Check if _**SB**_ is the same as _**SC**_.
    3. If so, return `index`
5. Return -1.

But you are free to create your own algorithm.

If you are facing problems to get the correct length of a string, you can test the following lines of code:

```c
#include <string.h>

strlen(stringA); // long unsigned int with the size of string.
```

With all this you can accomplish the task, Good Luck!.
