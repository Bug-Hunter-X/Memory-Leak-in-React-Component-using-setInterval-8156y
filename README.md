# React setInterval Memory Leak

This repository demonstrates a common error in React applications: a memory leak caused by the improper use of `setInterval` within the `useEffect` hook.  The provided `bug.js` showcases the problematic code. The solution, `bugSolution.js`, demonstrates the correct implementation, preventing the leak.

## Bug
The original component uses `setInterval` to update the count every second. However, it lacks a cleanup function to clear the interval when the component unmounts. This results in the interval continuing to run even after the component is no longer needed, leading to a memory leak.

## Solution
The solution addresses this by using the cleanup function provided by the `useEffect` hook's return value. This function is executed when the component unmounts or when the dependencies array changes, ensuring that the interval is cleared properly, preventing the leak.