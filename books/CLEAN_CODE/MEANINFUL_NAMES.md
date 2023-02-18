*[:arrow_left: Go back to Clean Code](./CLEAN_CODE_BOOK.md)*


# Meaningful names
- Choosing good names takes time
- change them when you find better ones
- names must not be implicit but explicit
- conditionals to a intention-revealing function to hide complexity
> change `if (i.get(0) == "active")` 

> to `if(i.isActive())`

- to not use the container type in names (i.e accountList when List is the container type)
- do not use names that can be vary in small ways (**ControllerToHandleString**, **ControllerToStoreString**)
- Use pronounceable names
- single-letter can ONLY be used as local variables in short methods
``` 
for (i=1;i<clients.size();i++){ 
    COUNT_OF_CLIENTS += i
}
```
- use searchable names
- do not use colloquialisms or slang
- one word per concept
- use technical names, such as patterns, math terms, algorithms, etc
- Shorter names are generally better than longer ones, so long as they are clear
- names must be precise
### Names with measures
 When using names to something that is used to measure, specify the unit of that measurement.

### Distinguishable names
Names must express meaning and avoid noise such as **Product** and **ProductInfo**.

Make them distinguishable from name and purpose, not just for name.

Use prefix conventions such as
- a: for local variables like aClient
- the: for function arguments like theCustomer

### Class names
Classes and objects should have nouns and avoid Data, Info, Manager in the name.
Never use verbs in class names
#### constructors
When constructors are overloaded use static factory methods with a name that describe the arguments
> `Customer aCustomer = Customer.debtor(100);`
instead of 
> `Customer aCustomer = new Customer(100);`
### Methods names
Methods should have verbs 