# React 19 useEffect Cleanup Issue
This example demonstrates a common mistake in React 18 and 19's `useEffect` hook:  forgetting to clean up intervals or timeouts.  This can lead to memory leaks and unexpected behavior when the component unmounts. The `bug.js` file contains the erroneous code. The `bugSolution.js` file provides the corrected version.

## Problem
The `setInterval` function within the `useEffect` hook in `bug.js` continues to run even after the component is unmounted. This is because there's no mechanism to stop the interval. This results in unnecessary updates and, eventually, memory leaks.

## Solution
The `bugSolution.js` file shows the correct implementation. It uses the return value of `useEffect` to provide a cleanup function. This cleanup function stops the interval when the component unmounts, resolving the memory leak.