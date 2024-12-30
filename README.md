# Express.js Route Handler Missing Error Handling for Invalid User IDs

This repository demonstrates a common error in Express.js route handlers:  failure to handle cases where input data is invalid or missing.  Specifically, this example shows a route that fetches a user by ID but lacks error handling if the ID is not a valid integer.

## Bug

The `bug.js` file contains an Express.js route handler that attempts to fetch a user from an array using the `req.params.id`.  It uses `parseInt` to convert the ID to an integer, but doesn't check if the conversion was successful, or handle the case where no user with the given ID exists. This could result in the application crashing if the user provides an invalid ID.

## Solution

The `bugSolution.js` file provides a corrected version of the route handler.  It includes explicit error handling using `isNaN` to check if the parsed ID is a number and also handles the case where the user is not found, sending a 404 response appropriately.

## How to Run

1. Clone this repository.
2. Navigate to the repository's directory in your terminal.
3. Run `npm install express` to install the necessary dependencies.
4. Run `node bug.js` (to reproduce the bug) or `node bugSolution.js` (to see the solution).