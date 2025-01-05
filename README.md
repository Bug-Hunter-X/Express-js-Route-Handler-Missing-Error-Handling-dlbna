# Express.js Route Handler Missing Error Handling

This example demonstrates a common error in Express.js route handlers: missing error handling for invalid input.  Specifically, the route `/users/:id` does not handle cases where `req.params.id` is not a valid number or when no user with the given ID exists.

The `bug.js` file contains the buggy code.  The `bugSolution.js` file provides a corrected version with proper error handling.

## Bug

The original code attempts to parse the user ID as an integer using `parseInt(userId)`.  However, it does not check if the result of `parseInt` is actually a number or if a user with that ID exists.  This can lead to errors if the user ID is not a valid integer or if a user with that ID is not found in the `users` array.

## Solution

The solution adds checks to ensure the user ID is a valid number and that a user with that ID exists.  If either condition is false, an appropriate error response (404 Not Found) is returned.