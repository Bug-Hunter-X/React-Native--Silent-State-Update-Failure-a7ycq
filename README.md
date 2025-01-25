# React Native Silent State Update Failure

This repository demonstrates a common, yet subtle, bug in React Native applications where state updates might not trigger a re-render if the update happens outside the component's main rendering logic.  The issue is often tricky to debug as it doesn't produce a clear error message.

## Problem
The `bug.js` file showcases a scenario where modifying the state using a spread operator (`...`) within an event handler doesn't reflect the changes in the UI. This is because directly changing the state variable doesn't trigger React's reconciliation process, which is responsible for updating the UI.

## Solution
The `bugSolution.js` provides a correct implementation, using the `setState` function provided by React. Using the `setState` function enforces React's update cycle, ensuring that the component re-renders properly when state values change.

## How to Reproduce
1. Clone the repository.
2. Navigate to the directory.
3. Run `npm install`
4. Run `npx react-native run-android` (or `npx react-native run-ios`) 
5. Observe the incorrect behavior in `bug.js` and then the correct behavior in `bugSolution.js`
