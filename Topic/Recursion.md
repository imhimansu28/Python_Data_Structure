# Recursion

## Inductive definitions

Many airthmetic functions are naturally defined inductively

- **Factorial**

  - $ 0! = 1 $
  - $ n! = n * (n-1)! $

- **Multiplication** - repeated addition

  - $ m * 1 = m $
  - $ m *(n+1) = m+(m*n) $

- Define one or more base cases

- Inductive step defines f(n) in terms of smaller arguments

## Recursive computation

- Inductive definitions naturally give rise to recursive programs

```Python


def factorial(n):
    if n == 0:
        return(1)
    else:
        return(n* factorial(n-1))


```

## Inductive definitions for list

- Lists can be decomposed as
  - Firt (or last) element
  - Remaining list with one less element
- Define list function inductively
  - Base case: empty list or lis of size 1
  - Inductive Step: $ f(l) $ in term of smaller of $ l $

### Length of a list

``` python

def length(l):
  if l == []:
    return(0)
  else:
    return(1+length(l[l:0]))



```

### Sum of a list of Numbers

```python

def sumlist(l):
  if l == []:
    return(0)
  else:
    return(l[0]+ sumlist(l[l:0]))


```

## Recursion limit in Python

- Python sets a recursion limit of about 1000

```Console
>>> l = list(range(1000,0,-1))
>>> InsertionSort(l)
........

RecursionError: maximum recursion  depth exceeded in comparison


```

- Can manually raise the limit

```Console

>>> import sys

>>> sys.setrecursionlimit(10000)


```

## Recursive insertion sort

- $ T(n) $, time to  run  insertion sort on length n
  - Time $ T(n-1)$ to sort slice **seq[0:n-1]**
  - $ n-1 $ steps to insert **seq[n-1]** in sorted slice

- Recurrence
  - $ T(n) = n-1 + T(n-1)$
  - $ T(1) = 1$
- $T(n) = n-1 + T(n-1) = n-1 + ((n-2)+T(n-2))=..
  .=(n-1)+(n-2)+..+1 = n(n-1)/2 = O(n^2)$
