# Unit Tests

- Having dirty tests is worse than having no tests
- Test code is just as important as production code
- It requires thought, design, and care
- Without tests you will be reluctant to make changes
- Tests makes the code flexible because we can make changes without fear

> Test enable change

## TDD
First write the test, make the test pass with the minimum production code and refactor.

## What is a clean test?

Readability, Readability, Readability 
- clarity, simplicity, expression
- the number of asserts in a test ought to be minimized.
- Single concept per test
- Domain specific language: Create an standard to write tests.
- Build-Operate-Check pattern: like given/when/then template

F.I.R.T.S
- Fast: Test should be fast
- Independent: Test should not depend on each other and should not set up the conditions for the next test
- Repeatable: Test should be repeatable in any environment.
- Self-Validating: Test should not required manual evaluation, they pass or fail.
- Timely(TDD): Test needs to be written just before the production code. This allows production code to be testable


## Not use inheritance in tests
- It use more CPU and has a mental price to pay (understanding it)
- Implies context switching
- It depends on context, and scenarios it is not a silver bullet.

## Context switching
Context switching has a price and is a mental draining.

We have to respect our own time and of our team members

- Do one thing at a time: first the most important tasks
- Try not to get interrupted if something needs to be done
- We cannot do everything.

There is time for collaboration and time to the heavy lifting.

## Naming fields in tests
Names should express purpose not types, so avoid using mock or sub suffix in names.

## Nested classes for test
Nested classes allow us to give a great context to every test.

When we can separate methods, use cases and behaviors. 
Also set specific setup for every set of tests, such as mocks, constants, etc...

Add nested classes where its name follows the convention of
[When][MethodName] i.e *WhenCreatingNewUser*

Then add new inner classes to the specific use case following the same naming convention.

The methods of this nested class follows the convention of
[Should][TestPurpose] i.e *ShouldCreateUser*

```
class UserRepository {
    class WhenCreatingNewUser {
        class WhenHasUniqueEmail {
            void shouldCreateUser()
        }
        class WhenHasRepeatedEmail {
            void shouldThrowDuplicatedEmailException()
        }
    }
}
```


## Avoid using magic numbers
Magic numbers has some consequences
- Magic numbers has just value not meaning.
- We have to deal with all occurrences.

Add constants depending on context
- The constant is need only in a specific class: 
Add to the specific class
- The constant is need for a multiple set of test classes:
Add it to a non-instantiable class. But this should be minimized cause this can cause side effects.


## Object Mother
## Fluent interface
## Behaviors driven development
## Factory methods or test data builders
## DSL 