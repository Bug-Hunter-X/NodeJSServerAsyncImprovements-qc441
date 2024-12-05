# Node.js Server Unresponsiveness Bug

This repository demonstrates a common Node.js issue: server unresponsiveness caused by a long-running synchronous operation blocking the event loop.

## Bug Description

The `bug.js` file contains a simple HTTP server.  However, the request handler includes a `while` loop that keeps the CPU busy for 5 seconds. This synchronous operation blocks the event loop, making the server unresponsive to new requests during that time.

## Solution

The `bugSolution.js` file demonstrates the solution: offloading the long-running task to a separate process or using asynchronous operations (e.g., timers, promises, async/await).  This prevents the event loop from being blocked, ensuring the server remains responsive.

## How to Reproduce

1. Clone this repository.
2. Run `node bug.js`.
3. Try making multiple requests to the server (e.g., using `curl` or a browser). Observe the server's unresponsiveness.
4. Run `node bugSolution.js` and repeat the request tests, noting the improved responsiveness. 
