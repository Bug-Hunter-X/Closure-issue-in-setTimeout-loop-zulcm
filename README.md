# JavaScript Closure Issue in setTimeout Loop

This repository demonstrates a common JavaScript closure issue that arises when using `setTimeout` within a loop.  The problem stems from how JavaScript handles variable scoping and closures.

## Bug Description

The `bug.js` file contains a function that uses `setTimeout` to log the value of a loop counter. Due to the way closures work with `setTimeout`, the expected output (0, 1, 2,...9) isn't produced; instead, all logs show the final value of `i` (which is 10). This happens because the `setTimeout` callbacks only access the variable `i` after the loop has finished executing.

## Solution

The `bugSolution.js` file demonstrates the solution.  By using an immediately invoked function expression (IIFE) or `let` within the loop, a new scope is created for each iteration. This ensures that each `setTimeout` callback captures its own value of `i`, producing the expected output.