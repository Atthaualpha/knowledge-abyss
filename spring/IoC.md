# Inversion of Control (IoC)

*[:arrow_left: Go back to Spring](./SPRING.md)*


Inversion of control is a **design principle** that claims that classes should not have the responsibility to *(create, control, manage)* the configuration needed to function. Classes should only "define" the configuration and *(invert,delegate)* this responsibility to an external *(component, assembler, framework, container)* to provide that configuration.

**In simple terms, class should not deal with dependency resolution, but rather delegate that task to something else, in order to loose coupling against implementations.**

> The real issue that IoC tries to deal with: **Separating configuration from use**

*Hollywood Principle: Don't call me, I'll call you*

## Types of IoC

- [Service locator](./SERVICE_LOCATOR.md)
- [Dependency injection](./DEPENDENCY_INJECTION.md)


