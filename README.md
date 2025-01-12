# Stale Closure in React's useState with setInterval

This example demonstrates a common mistake when using React's `useState` hook with `setInterval`.  The issue arises from the closure over the `count` variable, resulting in stale closure and incorrect updates.

## Problem

The provided code attempts to increment a counter every second. However, because `setCount(count + 1)` uses the initial value of `count` captured during the render, the counter does not increase correctly.  Each interval callback uses the value of `count` from when the `useEffect` hook ran.

## Solution

The correct way to update state is to use the functional update form of `setCount` which accepts the previous state as an argument, ensuring that you are always working with the latest value.