[[Architectural Solutions]]

# Software Interfaces
## Three initial points
1.  _All elements have interfaces._ All elements interact with some actors; otherwise, what is the point of the elements existence.
2.  _Interfaces are two-way._ When considering interfaces, most software engineers first think of a summary of what an element provides. What methods does the element make available? What events does it process? But an element also interacts with its environment by making use of resources external to it or by assuming that its environment behaves in a certain way. If these resources are missing or if the environment doesn't behave as expected, the element can't function correctly. So an interface is more than what is _provided_ bu an element; and interface also includes what is _required_ by an element.
3.  _An element can interact with mire than one actor through the same interface._ For example, web servers often restrict the number of HTTP connections that can be open simultaneously.

## Multiple Interfaces
It is possible to split a single interface into multiple interfaces.

## Resources
- _Resources syntax._ The syntax is the resource's signature, which includes any information that another program will need to write a syntactically correct program at uses the resource, The signature includes the name if the resource, the names and the data types of arguments, if any, and so forth.
- _Resource semantics._ What is the result of invoking this resource? Semantics come in a verity of guises, including the following:
	- Assignment of values to data that the actor invoking the resource can access. The value assignment might be as simple as setting the value of a return argument or as far-reaching as updating a central database.
	- Assumptions about the values crossing the interface.
	- Changes in the eleent's state brought about by using the resource. This includes exceptional conditions, such as side effects from a partially completed operation.
	- Events that will be signaled or messages that will be sent as a result of using the resource.
	- How other resources will behave differently in the future as the result of using this resource. For example, if you ask a resource to destroy an object, trying to access that object in the future through other resources could produce an error as a result.
	- Humanly observable results. These are prevalent in embedded systems. For example, calling a program that turns on a display in a cockpit has a very observable effect—the display comes on. In addition, the statement of semantics should make it clear whether the execution of the resource will be atomic or may be suspended or interrupted.

## Operations, Events, and Properties
The resources of provided interfaces consist of operations, events, and properties. These resources are complemented by an explicit description of the behavior caused or data exchanged when accessing each interface resource in terms of its syntax, structure, and semantics. (Without this description, how would the programmer or actor know whether or how to use the resources?)

_Operations_ are methods or functionality that processes data and, in most cases, return data(`void`, `string`, `Object<T>`, etc.). Just a normal method. It is in these methods that exception handling is implemented to make sure that any errors/faults in the system doesn't take the whole thing down.

_Events_ describes incoming events, local reference events, etc.
Events are usually asynchronous, and awaits passively until invoked.

In addition to the data transferred via operations and events, an important aspect of interfaces is metadata, such as access rights, units of measure, or formatting assumptions. Another name for this interface metadata is properties. Property values can influence the behavior of operations, as highlighted in the quotation that began this chapter. Property values also affect the behavior of the element, depending on its state.

Complex interfaces of elements that are both stateful and active will feature a combination of operations, events, and properties.