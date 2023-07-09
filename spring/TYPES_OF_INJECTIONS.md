# Types of injection

*[:arrow_left: Go back to Dependency Injection](./DEPENDENCY_INJECTION.md)*

Spring provides some approaches to implement **Dependency Injection**.

- Constructor Injection
- Setter Injection
- Field Injection

## Constructor Injection

Constructor Injection occurs by using the constructor of a class, where every argument will be initialized with the corresponding instances.

This resolution matching occurs by using the **argument's type**. This means that an instances of a specific type has to be already created before, in order to fulfill constructor's arguments.

This type of injection has some advantages:
- Allows **immutability** of dependencies by using the **final** key word on class's fields.
- Avoid null dependencies and the need to non-null checks
- Helps in achieving a clear and consistent state of the object.
- It is easy to detect if a class has to many responsibilities.

But also has some disadvantages:
- May lead to circular dependencies when there are design problems.
- When having multiple dependencies makes it more verbose while mocking dependencies.

## Setter Injection

Setter injection occurs when dependency instances are injected through setter methods.

This type of injection has some advantages:
- It is useful while using optional dependencies.
- Allows to change dependencies in runtime.
- Can be used along with constructor injection.
- Can be used to inject multiple dependencies in a single method.

But also has son disadvantages:
- Using optional dependencies should always have default implementations
- May lead to null dependencies and null pointers errors.
- Make hard to detect if a class has too many responsibilities the more dependencies has.
- Immutability beans is not ensured while using optional dependencies.

Setter injection may be implemented in two main ways:
- Mandatory injection
- Optional injection


### Mandatory injection
This kind of injection means that dependencies must be injected while the bean is being created and implies that if some dependency is not ready will cause and error.

This injection is implemented using the `@Autowired` annotation in a specific setter method

```JAVA
@Autowired
public void setDependency(Dependency dependency) {
    ...
}
```

### Optional injection
This kind of injection means that a bean can be created without all of its dependencies injected and no errors will be thrown.

This injection can be implemented in several ways.

#### Regular Setter method

By default if a setter method is defined without any annotation spring will no invoke the setter method while bean creation.

```JAVA
public void setDependency(Dependency dependency) {
    ...
}
```

#### Autowired required property

The `@Autowired` annotation can be configured to skip the setter method invocation while bean creation if the dependency can be satisfied, using **required** parameter.

But keep in mind that if the dependency can be satisfied, the setter method will be invoked.

```JAVA
@Autowired(required = false)
public void setDependency(Dependency dependency) {
    ...
}
```

#### Other alternatives

Same behaviour can be achieved using annotations like `@Nullable` or `Optional` wrapper. Note that the setter method will be invoked but will not fail if the dependency cannot be satisfied.

```JAVA
@Autowired
public void setDependency(@Nullable Dependency dependency) {
    ...
}
```

## Field Injection

Field injection is a type of injection that does not uses constructor or setter methods to inject dependencies. This injection allows to inject dependencies instances to a specific fields even if they are private.

Field injection works with reflection to access the field directly and sets the value, this implies that the field must not be `final`.

This injection may be achieve using the `@Autowired` annotation in the specific field.

```JAVA
@Autowired
private Dependency dependency;
```

This type of injection has some advantages:
- Easy to write and less verbose.

But also has son disadvantages:
- The use of reflection may lead to performance issues.
- More prone to have lots of dependencies violating Single Responsibility Principle.
- Does not allow immutability of classes.
- May lead to circular dependencies and spring wont detect these scenarios.
- Testing is more error prone to have null dependencies.
- If using mockito to inject dependencies, if field injection fails mockito won't report the failure.