# How to use a Hash Tables

## Mission 10 Make a search with Hash tables

First we have to create our node structure, and fill it. 


```C++
{ 
    char Nickname[30]; // Put a size for our node 
    NodeHash *prev; // Prev node 
    NodeHash *next; // Next node 
}
```

As always, this guide will help you to accomplish this mission.

The hash table belongs to the category of dictionaries that are data structures and algorithms that allow searching, inserting and discarding elements. 

This is how a Hash table looks like: 

![Simple Linked List](./img/T-Hash_1.png)

But how it works?.

When we use a hash table, we assign a specific memory space to store information, we use a Hash function which consists of getting the best value to store it. 

### Hash Function: 

But,we can make a perfect Hash function? 

Yes, but a good hash function satisfies (approximately) the assumption of simple uniform hashing: each key is equally likely to hash to any of the m slots, independently of where any other key has hashed to. Unfortunately, we typically have no way to check this condition, since we rarely know the probability distribution from which the keys are drawn. Moreover, the keys might not be drawn independently. Occasionally we do know the distribution. 

For Example: if we know that the
keys are random real numbers k independently and uniformly distributed in the
range $$ 0 \leqslant k < 1 $$ 

then the hash function is: 

$$ h = k [km] $$

In this occasion the Hash Function Satisfies the condition of simple hashing. 


### Insert 

??

```C++

int i = 0; 

While(i == m){
    j = HashFunc(k,i) // We call the Hash Function to insert in the Key 
    if(T[j] == NULL){ // Search in the Hash Table 
        T[j] = k; // We check the Key in the Hash Table 
        return j;
    } 
    else{ 
        i = i+1
    }
}

```

### Search 

If you want to search, you should use the HASH Function and then search in the queue using the specific index.

```C++

int index = HashFunc(x);  //Compute the index by using the function

//Search the linked list at that specific index


```