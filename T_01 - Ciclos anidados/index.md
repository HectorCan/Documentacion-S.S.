# How to solve Taylor's Approximation

## Mission 1 - Taylor's Approximation

Calculate the function $e^x$ using Taylor's Series Expansion.

The function $e^x$ is given by:

$e^x = 1 + x + $ $x^2 \over 2! $ $ + ... + $ $x^n \over n!$

### Objective 1 - Start from the basics

First you need to generate a function that implements the factorial $n!$

Remember a factorial is the multiplication from 1 to the $n$ number, so the factorial of 3 is $1 * 2 * 3$

```c++
int factorial(int n) {
    // return the multiplication from 1 to n
}
```

### Objective 2 - Going up!

You now can generate the divisor for each element, maybe you are wondering where are the divisor of $x$, but remember $x$ is always over 1

Now you must calculate the value of each element, so we are going to calculate the following expression:

$x^n \over n!$

```c++
int calculate_element(int x, int n) {
    // return (x ^ n) / n!
} 
```

### Objective 3 - Let's combine!

You have everything to finish this mission, you must combine what you have created to create the $e^x$ function.

```c++
int e_x(int x, int n) {
    // calculate e^x
}
```

If you need more help, read the following tips:

You can see in the $e^x$ function that there is some linear structure without the $ 1 + $, of course, each element has the structure: $x^n \over n!$

But what changes? Exactly $n$

$n$ is the only value that changes in each element, but you can see that this $n$ goes from 1 to the $n$ we have specified, so this is a for loop.

So the task becomes the following:

1. Sum = 1
2. For i = 1 to n
    1. Element = Calculate the element
    2. Sum = Sum + Element

Also, you can see that there is no need for any function, everything can be added in the for. So try putting all pieces of code together!
