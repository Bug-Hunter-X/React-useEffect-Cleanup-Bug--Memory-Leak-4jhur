# React useEffect Cleanup Bug

This repository demonstrates a common bug in React applications involving the `useEffect` hook and its cleanup function. The example shows how forgetting to return a cleanup function from `useEffect` can lead to memory leaks.

## Bug Description

The `MyComponent` uses `setInterval` to update the counter every second.  However, the `useEffect` hook does not include a cleanup function to clear the interval when the component unmounts. This leads to a memory leak because the interval continues to run indefinitely, even after the component is removed from the DOM.

## Solution

The solution involves adding a cleanup function that uses `clearInterval` to stop the interval when the component unmounts.