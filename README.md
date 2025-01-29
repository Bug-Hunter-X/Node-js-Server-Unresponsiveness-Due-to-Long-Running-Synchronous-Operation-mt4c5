# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js where a server becomes unresponsive due to a long-running synchronous operation blocking the event loop.  The `server.js` file contains the buggy code, while `serverSolution.js` provides a solution using asynchronous operations.

## Problem

The problem lies in the synchronous `while` loop within the request handler.  This loop keeps the CPU busy for 5 seconds, preventing the event loop from processing other requests or events.  This leads to the server appearing unresponsive during this period.

## Solution

The solution involves refactoring the code to use asynchronous operations.  Asynchronous operations allow other events to be processed while the long-running task is executing, preventing the server from becoming unresponsive.  This is demonstrated in `serverSolution.js`.