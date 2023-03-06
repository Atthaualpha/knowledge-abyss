# Error handling

Handle errors is important but must not obscure the code.


## Tips
- Separate logic from error handling.
- Try blocks are like transactions and catch blocs leaves the program in a consistent state.
- Write first the try-catch-finally statements.
- When handle exception first using TDD throws Exception, then narrow the scope of the exception
- Use unchecked exceptions: 
The price of using checked exceptions is an open/closed principle violation and encapsulation because any changes made to throw an exception means changes all callers of that method and also expose internal details.
Checked exceptions are useful when writing critical libraries.
- Provide context in messages exceptions
- Define exceptions Classes in terms o a caller's needs: This means that we should concern about how they are caught. A best practice is by wrapping the API we are calling and make sure that it returns a common exception type. 

This means create method or class method where the logic to catch the API exceptions in wrapping within that logic, and when a caller needs this API can deal with a common exception type.
- Use the *special case pattern*: where you create a class that handles the special case, and hide this logic from the caller
- Don't pass null: This imply extra effort for callers
    - Return null from methods is bad
    - Pass null into methods is worse: Forbid pass nulls to arguments
## Wrapping third-party APIs or libraries:
Wrap external APIs in order to throw custom exceptions, some advantages are:
- Minimize the dependencies
- Easy to mock testing code
- The code is not tied to a particular vendor's API
