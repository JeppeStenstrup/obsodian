[[Design Patterns]]

# Decorator Pattern
Attach additional responsibilities to an object dynamically. Decorators provide a flexible alternative to subclassing for extending functionality.

![[Pasted image 20220913103210.png]]

## Usage
- To add responsibilities to individual objects dynamically and transparently, that is, without affecting other objects.
- For responsibilities that can be withdrawn.
- When extension by subclassing is impractical. Sometimes a large number of independent extensions are possible and would produce an explosion of subclasses.

## Structure
![[Pasted image 20220913103249.png]]

## [[JHotDraw Outline|JHotDraw]]

![[Pasted image 20220913103319.png]]

**Note**: A problem of the decorator pattern is that the type of the decorated object is difficult to obtain if:
- it is not made public by access methods like getDecoratedType() (the Java instanceof operator does not work) and
- no separate list of all figures (including the decorated) exists.

## Consequences

Pros:
- More flexibility than static inheritance.
- Avoids feature-laden classes high up in the hierarchy.

Cons:
- A decorator and its component aren’t identical.
- Lots of little objects.