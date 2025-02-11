# Infinite useEffect Loop in React

This repository demonstrates a common error in React applications: an infinite loop caused by an improperly configured `useEffect` hook.  The problem arises when a state variable used within the `useEffect` is not included in its dependency array.  This leads to the effect running continuously, often causing performance issues or crashes.

## The Bug

The `bug.js` file contains a React component with an `useEffect` hook that attempts to log the current count.  However, the `count` variable is not listed in the dependency array.  This causes React to re-run the effect after every render, creating an infinite loop of console logs.

## The Solution

The `bugSolution.js` file shows the corrected code.  By adding `count` to the dependency array, `useEffect` only runs when the `count` value changes.