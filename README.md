# Unresponsive Node.js Server

This repository demonstrates a common issue in Node.js applications: an unresponsive server caused by a long-running synchronous operation within the request handler.  The `server.js` file contains the buggy code, while `serverSolution.js` provides a solution using asynchronous operations.

## Problem

The server in `server.js` simulates a long-running task (a 5-second loop) within the request handler.  This blocks the event loop, preventing the server from handling subsequent requests until the task completes.  This results in unresponsiveness and potentially a poor user experience.

## Solution

The `serverSolution.js` file demonstrates how to address this by using asynchronous techniques.  Instead of blocking the event loop, the solution uses asynchronous operations (e.g., `setTimeout`) to perform the long-running task without blocking other requests.