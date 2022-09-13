[[Design Patterns]]

# State Pattern
Allow an object to alter its behavior when its internal state changes. The object will appear to change its class.

## When to use
- An object’s behavior depends on its state, and it must change its behavior at run-time depending on that state.
- Operations have large, multipart conditional statements that depend on the object’s state.

![[Pasted image 20220913102626.png]]

## Goal
Externalize the state of a tool. A tool can subdivide its state. This is necessary to provide means to make a tool operate in different modes (states).

**Example**: 
A drawing tool’s operation may differ whether the tool has already been used before and is obvious for toggling tools:
- zoom tool: toggle between ”zoom in” and ”zoom out”
- selection tool: toggle between ”select border” and ”select text”
![[Pasted image 20220913102813.png]]

## Consequences

Pros:
It localizes state-specific behavior and partitions behavior for different states. New states and transitions can be added easily by defining new subclasses.
- It makes state transitions explicit.
- State objects can be shared.