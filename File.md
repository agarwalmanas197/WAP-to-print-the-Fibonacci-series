# The Fibonacci numbers are the numbers in the following integer sequence.
```
0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, ……..
```
In mathematical terms, the sequence Fn of Fibonacci numbers is defined by the recurrence relation
```
    Fn = Fn-1 + Fn-2
```
with seed values
```
   F0 = 0 and F1 = 1.
 ```

Given a number n, print n-th Fibonacci Number.
Examples:
```
Input  : n = 2
Output : 1

Input  : n = 9
Output : 34
```
Write a function int fib(int n) that returns Fn. For example, if n = 0, then fib() should return 0. If n = 1, then it should return 1. For n > 1, it should return Fn-1 + Fn-2
```
For n = 9
Output:34
```
A simple method that is a direct recursive implementation mathematical recurrence relation given above.

### Fibonacci Series using Recursion 
```
#include<stdio.h> 

int fib(int n) 
{ 

   if (n <= 1) 

      return n; 

   return fib(n-1) + fib(n-2); 
} 

  

int main () 
{ 

  int n = 9; 

  printf("%d", fib(n)); 

  getchar(); 

  return 0; 
}
```
### Output
```
34
``` 
Time Complexity: T(n) = T(n-1) + T(n-2) which is exponential.
We can observe that this implementation does a lot of repeated work (see the following recursion tree). So this is a bad implementation for nth Fibonacci number
```

                       fib(5)   
                     /                \
               fib(4)                fib(3)   
             /        \              /       \ 
         fib(3)      fib(2)         fib(2)   fib(1)
        /    \       /    \        /      \
  fib(2)   fib(1)  fib(1) fib(0) fib(1) fib(0)
  /     \
fib(1) fib(0)
```
Extra Space: O(n) if we consider the function call stack size, otherwise O(1).
