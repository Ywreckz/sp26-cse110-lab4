# Part 2 - A Little More of a Challenge

## discountPrices with var

**Q1. What happens at line 12?**
`console.log(i)` prints `3`. Because `var` is function-scoped, `i` persists after the for loop ends, and its final value is 3 (the length of the prices array).

**Q2. What happens at line 13?**
`console.log(discountedPrice)` prints `150`. `var` is function-scoped, so `discountedPrice` is still accessible outside the loop. Its last value was 300 * (1 - 0.5) = 150.

**Q3. What happens at line 14?**
`console.log(finalPrice)` prints `150`. `finalPrice` is also `var` and function-scoped, so it's accessible here. Its last value was Math.round(150 * 100) / 100 = 150.

**Q4. What does this function return?**
Returns `[50, 100, 150]` — the discounted array containing each price multiplied by (1 - 0.5).

## discountPrices with let

**Q5. What happens at line 12?**
Error — `ReferenceError: i is not defined`. `let` is block-scoped, so `i` only exists inside the for loop and is not accessible outside it.

**Q6. What happens at line 13?**
Error — `ReferenceError: discountedPrice is not defined`. `let` is block-scoped, so `discountedPrice` only exists inside the for loop block.

**Q7. What happens at line 14?**
`console.log(finalPrice)` prints `150`. `finalPrice` is declared with `let` outside the loop (function body scope), so it is still accessible here. Its last value was 150.

**Q8. What does this function return?**
Returns `[50, 100, 150]` — same result as Q4, the discounted prices array.

## discountPrices with const

**Q9. What happens at line 11?**
Error — `ReferenceError: i is not defined`. `i` was declared with `let` inside the for loop, so it's block-scoped and not accessible outside it.

**Q10. What happens at line 12?**
`console.log(length)` prints `3`. `length` is declared with `const` in the function body, so it's accessible here.

**Q11. What does this function return?**
Returns `[50, 100, 150]` — the discounted prices array, same as before.

## Data Types - Object Notation

**Q12. Given the student object, write the notation for:**

A. `student.name`

B. `student['Grad Year']`

C. `student.greeting()`

D. `student['Favorite Teacher'].name`

E. `student.courseLoad[0]`

## Basic Operators & Type Conversion

**Arithmetic:**

- `'3' + 2` = `'32'` — the number 2 is converted to a string and concatenated.
- `'3' - 2` = `1` — the string '3' is converted to a number and subtracted.
- `3 + null` = `3` — null converts to 0.
- `'3' + null` = `'3null'` — null converts to the string 'null' and concatenates.
- `true + 3` = `4` — true converts to 1.
- `false + null` = `0` — false converts to 0, null converts to 0.
- `'3' + undefined` = `'3undefined'` — undefined converts to the string 'undefined'.
- `'3' - undefined` = `NaN` — undefined converts to NaN when used in subtraction.

**Comparison:**

- `'2' > 1` = `true` — '2' is converted to a number for comparison.
- `'2' < '12'` = `false` — both are strings, compared lexicographically; '2' > '1'.
- `2 == '2'` = `true` — loose equality converts '2' to a number.
- `2 === '2'` = `false` — strict equality, different types.
- `true == 2` = `false` — true converts to 1, and 1 != 2.
- `true === Boolean(2)` = `true` — Boolean(2) is true, both are true booleans.

**Q15. Difference between == and ===:**
`==` is loose equality and allows type conversion before comparing. `===` is strict equality and requires both value AND type to match — no conversion happens.

## Functions

**Q17. What will modifyArray([1,2,3], doSomething) return?**
Returns `[2, 4, 6]`. The `modifyArray` function loops through each element and calls `doSomething` on it, which multiplies each number by 2. So 1→2, 2→4, 3→6, and those get pushed into `newArr`.

## setInterval & setTimeout

**Q19. What is the output of the printNums code?**
1
4
3
2

`1` and `4` print immediately in order. The `setTimeout` with 0ms delay still gets pushed to the event queue and runs after the current synchronous code finishes, so `3` prints third. The `setTimeout` with 1000ms runs last, so `2` prints last.