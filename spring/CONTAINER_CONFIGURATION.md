# Container configuration

*[:arrow_left: Go back to Core Container](./CORE_CONTAINER.md)*


First container load the configuration

Then asking the container for a bean trigger the creation and initialization of the bean, including the dependencies. 

Injecting dependencies triggers the creation of other beans, creating an entire graph of related objects.

## Basic configuration without bean creation

The following example shows how to load beans configuration but keep in mind that **this does not create the beans**, just load the configuration

```
//Location to configuration file
ClassPathResource res = new ClassPathResource("configuration.xml");

//Create the instance of the bean factory (container)
DefaultListableBeanFactory factory = new DefaultListableBeanFactory();

//Register the bean factory into the reader to load the configuration
XmlBeanDefinitionReader reader = new XmlBeanDefinitionReader(factory);

//Read the given configuration file and add the configuration to the registered bean factory
reader.loadBeanDefinitions(res);
```

With the previous configuration, to create a bean we need to ask the bean to the container, that will trigger the creation with their dependencies.

```
MyService myService = (MyService) factory.getBean("myService");
```

## Basic configuration with bean creation

Another example of configuration that involves the bean creation would be

```
ApplicationContext factory = new ClassPathXmlApplicationContext("application-context.xml");
```

This loads the configuration from xml file and also create the beans instances.


## Default bean scope

Every bean that is created by the container has scope by default. The scope is **singleton**, this means that the bean instance will be reused every time that is needed and will be live inside the container.

This mean the bean stateless or state is set only once at initialization time. This ensure that the bean is threadsafe.

## Autowiring

Using the attribute **autowire** 

Types of autowiring allowed in spring xml configuration:
- no
- byName
- byType
- constructor
- default: This the same as **no** 

*Using **byName** and **byType**, requires that the dependency implements a no-argument constructor and 
construcsetter methods.*


*@Autowired annotation is the same as autowire in xml bean element*

