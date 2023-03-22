# Boundaries

Interface providers strive for broad applicability but users want an interface that is focused in specific needs.

- If a boundary interface is used, keep it inside a class or close to where it is used. Avoid returning it from public API

- Learning third-party code is hard
- Integrating third-party code is hard.
- We should avoid our code knows about the third-party code.
- Prefer depending on something that you control
- Manage third party boundaries having very few places in the code that refer to them.
- Wrap them or use adapters

## Learning tests
Learning tests is a technique that allow us to first test the third-party code that we want to integrate into our productive code.
With this approach we just focus on understand how the external code works, and if it suite to our use cases.

Advantages:
- Learning tests are free, we have to learn the API anyway
- We create isolated tests
- Increase our understanding of the API
- Help us to reduce risk when updating the external APIs

## Working with code that does not exist (yet)

- Define our own interface, with the signature that we would **wish** it would have
- Create a fake implementation.
- Use adapter pattern when integrating the real API 