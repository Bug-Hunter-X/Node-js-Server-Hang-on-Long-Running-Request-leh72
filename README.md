# Node.js Server Hang on Long-Running Request

This repository demonstrates a common issue in Node.js where a long-running synchronous operation blocks the event loop, preventing the server from handling subsequent requests.  The `server.js` file contains the buggy code, while `server-solution.js` provides a corrected version.

## Problem

The server uses a `while` loop to simulate a task taking 5 seconds. During this time, the event loop is blocked, and the server becomes unresponsive to new requests.  This is a classic example of how blocking operations can cripple Node.js's non-blocking, event-driven architecture.

## Solution

The solution uses asynchronous operations or offloads the long-running task to a worker thread, worker pool or other background processes, preventing the blocking of the event loop and ensuring responsiveness.