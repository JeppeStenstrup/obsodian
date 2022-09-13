[[Design Patterns]]

# Strategy Pattern
Define a family of algorithms, encapsulate each one, and make them interchangeable. Strategy lets the algorithm vary independently from clients that use it.

## When to use
- Many related classes differ only in their behavior. Strategies provide a way to configure a class with one of many behaviors.
- You need different variants of an algorithm. For example, you might define algorithms reflecting different space/time trade-offs.
- An algorithm uses data that clients shouldn’t know about. Use the Strategy pattern to avoid exposing complex, algorithm-specific data structures.
- A class defines many behaviors, and these appear as multiple conditional statements in its operations.

## Structure
![[Pasted image 20220913102306.png]]

It has advantages to separate layout algorithms from objects to be laid out (see also Java AWT, Swing). Here, the Strategy Pattern is used.

Every layouter (Java Swing / AWT: layout manager) can be attached to a composite figure rendering it.

![[Pasted image 20220913102412.png]]

## Consequences

Pros:
- Families of related algorithms.
- An alternative to subclassing.
- Strategies eliminate conditional statements.
- A choice of implementations. Strategies can provide different implementations of the same behavior. The client can choose among strategies with different time and space trade-offs.

Cons:
- Clients must be aware of different Strategies.
- Communication overhead between Strategy and Context.
- Increased number of objects.