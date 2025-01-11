# React Native useCallback Hook Bug: Missing Dependency

This repository demonstrates a common but subtle bug that can occur when using the `useCallback` hook in React Native.  The bug arises when a function passed to `useCallback` relies on a state variable, but that state variable is omitted from the dependency array.

## Bug Description

The issue is demonstrated in `bug.js`. The `buggyIncrement` function uses `setCount` to increment the count, but it doesn't include `count` in its dependency array.  As a result, even though the function's logic doesn't change, a new function instance is created every render, leading to unexpected behavior and potentially breaking component functionality. 

## Solution

The solution is shown in `bugSolution.js` and involves correctly specifying the state variable `count` as a dependency of `useCallback`.

## How to Reproduce

1. Clone this repository.
2. Run `npm install`.
3. Run the project using your preferred React Native method (e.g., `npx react-native run-android` or `npx react-native run-ios`).
4. Observe the difference in behavior between the "Increment" button (correct use of useCallback) and the "Buggy Increment" button (incorrect use of useCallback).
