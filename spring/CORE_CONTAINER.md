# Spring Core Container

*[:arrow_left: Go back to Spring](./SPRING.md)*

The core of Spring's mechanism to use IoC is named IoC container.

This container is a **long-live** instance that allows configuration of objects and is responsible for managing the creation of objects (beans), wiring and handle lifecycle for those objects.

## Container description

There are some aspects that describe the **container**

- Is a **long-live** object that lives throughout application lifetime.
- It is not a **singleton** because the same application can contain multiple containers, so it is not a unique instance to be reused.
- It is not **static** because the container is an object that have to be instantiated, an cannot be accessed directly without instantiating.
- The container is stored in the application context, that because can be globally accessible, but this does not mean that is static or singleton.
- Acts as a registry which contains all objects configured an are used by the application. But the responsibility goes beyond a simple object storage.

## Container flavors

Spring container has two main flavors or types

- BeanFactory
- ApplicationContext

### BeanFactory 

This is the main interface for a container implementation. That provides a basic usage.

Due to **BeanFactory** is an interface the default implementation is **DefaultListableBeanFactory**

##### BeanFactory responsibilities
- Instantiation: Can create and instantiate new bean instances based on the bean definitions and configuration provided.
- Configuration: Can configure bean instances using property setters, constructor arguments, and other configuration settings.
- Wiring and AutoWiring: Can wire dependencies between beans. It can inject one bean into another using constructor injection, setter injection, or field injection.
- Lifecycle management: Can manage the lifecycle of beans. It can create and destroy beans as needed, and it can also initialize and clean up beans.
- Scoping: Can manage bean scope. It can create and manage beans with different scopes such as singleton, prototype, request, session, etc.


### ApplicationContext

This type of container is basically a BeanFactory. This means that anything a bean factory can do, an application context can do as well.

They differ in the way that ApplicationContext, increase functionality and usage style.

Some feature that provides this container are:
- Internationalization support
- Event handling and notification with in the container
- Web application support
- Automatic bean post processing
- Environment-aware configuration that allows to access to properties defined to a specific environment.

## How wiring works

To wire beans spring use a **topological ordering**, this is a way of ordering (graph) a set of items based on their dependencies. The order ensures that if item A depends on item B, then B will always come before A in the ordering.

### Wiring vs AutoWiring
