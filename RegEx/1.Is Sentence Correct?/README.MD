# Is Sentence Correct?

**Implement the missing code, denoted by ellipses. You may not modify the pre-existing code.**

A sentence is considered correct if:

* it starts with a capital letter;
* it ends with a full stop, question mark or exclamation point (`'.'`, `'?'` or `'!'`);
* full stops, question marks and exclamation points don't appear anywhere else in the sentence.

Given a `sentence`, return `true` if it is correct and `false` otherwise.

## Example

* For `sentence = "This is an example of *correct* sentence."`, the output should be

    `isSentenceCorrect(sentence) = true`;

* For `sentence = "!this sentence is TOTALLY incorrecT"`, the output should be

    `isSentenceCorrect(sentence) = false`.

## Input/Output
* [**execution time limit**] 4 seconds (py3)
* [**input**] string `sentence`
  * Guaranteed constraints:
    * `2 ≤ sentence.length ≤ 100`.
* [**output**] boolean
  * `true` if the given `sentence` is correct, `false` otherwise.

---

`isSentenceCorrect.py`

```python
def isSentenceCorrect(sentence):
    pattern = r"^[A-Z][^.?!]*[.?!]$"
    return re.match(pattern, sentence) is not None
```


* `^[A-Z]`
  * start with Capital letter
* `[^.?!]*`
  * `[^.?!]` The middle must not be the letter `.`, `?`, `!`.
  *  `*` matches zero or more character
* `[.?!]$`
  * end with `.`, `?`, `!`.