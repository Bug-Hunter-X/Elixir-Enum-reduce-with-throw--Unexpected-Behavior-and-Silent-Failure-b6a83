# Elixir Enum.reduce with throw: Unexpected Behavior and Silent Failure

This example demonstrates a potential issue when using `throw` within `Enum.reduce`. If the `throw` is not handled properly, it can lead to unexpected behavior, making debugging difficult.

## Bug Description
The provided Elixir code uses `Enum.reduce` to sum a list. However, if the number 3 is encountered, `throw` is used to interrupt the reduction. The problem arises if this `throw` is not caught using a `try...catch` block, leading to a silent failure or masking other potential errors.

## Reproduction
1. Run the code in `bug.ex`.
2. Observe that no error is explicitly raised, and the `Enum.reduce` does not return the expected sum.

## Solution
The solution involves using a `try...catch` block to handle the `:three_found` exception. This allows for more graceful error handling and prevents silent failures.

## How to run the code
1. Make sure you have Elixir installed.
2. Save the code in files named `bug.ex` and `bugSolution.ex`.
3. Run the code using `elixir bug.ex` and `elixir bugSolution.ex` respectively.
