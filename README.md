# React useEffect Infinite Loop Bug

This repository demonstrates a common React bug: an infinite loop caused by incorrect usage of the `useEffect` hook.  The `useEffect` hook in `bug.js` attempts to update the `count` state within its own effect, leading to a continuous re-render cycle.

## Bug Description
The provided `MyComponent` utilizes `useEffect` to increment the count state.  However, the dependency array is empty (`[]`), meaning the effect runs after every render, leading to a continuous update and an infinite loop.  This is demonstrated with a simple counter that rapidly increases until the browser crashes or the tab becomes unresponsive.

## Solution
The solution, found in `bugSolution.js`, demonstrates how to avoid this infinite loop by properly managing the dependencies of the effect.  By adding `count` to the dependency array, the effect only runs when `count` changes which is what we intended, breaking the infinite loop. 

## How to reproduce
Clone this repo and run `npm start` to observe the problematic behavior. The corrected code showcases a safe implementation of useEffect.