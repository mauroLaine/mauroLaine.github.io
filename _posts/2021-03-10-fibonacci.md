---
layout: default
title:  "Fibonacci Number"
date:   2021-03-10 17:23:45 -0800
categories: algorithms
---

# Fibonacci Number

Calculate the _n_-th Fibonacci number.

> **Input:** An integer _n_.
>
> **Output:** _n_-th Fibonacci number.
>
> Fn = F(n-1) + F(n-2)

Fibonacci numbers are defined recursively:
> F(n) = 
>
>           n                  if n is 0 or 1
>
>           F(n-1) + F(n-2)    if n ≥ 2  


**Input format**: An integer _n_.

**Output format**: Fn.

**Example**:

Input:
> 10

Output:
> 55



## Naive algorithm

```
fibonacci(n):
if n ≤ 1:
    return n
return fibonacci(n-1) + fibonacci(n-2)            
```
## Fast algorithm

```
fibonacciList(n):
create an array F(0...n)
F[0] <- 0
F[1] <- 1
for i from 2 to n:
    F[i] <- F[i-1] + F[i-2]
return F[n]         
```

## Python implementation

```python
def fib_list(n):
    number_list = [None] * (n + 1)
    number_list[0] = 0
    number_list[1] = 1
    for i in range(2, n + 1):
        number_list[i] = number_list[i - 1] + number_list[i - 2]
    return number_list[n]
```

[Completed code](https://github.com/mauroLaine/algorithms/blob/main/w2/fibonacci.py)