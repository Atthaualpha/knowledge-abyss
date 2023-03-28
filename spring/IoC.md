# Inversion of Control (IoC)

Inversion of control is a design principle that claims that classes should not have the responsibility to *(create, control, manage)* the configuration needed to function. Classes should only "define" the configuration and *(invert,delegate)* this responsibility to an external *(component, assembler, framework, container)* to provide that configuration.

**In simple terms, class should not deal with dependency resolution, but rather delegate that task to something else, in order achieve loose coupling with implementations.**

> IoC tries to deal with the real issue: **Separating configuration from use**

## Types of IoC

- Service locator
- Dependency injection


## Service locator

Types of service locator (lookup)

- Dependency pull
- Contextualized Service Locator

## Dependency injection

*Hollywood Principle: Don't call me, I'll call you*

Types of dependency injection

- Setter injection
- Constructor injection

*Additional injection would be **field injection**, which uses reflection to set dependency value, but using reflection has some performance implications.*
