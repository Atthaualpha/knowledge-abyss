# Objects and data structures

## Data abstraction

Hiding implementation is about abstraction.
- express data in abstract terms
- find the best way to represent the data that an object contains, without exposing implementations.

## Objects
Objects hide their **data** behind abstractions and expose functions that operate on that data.
## Structures
Structures expose their data and have no meaningful functions.

## Procedural code(code using data structures) 
- Makes it easy to add new functions without changing the existing data structures.
- Makes it hard to add new data structures because all the functions must change
## OO code
- Makes it easy too add new classes without changing existing functions
- Makes it hard to add new functions because all the classes must change.

> **Everything is an object is a myth**, sometimes we just need to have simple data structures with procedures operating on them..


## Data transfer object (DTO)

A DTO is a quintessential form a data structure, is a class with public variables and no functions. 
It is used to transfer data between layers commonly with databases, external APIs, sockets, etc.
Immutability is a good fit with DTOs 

# The Law of Demeter
This law is useful to keep lousy coupled our codebase and reinforce the concept of hide internal structures.

The law says that if we have a method *f* and a class *C*, then the method *f* should only call methods of
- The same class, in this case *C*
- And object created inside *f*
- And object passed as an argument to *f*
- And object held in an instance variable of *C*

In other words, **talk to friends, not to strangers**

Example
```
class C {

    Object obj;

    void f(p) {
        v() // call methods on same class
        
        new O().do() // methods of an object created by f

        p.do() // methods of arguments

        obj.do() // method of same object class
    }

    void v() {

    }

}
```

And avoid know the internal data of objects 
```
void f(p) {
   p.do().this().that()
}
```

Keep in mind that there are some cases when this law is broken that is why this is also called the Occasionally Useful Suggestion of Demeter.
