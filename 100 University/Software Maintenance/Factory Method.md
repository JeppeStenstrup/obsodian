[[Design Patterns]]

# Factory Method
Define an interface for creating an object, but let subclasses decide which class to instantiate. Factory Method lets a class defer instantiation to subclasses.

## When to use
- When a class can’t anticipate the class of objects it must create.
- When a class wants its subclasses to specify the objects it creates.
- When classes delegate responsibility to one of several helper subclasses, and you want to localize the knowledge of which helper subclass is the delegate.

## Structure
![[Pasted image 20220913103537.png]]

# [[JHotDraw Outline|JHotDraw]]

## Goal
Abstract from the concrete classes to be instantiated, which helps creation of customized components. This is used in JHotDraw to keep menus and tool structure flexible. Factory methods in the DrawApplication class are called createMenus() and createTools(). The customized application class (MyDrawApplication) inherits from DrawApplication and overwrites the createMenus() and createTools() methods.

![[Pasted image 20220913103638.png]]

## Consequences
- It provides hooks for the subclasses.
- It connects parallel class hierarchies.