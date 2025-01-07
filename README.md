# Firebase Data Access Error: Snapshot Not Fully Populated

This repository demonstrates a common error encountered when using the Firebase SDK: attempting to access properties of a document snapshot before the snapshot is fully populated. This often happens when dealing with asynchronous operations and not properly handling promises or async/await.

## Bug Description

The bug arises when trying to access fields within a Firebase document snapshot before the data has been fetched from the Firebase server.  This typically results in undefined values or errors being thrown.

## Bug Reproduction

1. Clone this repository.
2. Install the necessary dependencies using npm or yarn.
3. Run the `bug.js` file.  You'll likely observe an error due to data being accessed prematurely.
4. Run the `bugSolution.js` file. It demonstrates the corrected method, which waits for the data to be fully fetched before attempting to access it.

## Solution

The solution involves ensuring all data access happens only after the promise from the Firebase database operation is resolved. Using `then()` or `async/await` is the recommended approach to handle this asynchronously.