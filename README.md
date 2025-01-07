# Express.js Route Handler Error Handling
This repository demonstrates a common error in Express.js route handlers:  lack of error handling for invalid input.  Specifically, the example shows a route that retrieves a user by ID.  If the ID is not a valid integer, the code will crash.

The `bug.js` file contains the erroneous code. The `bugSolution.js` file provides a corrected version with proper error handling.

## Bug
The bug lies in the absence of error handling for non-numeric user IDs.  Attempting to parse a non-numeric string as an integer using `parseInt` will not throw an error but will result in `NaN`, leading to unexpected behavior.

## Solution
The solution involves adding error handling to check if `parseInt(userId)` results in `NaN`. If it does, the code returns a 400 Bad Request response, indicating invalid input.