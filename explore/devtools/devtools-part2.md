# DevTools Part 2 - Debugging

**What was the bug?**
num1 and num2 are retrieved from the DOM as strings using `.value`. When passed to calculateSum, the + operator concatenates them as strings instead of adding them as numbers (e.g. "2" + "3" = "23" instead of 5).

**How to fix it?**
Convert num1 and num2 to numbers before passing them to calculateSum. Change lines 3-4 in explore.js to:

`let num1 = Number(document.getElementById("num1").value);`
`let num2 = Number(document.getElementById("num2").value);`