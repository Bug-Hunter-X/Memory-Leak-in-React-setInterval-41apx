# React setInterval Memory Leak
This repository demonstrates a common error in React applications: memory leaks caused by improper use of `setInterval` within the `useEffect` hook.  The `bug.js` file contains the buggy code, while `bugSolution.js` provides the corrected version.

## Problem
The original code uses `setInterval` to update a counter every second.  However, it fails to provide a cleanup function within the `useEffect` hook to clear the interval when the component unmounts. This results in a memory leak because the interval continues to run even after the component is no longer needed.

## Solution
The solution clears the interval using `clearInterval` in the cleanup function returned by `useEffect`. This ensures that the interval is properly stopped when the component unmounts, preventing the memory leak.