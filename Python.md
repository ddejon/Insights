## Built-in functions

- Python 2.7: https://docs.python.org/2.7/library/functions.html
- Python 3.6: https://docs.python.org/3.6/library/functions.html

## Infinite loop
Use `while 1:`, more efficient than `while true:` (single jump operation)

## Logical operators

*from: https://stackoverflow.com/questions/22646463/difference-between-and-boolean-vs-bitwise-in-python-why-difference-i*

- If you are not dealing with arrays and are not performing math manipulations of integers, you probably want `and`.
- If you have vectors of truth values that you wish to combine, use `numpy` with `&`.

*from: https://stackoverflow.com/questions/33384529/difference-between-numpy-logical-and-and*
- "Bitwise and" `(&)` behaves much the same as `logical_and` on boolean arrays, but it doesn't convey the intent as well as using `logical_and`, and raises the possibility of getting misleading answers in non-trivial cases (packed or sparse arrays, maybe).
- I have been googling some official confirmation that I can use `&` instead of `logical_and` on NumPy bool arrays, and found one in the NumPy v1.15 Manual:
  > "If you know you have boolean arguments, you can get away with using NumPy’s bitwise operators, but be careful with parentheses, like this: z = (x > 1) & (x < 2). The absence of NumPy operator forms of logical_and and logical_or is an unfortunate consequence of Python’s design."

  So one can also use ~ for logical_not and | for logical_or.

## Looping
*from: https://treyhunner.com/2016/04/how-to-loop-with-indexes-in-python/*

- loop over a list while keeping track of indexes with `enumerate`:
```python
colors = ["red", "green", "blue", "purple"]
ratios = [0.2, 0.3, 0.1, 0.4]
for i, color in enumerate(colors):
    ratio = ratios[i]
    print("{}% {}".format(ratio * 100, color))
```
- loop over multiple lists at the same time with `zip`:
```python
for header, rows in zip(headers, columns):
    print("{}: {}".format(header, ", ".join(rows)))
```

## Operator precedence
http://www.mathcs.emory.edu/~valerie/courses/fall10/155/resources/op_precedence.html (cheat sheet)
Documentation in Python docs: https://docs.python.org/3/reference/expressions.html
