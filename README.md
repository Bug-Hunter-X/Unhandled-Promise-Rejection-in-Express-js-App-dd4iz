# Unhandled Promise Rejection in Express.js

This example demonstrates a common error in Express.js applications: failure to properly handle promise rejections within asynchronous request handlers.

The `bug.js` file contains an Express app with an asynchronous route handler (`/`). This handler calls `someAsyncOperation()`, which randomly rejects a promise. However, the route handler lacks a `.catch()` block to handle this rejection, resulting in a silent failure or a crash depending on the Node.js environment.

The `bugSolution.js` file demonstrates how to correctly handle the promise rejection using a `.catch()` block. This ensures that errors are handled gracefully, preventing application crashes and providing informative error responses to the client.

## How to reproduce

1. Clone this repository.
2. Run `npm install` to install Express.js.
3. Run `node bug.js`. You will get varying results depending on whether the simulated error happens or not.
4. Run `node bugSolution.js`. You will see a more robust and consistent result.