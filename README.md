# Node.js HTTP Server Hang Without Content-Length Header

This repository demonstrates a common issue in Node.js HTTP servers where the server hangs if the response doesn't include a `Content-Length` header.  This typically happens when the response body's size is unknown beforehand.

## Bug

The `bug.js` file contains a simple HTTP server that sends a 'Hello World' response without specifying the `Content-Length` header.  This will cause the client to hang, waiting for the server to close the connection.

## Solution

The `bugSolution.js` file demonstrates the solution: adding the `Content-Length` header to the response.  This informs the client of the size of the response body, allowing it to properly close the connection.  Alternatively, you can use chunked transfer encoding if the response size is unknown at the beginning.