# Insertion Sort

## How to sort

- You are a Teaching Assistant for a course
- The instructor gives you a stack of exam answers papers with marks, ordered randomly
- Your task is to arrange them in descending order

## Strategy 2

- Firts paper: put in new stack
- Second paper:
  - Lower marks than first ? Place below first paper
  - Higher marks than first ? Place above first paper
- Third Paper:
  - Insert into the correct position with respect to first two paper
- Do this for each subsequent paper:
  - Insert into correct position in new sorted stack

```python

def insertionSort(seq):
    for sliceEnd in range(len(seq)):

        # Build longer and longer sorted slices
        # In each iteration seq[0:sliceEnd] already sorted


        # Move First element after sorted slice left
        # till it is in the correct place

        pos = sliceEnd

        while pos > 0 and  seq[pos] < seq[pos-1]:
            (seq[pos], seq[pos-1]) = (seq[pos-1], seq[pos])
            pos = pos - 1



```

## Analysis of insertionSort

- Inserting a new value in sorted segment of length k requires upto k steps in the worst case

- In each iteration, sorted segment in which to insert increased by 1

- $ T(n) $ = $ 1 + 2 + ................+ n-1 $ = $ n(n-1)/2 = O(n^2) $
