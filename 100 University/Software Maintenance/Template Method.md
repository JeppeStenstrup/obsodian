[[Design Patterns]]

# Template Method
Define the skeleton of an algorithm in an operation, deferring some steps to subclasses; lets subclasses redefine certain steps of an algorithm without changing the algorithm’s structure

## Goal
Define the skeleton of an algorithm in the framework, deferring application-specific steps or additions to the application-specific classes. From the framework’s point of view, connecting figures via a line is always the same operation.

From the application’s point of view, it is quite a difference depending on the semantics of the connection. To join these two views, the Template Method pattern is used.

The framework’s algorithm for connecting figures (its invariant parts) are placed in one class (LineConnection), exposing the variant parts of the algorithm in empty methods that subclasses can overwrite.

**Example**:
![[Pasted image 20220913103037.png]]

