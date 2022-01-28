# Operators and Loops

[Article to reference for the below operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#assignment_operators)

## Assignment operators

An assignment operators assigns a value to its left operand based on the value of its right operand.
- the simple assignment operator is `=` such that `x = f()` is an assignment expression that assigns the value of `f()` to `x`

Some compound assignment operators include:
- addition assignment as `x += f()` meaning x = x + f()
- (following same structure as above for subtraction, multiplication, division, remainder, and exponentiation, with `-`, `*`, `/`, `%`, and `**`, respectively
- there are also directional shift assignments, bitwise assignments, and logical assignments

## Comparison operators

- Equal: `==` returns `true` if the operands are equal
- Not equal `!=` returns `true` if the operands are not equal
- Strict equal `===` returns `true` if operands are equal and of the same type (number or string)
- Strict not equal `!==` returns `true` if the operands are of the same type but not equal, or are equal but of different type (ex. 3 and three)
- Greater than `>`, greater than or equal `>=`, less than `<`, and less than or equal `<=` are all pretty self-explanatory.

## For loops

A `for` loop repeats until a specified condition evaluates to `false`. It looks like:
```
for ([initialExpression]; [conditionExpression]; [incrementExpression])
  statement
```
- when for loop executes, following occurs:
1. the initializing expression `initialExpression` is executed (usually the expression itself encounters one or more loop counters, but it can be as complex as you want). It can also declare variables.
2. the `conditionExpression` is evaluated, and if true, loop statements will execute. If condition is false, the `for` loop terminates. (if `condition` expression is omitted entirely, condition is assumed to be true.)
3. the `statement` executes. To execute multiple statements, use a block statement of form `({ ... ])` to group the statements.
4. if present, the update expression `incrementExpression` is executed.
5. control flow returns to step 2.

A `while` loop executes its statements as long as a specified condition evaluates to `true`. A while statement looks like:
```
while (condition)
  statement
```
- if the condition becomes `false`, `statement` within the loop stops executing and control passes to the statement following the loop.
- the condition test occures *before* `statement` in the loop is executed. If the condition returns `false`, execution stops, and control is passed to the statement following `while`.
- to execute multiple statements, use block statement of form `({ ...})` to group the statements.
example (this `while` loop iterates as long as `n` is less than `3`:
```
let n = 0;
let x = 0;
while (n < 3) {
  n++;
  x += n;
 }
```
- with each iteration, the loop increments `n` and add that value to `x`. So after each pass, `x` and `n` take on the following values:
1. first pass: `n` = `1` and `x` = `1`
2. second pass: `n` = `3` and `x` = `6`
3. third pass: `n` = `3` and `x` = `6`
- after completing the third pass, the condition `n < 3` is no longer `true`, so the loop terminates.


WHILE vs FOR
- While - count / until ; For - loop through x number until hitting limit of x ?
