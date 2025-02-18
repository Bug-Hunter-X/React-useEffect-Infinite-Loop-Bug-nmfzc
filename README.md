# React useEffect Infinite Loop Bug

This repository demonstrates a common React bug involving the `useEffect` hook causing an infinite loop. The problem arises from an improperly defined dependency array, leading to the effect running on every render.

## Bug Description
The `useEffect` hook in `bug.js` is designed to log the current count to the console. However, because the dependency array `[count]` is not optimized, the effect re-runs whenever the `count` state changes, which happens every time the button is clicked. This creates an infinite loop, causing the console to be spammed and potentially affecting application performance.

## Bug Solution
The `bugSolution.js` file provides a corrected version of the code.  By omitting the dependency array (or using an empty array `[]`), the effect will only run once after the initial render, or only on unmount if the empty array is used and the cleanup function is added.  This resolves the infinite loop issue.