# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: the lack of proper error handling for invalid input.  Specifically, this example shows a route that retrieves a user by ID.  The code has a vulnerability in that it doesn't handle cases where the user ID is not a valid number, leading to potential errors and application crashes.

The `bug.js` file contains the buggy code. The `bugSolution.js` file provides a corrected version with appropriate error handling.

## How to Reproduce
1. Clone this repository.
2. Navigate to the directory.
3. Run `node bug.js`.
4. Send a request to `/users/abc` (or any non-numeric ID). The application will crash.
5. Now run `node bugSolution.js` and test with same request, it should handle invalid input gracefully.

## Solution
The solution involves adding input validation to check if the user ID is a number before attempting to use it. If it's not a number, return a 400 Bad Request error.