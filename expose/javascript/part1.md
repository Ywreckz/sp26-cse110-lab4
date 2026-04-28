# Part 1 - Variables & Scoping

## var declaration

**Q1. What is printed by line 9?**
`values added: 20` — since `add` is true, we enter the if block, result becomes 10 + 10 = 20, and line 9 logs it.

**Q2. What is printed by line 13?**
`final result: 20` — because `var` has function scope, `result` is still accessible outside the if block.

**Q3. Why should you not use var?**
`var` has function scope instead of block scope, meaning variables declared inside if blocks or loops leak out into the rest of the function. This leads to unexpected bugs and naming conflicts.

## let declaration

**Q4. What is printed by line 9?**
`values added: 20` — same as Q1, `let` has block scope but we're still inside the block here.

**Q5. What is printed by line 13?**
Error — `ReferenceError: result is not defined`. `let` is block-scoped, so `result` only exists inside the if block and cannot be accessed on line 13.

## const declaration

**Q6. What is printed by line 9?**
Error — `TypeError: Assignment to constant variable`. Line 7 tries to reassign `result`, but `const` prevents reassignment.

**Q7. What is printed by line 13?**
Never reached — the error on line 7 crashes the program before getting here.