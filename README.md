# React useEffect Hook Memory Leak with setInterval

This example demonstrates a common mistake in React when using the `useEffect` hook with `setInterval`.  Forgetting to properly clear the interval leads to a memory leak.

## Bug
The `bug.js` file contains a React component that uses `setInterval` to update a counter every second.  However, it fails to clear the interval when the component unmounts, resulting in a memory leak. 

## Solution
The `bugSolution.js` file shows the corrected version. It uses the return value of `setInterval` within `useEffect` to store the interval ID.  A cleanup function is then added to `useEffect` to `clearInterval` when the component unmounts, preventing the memory leak.