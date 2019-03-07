## Logical operators

*from: https://stackoverflow.com/questions/22646463/difference-between-and-boolean-vs-bitwise-in-python-why-difference-i*

- If you are not dealing with arrays and are not performing math manipulations of integers, you probably want `and`.
- If you have vectors of truth values that you wish to combine, use `numpy` with `&`.

*from: https://stackoverflow.com/questions/33384529/difference-between-numpy-logical-and-and*
- "Bitwise and" `(&)` behaves much the same as `logical_and` on boolean arrays, but it doesn't convey the intent as well as using `logical_and`, and raises the possibility of getting misleading answers in non-trivial cases (packed or sparse arrays, maybe).
- I have been googling some official confirmation that I can use `&` instead of `logical_and` on NumPy bool arrays, and found one in the NumPy v1.15 Manual: 
  > "If you know you have boolean arguments, you can get away with using NumPy’s bitwise operators, but be careful with parentheses, like this: z = (x > 1) & (x < 2). The absence of NumPy operator forms of logical_and and logical_or is an unfortunate consequence of Python’s design."
  So one can also use ~ for logical_not and | for logical_or.
