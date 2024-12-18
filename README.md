# Express.js - req.body is empty despite using express.json()

This repository demonstrates a common issue in Express.js applications where the `req.body` is empty even after using the `express.json()` middleware. This often occurs due to incorrect middleware order or missing configuration.

## Bug Report

The `bug.js` file contains an Express.js application that attempts to parse a JSON request body. Despite using `express.json()`, the `req.body` remains empty.

## Solution

The `bugSolution.js` file provides a corrected version of the application. The solution ensures that `express.json()` is placed correctly in the middleware stack and handles potential issues with the request content type.

## How to reproduce the bug:

1. Clone this repository.
2. Navigate to the directory.
3. Run `node bug.js`.
4. Send a POST request to `http://localhost:3000/data` with a JSON payload.
5. Observe that the server logs an empty `req.body`.

## How to fix the bug:

1. Review the `bugSolution.js` for the fix implementation.
2. Ensure the `express.json()` middleware is placed before the route handler.
3. Verify that the request is actually sending a JSON payload with the correct content type (application/json).