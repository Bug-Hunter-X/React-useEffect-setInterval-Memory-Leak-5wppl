# React useEffect setInterval Memory Leak

This repository demonstrates a common error in React applications: memory leaks caused by improper use of `setInterval` within the `useEffect` hook.

## Bug Description
The `MyComponent` component uses `setInterval` to update the `count` state every second. However, the component fails to clear the interval when it unmounts, leading to a memory leak. This is because `setInterval` continues to run even after the component is removed from the DOM, resulting in unnecessary updates and potential performance issues.

## Solution
The solution involves returning a cleanup function from the `useEffect` hook, ensuring that the interval is cleared when the component unmounts.