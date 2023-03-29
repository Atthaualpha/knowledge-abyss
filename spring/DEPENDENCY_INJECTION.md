# Dependency injection (DI)

*[:arrow_left: Go back to IoC](./IoC.md)*

Dependency injection can be thought as an implementation of IoC.
DI is a design pattern, this means that is the "how" IoC can be applied.


## How it works

DI solves a specific problem, *how to provide the dependencies(implementations) needed by a specific class?*. This means dependency creation and resolution. 

DI proposes that a class should define its dependencies in order to be provided by someone else. This way the class does not need to know how to get the dependencies. (This is also called as define the configuration to function)

### Example without DI

```
public class MessageService {

    public void sendMessage(Message message) {
        MessageSender sender = new MessageSender();

        sender.sendMessage(message);
    }
}

```

In the previous example, the **MessageService** has the responsibility to create the **MessageSender** this means that is coupled to that implementation.

This approach has some drawbacks
- Logic is coupled to specific implementations
- Is hard to test
- Hard to configure to work with different implementations.

### Example with DI

```
public class MessageService {

    private final MessageSender sender;

    public MessageService(MessageSender sender) {
        this.sender = sender;
    }

    public void sendMessage(Message message) {
        sender.sendMessage(message);
    }
}

```

In this example, the **MessageService** does not have the responsibility to create the instance to work with the **MessageSender**, this means that does not need to know create this dependency.

This has some advantages:

- Reduce the glue code: this means that the creation of dependencies is not tied up to the class.
- Easy to test: Now to test or mock the behavior of MessageSender, is easy, because with DI, we can provide different implementations.
- Allows design guided by interfaces: This improve abstraction and reduce coupling complexity.

Also some disadvantages:
- While the injection is made in runtime, it may lead to problems if implementation provided is wrong.
- If overused may lead to maintenance problems.

## Types of DI

There are some types of DI implementations
- Constructor injection
- Setter inject

*Additional injection would be **field injection**, which uses reflection to set dependency value, but using reflection has some performance implications and it is easy to broke Single Responsibility Principle (SRP)*