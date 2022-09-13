[[Design Patterns]]

# Composite Pattern
Compose objects into tree structures to represent part-whole hierarchies. Composite lets clients treat individual objects and compositions of objects uniformly.

## When to use?
- When you want to represent whole-part- hierarchies of objects.
- When you want clients to be able to ignore the difference between compositions of objects and individual objects. Clients will treat all objects in the composite structure uniformly.

## Structure
![[Pasted image 20220913101642.png]]
![[Pasted image 20220913101658.png]]

## [[JHotDraw Outline|JHotDraw]]

A figure is composed of several figures. Composite figure as well as child figures are treated uniformly. Operations performed on either of the figures will exert a common behavior on all figures (scale, rotation, move).

**Example**: A composite figure consisting of 5 subordinate figures.

![[Pasted image 20220913101735.png]]

This allows for nested structures of arbitrary depth, and uniformly handling of all objects forming a composite.

![[Pasted image 20220913101910.png]]

## Consequences

Pros:
- Wherever client code expects a primitive object, it can also take a composite object.
- Makes the client simple. Clients can treat composite structures and individual objects uniformly, and this simplifies their code.
- Makes it easier to add new kinds of components. Clients don’t have to be changed for new Component classes.

Cons:
- Can make your design overly general. It makes it harder to restrict the components of a composite.
	- If you want a composite to have only certain components, you can’t rely on the type system to enforce those constraints for you. You’ll have to use run-time checks instead.