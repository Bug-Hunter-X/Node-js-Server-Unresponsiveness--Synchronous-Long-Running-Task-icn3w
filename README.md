# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js servers: unresponsiveness caused by long-running synchronous operations within the request handler.  The provided `server.js` file contains a simple HTTP server that simulates a 5-second CPU-bound task.  This blocks the event loop, preventing the server from responding to subsequent requests.

The solution (`serverSolution.js`) demonstrates how to address this using asynchronous operations or worker threads to prevent blocking the main thread and maintain server responsiveness.

## How to reproduce the bug:

1. Clone this repository.
2. Run `node server.js`.
3. Open multiple browser tabs and try to access `http://localhost:3000`. You'll notice that only the first request will get a response. Subsequent requests will hang.

## Solution:

The solution provided avoids blocking the main thread by using asynchronous operations or worker threads, allowing the server to handle multiple requests concurrently.