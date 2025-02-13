# Incorrect setInterval Usage in React Component

This repository demonstrates a common error when using `setInterval` within a React component's `useEffect` hook.  The provided `bug.js` file shows the problematic code, and `bugSolution.js` offers a corrected version.

The issue arises from the closure created by the callback function within `setInterval`. Each time the interval executes, a new closure is created, referencing a potentially stale value of `count`.  When `clearInterval` is called, the wrong interval might be cleared or it might not be cleared at all resulting in memory leak.

The solution involves using a ref to store the interval ID, ensuring that the correct interval is always cleared.