# React 18 useEffect Infinite Loop Bug

This repository demonstrates a common error in React 18 involving the `useEffect` hook.  Incorrect usage can lead to an infinite render loop, significantly impacting performance.

## Problem

The provided `MyComponent` uses `useEffect` without a dependency array (`[]`). This causes the effect to run after every render, creating a cycle:  the effect updates the state, triggering a re-render, which runs the effect again, and so on.

## Solution

The `bugSolution.js` file shows the corrected code.  Adding an empty dependency array (`[]`) ensures the effect runs only once after the initial render.  Alternatively, specify dependencies to control when the effect runs, ensuring it is only triggered when necessary.