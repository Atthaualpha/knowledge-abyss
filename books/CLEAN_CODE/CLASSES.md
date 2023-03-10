# Classes

## Organization
- public static constants
- private static variables
- private instance variables
- public functions
- private functions

## Classes should be small

The measure the determinate how small a class should be it due to responsibilities. 
A useful way to define the responsibility of a class is through its name, the more
ambiguous the name the more responsibilities will have.

## Single Responsibility principle (SRP)

A guideline to know the class size is the SRP, which says that a class should have just one and only on reason to change (by change we mean responsibilities). In other words gather together the things that change by the same reason. (Cohesion)

This help us to create better abstractions.

To put in practice this principle we should avoid:
> thinking that we are done when the program works

We have to instead of going to the next problem, take a look back at the code and focus on organization and cleanliness

## Cohesion

Cohesion is the measure of how much the logic inside a class is its related to it.

To maximize the cohesion the methods in a class should use the maximum number of instance variables and methods variables. 

This means that if the number of methods using those variables will increase the relationship to the class.

When we have multiple variables that are just used by a subset of methods, the class has a lose cohesion. 

**To increase cohesion we must split the classes into many with high cohesion.**

## Organization for changes

- We must reduce the risk of change
- When we found ourselves opening up a class to modify it by more than one reason (responsibility) we must change our design
- Classes should be open for extension closed by modification
- Concrete classes has implementation details
- abstract classes represent concepts only
- We should depend on concepts not in details.
- Dependency inversion principle, our classes should depend on abstraction not on concrete details
