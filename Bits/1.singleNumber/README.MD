# singleNumber

**Implement the missing code, denoted by ellipses. You may not modify the pre-existing code.**

You are given an array of integers in which every element appears twice, except for one. Find the element that only appears one time. Your solution should have a linear runtime complexity (`O(n)`). Try to implement it without using extra memory.

## Example

* For `nums = [2, 2, 1]`, the output should be

    `singleNumber(nums) = 1`.

## Input/Output
* [**execution time limit**] 4 seconds (py3)
* [**input**] array.integer `nums`
  * Guaranteed constraints:
    * `1 ≤ nums.length < 10,000`.
    * `-1,000,000,000 ≤ nums[i] ≤ 1,000,000,000`
* [**output**] integer

---

`singleNumber.py`

```python
def singleNumber(nums):
    res = 0
    for num in nums:
        res ^= num 
    return res
```

bitwise exclusive OR (XOR) 

python :`x ^ y`

**truth table**

| x | y | x (xor) y |
|:--:|:--:|:--:|
|T|T|F|
|T|F|T|
|F|T|T|
|F|F|F|

from the truth table when x and y are equal. That value will disappear.

ex.

5 = `0b101`

3 = `0b011`

`input = [5, 3, 5]`

5(`101`) xor 3(`011`) = 6(`110`)

6(`110`) xor 5(`101`) = 3(`011`)