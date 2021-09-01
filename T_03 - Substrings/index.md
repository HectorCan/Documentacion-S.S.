# Instructions

**Problem**: Given two strings $S_a$ and $S_b$, make a function that return the position where the string $S_b$ is substring of $S_a$ for the first time, or -1 in other case.

_The function must be case sensitive._

**Definition**:
```
A string is considered as a substring if all their elements are in other string in the same order.
```

**Example**:

Given the following string, let's call it $S_a$:

```
Hello world!
```

and the following string $S_b$:

```
world
```


| H | e | l | l | o |  | w | o | r | l | d | ! |
|---|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|--:|
| 0 | 1 | 2 | 3 | 4 | 5 |`6`| 7 | 8 | 9 | 10 | 11 |


We can tell that $S_b$ is a substring of $S_a$, and it starts in position 6.

## Decompose

Sure you are wondering how I can get the position where $S_b$ is located in $S_a$.

The algorithm is the following:

1. Get the complete string $S_a$
2. Get the string to search $S_b$
3. Search $S_b$ in $S_a$.
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

You need to consider the following:

1. Avoid null characters at the end of string.
2. Remember is case sensitive so World != wOrLD.
3. Remember return the first ocurrency.

A simple search algorithm would be:

1. $LS_A = length$ of $S_a$
2. $LS_B = length$ of $S_b$
3. $i = 0, j= 0$
3. While $i < LS_A$
    1. If `character[i]` $S_a$ equals `character[j]` in $S_b$.
        1. Increment $j$ by 1.
    2. If not equals
        1. Set $j = 0$
    3. Increment $i$ by 1.
    4. If all characters in $S_b$ were found
        1. return $i - j$ 
4. Return $-1$.

But you are free to create your own algorithm.

If you are facing problems to get the correct length of a string, you can test the following lines of code:

```c
#include <string.h>

strlen(stringA); // long unsigned int with the size of string.
```

With all this you can accomplish the task, Good Luck!.
