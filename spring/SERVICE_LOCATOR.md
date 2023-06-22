# Service Locator

*[:arrow_left: Go back to IoC](./IoC.md)*

Service Locator is also a pattern that proposes an implementation for IoC principle.

This pattern proposes a kind of registry component which has the responsibility to create the dependencies that classes need.

In this case the class is abstracted from the dependency creation and just depends on the service locator to obtain the dependencies.

In service locator there are two concepts:

- Registry: It is a kind of storage which can be used to retrieve the dependencies.
- Container: This component is responsible for creating and manage dependencies lifecycle.

## Types of Service Locators

- Dependency pull: The dependencies are obtained by a lookup through a registry
- Contextualized Service Locator: The dependencies are retrieved by a lookup directly through the container.