[[Design Patterns]]

# Prototype Pattern
Specify the kinds of objects to create using a prototypical instance, and create new objects by copying this prototype.

## When to use
- When the classes to instantiate are specified at run-time, for example, by dynamic loading.
- When building a class hierarchy of factories that parallels the class hierarchy of products should be avoided.
- instances of a class can have one of only a few different combinations of state.
- It may be more convenient to install a corresponding number of prototypes and clone them rather than instantiating the class manually.

## Structure
![[Pasted image 20220913103822.png]]

## Consequences
- It hides the concrete product classes from the clients, thereby reducing the number of names clients know about.
- It lets a client work with application-specific classes without modification.
- It lets you add and remove products at run-time.
- It lets you specify new objects by varying values.

# [[JHotDraw Outline|JHotDraw]]

Each tool is initialized with an instance (a prototype) of the figure it is meant to create. When creating a new figure, the tool clones the prototype.