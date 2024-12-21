# Expo Document Picker - Silent Failure with Large Files or Permission Issues

This repository demonstrates a common, yet subtle, issue with Expo's Document Picker API.  When selecting large files or encountering permission problems, the API may return without an explicit error, resulting in empty or corrupted file data.

The `bug.js` file shows the problematic code where a file is selected but may fail silently with no proper error handling.  The `bugSolution.js` provides a more robust solution.  The solution includes detailed error handling and informative logging to pinpoint and handle exceptions from the native file picker.

## Reproduction
1. Clone this repository.
2. Run `npm install` or `yarn install`.
3. Run the application.
4. Attempt to select a large file (or a file which may have restricted access).
5. Observe the console logs and the file data.  With the `bug.js` version, an empty file will be reported.  With the `bugSolution.js` version, you'll see informative error messages.

## Solution
The key to addressing this issue is improved error handling and more informative logging.  The solution catches potential exceptions, logs meaningful details, and provides a clear indication of failure to the user.