# Clean code thoughts

*[:arrow_left: Go back](./BOOK.md)*

# Chapter 1:

- Later equals never
- Defend the code with passion
- the deadline cannot be make, making messes
- Code-sense is the key to clean code
- Code-sense allow programmers to see options and variations into a messy code
- programmers are artists

# What is clean code
- logic straightforward, that make hard to bugs hide
- Clean code, does one thing well.
- Code should be pleasing to read.
- Has minimum dependencies to ease maintenance.
- It should contain only what is necessary 
- Code, without tests, is not clean
- Smaller is better
- one method that says more clearly what it does, and some submethods saying how it is done.
- no duplications
- making it easy to read actually makes it easier to write


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