Test Driven Development (TDD)

*[:arrow_left: Go back to home](../README.md)*

Key concepts:
- red, green, refactor cycle
- think of examples and outcome, not the implementations and details
- write the minimum code that is needed to make the test pass
- each test should validate one single piece of logic
- The code that is produced is, by design, easy to test.
-By addressing the simplest tasks, your code is less prone to errors 
-In general, tests should not need to be changed during the refactor stage.
# red phase
-You have to write a test that uses a piece of code as if it were already implemented
- This is the phase where you design how your code will be used by clients.
-Forget about the implementation
# green phase
- you need to act like a programmer who has one simple task: write a straightforward solution that makes the test pass
- The to-do list is live: it changes while you are coding with doubts, problems, etc.
# refactor phase
- Removing code duplication often results in abstraction. 


rules:
- Write only enough of a unit test to fail.
- Write only enough production code to make the failing unit test pass.

