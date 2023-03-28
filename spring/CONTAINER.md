# Spring container

### Core container or spring container
Is collection of objects called beans, that are instantiated, configured and wired together.

> Spring container can be thought of as an object storage that has additional features to manage and manipulate those objects

> Spring container is a long-lived object it is not static nor singleton.
> it is not singleton because an application may have multiple containers so it is not just a unique instance.
> it is not static because a container is an instance of a BeanFactory cannot be accessed directly without this instantiation.
> the container is stored in the application context of the application ¿does spring has a static variable where the container is stored?

**spring boot has application context that allows global access to spring container, without spring boot this global access have to be done manually by declaring a static variable and store there the container**

> To wire beans spring use a **topological ordering** is a way of ordering (graph) a set of items based on their dependencies. The order ensures that if item A depends on item B, then B will always come before A in the ordering.

Any bean factory allows the configuration and
wiring together of objects using dependency injection, in a consistent and workable fashion. A bean factory also provides some management of these objects, with respect to their lifecycles.

This objects are stored into maps to facilitate their access

Flavors:
- BeanFactory: lightweight container for basic container uses, such as
- ApplicationContext: more featured container that allows, internationalization, event publishing, web applications, etc.

#### Bean factory operations
- Instantiation: BeanFactory can create and instantiate new bean instances based on the bean definitions and configuration provided.
- Configuration: BeanFactory can configure bean instances using property setters, constructor arguments, and other configuration settings.
- Wiring: BeanFactory can wire dependencies between beans. It can inject one bean into another using constructor injection, setter injection, or field injection.
- Lifecycle management: BeanFactory can manage the lifecycle of beans. It can create and destroy beans as needed, and it can also initialize and clean up beans.
- Scoping: BeanFactory can manage bean scope. It can create and manage beans with different scopes such as singleton, prototype, request, session, etc.