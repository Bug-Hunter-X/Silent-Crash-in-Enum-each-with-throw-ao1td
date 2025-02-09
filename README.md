# Silent Crash in Elixir's Enum.each

This example demonstrates a situation where using `throw` inside `Enum.each` can lead to a silent crash in your Elixir program.  The error isn't caught, and there's no informative error message.

The `bug.ex` file contains the problematic code. The solution, `bugSolution.ex`, shows how to properly handle exceptions.

This is an uncommon error because many developers expect `throw` to be handled by some higher level mechanism, but this isn't true in this case for `Enum.each`.

## How to Reproduce

1. Run `bug.ex`
2. Observe the crash, the code will simply exit without providing context on why it did so.

## Solution

Use a `try-catch` block to properly handle the thrown exception, improving debugging and preventing unexpected program termination.  See the improved implementation in `bugSolution.ex`.