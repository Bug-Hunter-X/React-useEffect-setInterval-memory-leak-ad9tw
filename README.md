# React useEffect setInterval memory leak

This repository demonstrates a common mistake when using the `setInterval` function within a React `useEffect` hook.  The issue arises from failing to properly clean up the interval, leading to a memory leak.

## Bug
The `bug.js` file contains a React component that uses `setInterval` to update a counter every second. However, it lacks the necessary cleanup function to clear the interval when the component unmounts or when the dependencies change.  This results in the interval continuing to run even after the component is no longer needed, causing a memory leak.

## Solution
The `bugSolution.js` file provides a corrected version of the component. It includes a cleanup function that uses `clearInterval` to stop the interval when the component unmounts.  This effectively prevents the memory leak.