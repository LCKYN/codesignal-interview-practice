# missingNumber

You are supposed to label a bunch of boxes with numbers from `0` to `n`, and all the labels are stored in the array `arr`. Unfortunately one of the labels is missing. Your task is to find it.

## Example

* For `arr = [3, 1, 0]`, the output should be
 
    `missingNumber(arr) = 2`.

## Input/Output
* [**execution time limit**] 4 seconds (py3)
* [**input**] array.integer `arr`

    An unsorted array consisting of different integers from `0` to `n` inclusive, with only one of them missing.

  * Guaranteed constraints:
    * `1 ≤ arr.length ≤ 1000`.
    * `0 ≤ arr[i] ≤ arr.length`.
* [**output**] integer

    The missing number.

---

`missingNumber.py`

```python
def missingNumber(arr):
    return sum(range(len(arr) + 1)) - sum(arr)
```

Only one number is missing from the array. And the array has numbers from `0` to `n`. To make it easy to understand An example will be the sorted value

ex.

missing number = 3

array length = 5

|index|element|
|:--:|:--:|
|0|0|
|1|1|
|2|2|
|3|4|
|4|5|

`sum(range(len(arr) + 1))` = 0 + 1 + 2 + 3 + 4 + 5 

`sum(arr)` = 0 + 1 + 2 + 4 + 5

Both start from `0` and ends with `n`. But the sum of `sum (arr)` is less than `sum(range(len(arr) + 1))` equal to the missing number.

---
`missingNumber2.py`

```python
def missingNumber(arr):
    n = len(arr)
    return n*(n+1)/2 - sum(arr)
```
same as `missingNumber.py` 

change `sum(range(len(arr) + 1))` to summation formula

sum from 0 to n = `n*(n+1)/2`

---
`missingNumber3.py`

```python
def missingNumber(arr):
    res = 0
    for i,v in enumerate(arr):
        res ^= (i + 1) ^ v
    return res
```

ex. from `missingNumber.py`

all number from `sum(range(len(arr) + 1))` and `sum(arr)` = 

`[0, 0, 1, 1, 2, 2, 3, 4, 4, 5, 5]`

same as [link](Bits/1.singleNumber/README.MD)