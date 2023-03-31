# Container configuration

First container load the configuration

Then asking the container for a bean trigger the creation and initialization of the bean, including the dependencies. 

Injecting dependencies triggers the creation of other beans, creating an entire graph of related objects.

## Basic configuration

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