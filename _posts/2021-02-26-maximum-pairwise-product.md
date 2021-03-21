---
layout: default
title:  "Maximum Pairwise Product"
date:   2021-02-26 17:23:45 -0800
categories: jekyll update
---

# Maximum Pairwise Product

Get the maximum pairwise product of two different elements in a sequence of non-negative integers.

> **Input:** A sequence of non-negative integers.
>
> **Output:** The maximum value that can be obtained by multiplying two different elements from the integer sequence.

Given a sequence of non-negative integers _a1_,...,_an_, compute:
> max _ai_ * _aj_ where 1 ≤ _i_ ≠ _j_ ≤ _n_

Note that _i_ and _j_ should be different, but it may be the case that _ai_ = _aj_. 

**Input format**: The first line contains an integer _n_. The next cointains a sequence of _n_ non-negative integers where _a1_,...,_an_ are separated by spaces.

**Output format**: The maximun pairwise product.

**Example**:

Input:
> 3
>
> 2 7 4

Output:
> 28

|       | **2** | **7** | **4** 
| **2** | | 14 | 8 |
| **7** | 14 |  | **28** | 
| **4** | 8 | 28 |  | 


## Naive Algorithm

```
maxPairwiseProductNaive(A[1..n]):
product <- 0
for i from 1 to n:
  from j from 1 to n:
    if i ≠ j:
      if product < A[i]*A[j]:
        product <- A[i]*A[j]
return product        
```
## Fast Algorithm

```
maxPairwiseProductFast(A[1..n]):
index1 <- 1
for i from 2 to n:
  if A[i] > A[index1]:
    index1 <- i
if index1 = 1:
  index2 = 2
else
  index2 = 1
from i from 1 to n:
  if i ≠ index1 and A[i] > A[index2]:
    index2 <- i
return A[index1] * A[index2]        
```

## Implementation

```python
def max_pairwise_product(numbers):
    index1 = 0
    n = len(numbers)
    for index in range(1, n):
        if numbers[index] > numbers[index1]:
            index1 = index
    if index1 == 0:
        index2 = 1
    else:
        index2 = 0
    for index in range(1, n):
        if index != index1 and numbers[index] > numbers[index2]:
            index2 = index
    return numbers[index1] * numbers[index2]
```

[Completed code](https://github.com/mauroLaine/algorithms/blob/main/w1/max_pairwise_product.py)