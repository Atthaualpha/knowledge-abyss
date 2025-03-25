# Mutation Testing

Mutation testing is a fault-based testing technique used to evaluate the quality of test cases in a software application. The main idea behind mutation testing is to introduce small changes (mutations) to the code (known as "mutants") and then execute the existing test cases against these modified versions to determine if the tests can detect the changes.

- how do you know if those tests you've written are any good


¿Por qué no es suficiente la cobertura de código? La cobertura de código solo muestra qué partes del código se ejecutan durante las pruebas, pero no si las pruebas realmente detectan errores. "Mutation Testing" va un paso más allá al verificar si las pruebas pueden detectar cambios intencionales en el código.

> Mutation Testing is a White Box Testing

## Objectives:
- Identify pieces of code that are not tested properly
- Assess the quality of the test cases
- Identify hidden defects 

## Types:
- Value Mutations
- Decision Mutations
- Statement Mutations


## Key concepts
- Mutants
- Surviving Mutant
- Killed Mutant
- Mutation Score


## Challenges
- Performance Overhead
- Equivalent Mutants: Some mutations do not change the program's behavior and result in "equivalent mutants," which can complicate the testing process as they can confuse the assessment of test effectiveness.