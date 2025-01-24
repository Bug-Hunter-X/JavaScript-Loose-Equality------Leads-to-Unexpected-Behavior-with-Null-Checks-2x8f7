# JavaScript Loose Equality (==) Leads to Unexpected Behavior with Null Checks

This repository demonstrates a common JavaScript error involving the loose equality operator (`==`) when checking for `null` values.  The loose equality operator can lead to unexpected type coercion, resulting in bugs that are difficult to track down.

## The Problem

The provided `foo` function uses `==` to check if either `a` or `b` is `null`.  This is problematic because `==` performs type coercion before comparison. For example `0 == null` evaluates to `false`, while `0 === null` evaluates to `false`, and `'0' == null` evaluates to `false` while `'0' === null` evaluates to `false`.  This means that certain values might be incorrectly treated as `null`.

## The Solution

The solution involves using the strict equality operator (`===`) which performs no type coercion.  This ensures that only values that are strictly equal to `null` will be considered `null`.

## How to Reproduce

1. Clone this repository.
2. Open `bug.js` and `bugSolution.js` to see the problematic code and its correction.
3. Run the files to observe the differences in behavior.