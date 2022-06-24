[[Quality Attribute MOC]]

![[It is not the strongest of the species that survive, nor the most intelligent, but the one most responsive to change.#^quote]]

# Modifiability

Changes happens all the time, big time in software development.
We constantly optimize, fix, add, and remove features from our systems to keep them up to date and fast.

To plan for modifiability, we need to consider four questions:
1. _What can change?_ Basically everything. Dependencies can get outdated or updated, forcing changing to the features depending on it. Aspects of the system can, with new knowledge, rules, or laws, lack behind on accommodating the requirements, etc.
2. _What is the likelihood of the change?_ One cannot prepare for all changes. Take for example the log4j vulnerability. No one saw it coming, everyone relied on it. That change came out of the blue, and everyone had to fix it immediately.
3. _When is the change made and who makes it?_ Back in the days, developers were the ones making the changes, nowadays, we're used to systems that are customizable. We can change the screensavers ion our pc's, we can often rearrange most parts of the systems to suit our needs and style, and we can add to the system (programs, apps, etc.) at will. So to answer who makes the changes, _anyone_, even the system if it has incorporated AI.
4. _What is the cost of the change?_ Making a system more modifiable involves two types of costs
	- The cost of introducing the mechanism(s)/feature(s)
	- The cost of making the modification using the mechanism(s)/feature(s)

# The Cost Equation
$$N \cdot \text{Cost of making change without the mechanism} \leq $$
$$\text{Cost of creating the mechanism} + (N \cdot \text{cost of making the change using the mechanism})$$

**Cost** is not strictly a bad thing. Just like investments, investing money in modifiability may save money on future development, or even make the platform all the more profitable,

# The different flavors of change
- _Scalability_: [[Scaling|Horizontal and vertical scaling]]
- _Variability_: Unsure exactly what this means, but the closest I can think of is what systems like [[Kubernetes]]. It let's all sorts of systems work together side by side, without them necessarily having any relation or similarities in either structure, language, or function.
- _Portability_: Intertwined with the practices of [[Deployability|deployability]], but basically means encapsulating everything with as many dependencies as possible, much like [[JVM]], that gathers as many dependencies within a confined, portable, package.
- _Location independence_: Pretty much refers to [[Kubernetes]]. Everything is deployed within an ecosystem, and there's a [[Loadbalancer|loadbalancer]] distributing it's resources (nodes) to services that needs them.

---

# Modifiability General Scenario
|Portion of Scenario|Description|Possible Values|
|-------------------|-----------|---------------|
|Source|The agent that causes a change to be made. Most are human actors, but the system might be one that learns or self-modifies, in which case the source is the system itself.|End user, developer, system administrator, product line owner, the system itself.|
|Stimulus|The change that the system needs to accommodate. (For this categorization, we regard fixing a defect as it change, to something that presumably wasn't working correctly.)|A directive to add/delete/modify functionality, or change a quality attribute, capacity, platform, or technology; a directive to add a new product to a product line; a directive to change the location of a service to another location.|
|Artifact|The artifacts that are modified. Specific components or modules, the system's platform, its user interface, its environment, or another system with which it interoperates.|Code, data, interfaces, components, resources, test cases, configurations, documentation.|
|Environment|The time or stage at which the change is made.|Runtime, compile time, build time, initiation time, design time.|
|Response|Make the change and incorporate it into the system.|One or more of the following:<br>- Make modification<br>- Test modification<br>- Deploy modification<br>- Self-modify|
|Response measure|The resources that were expended to make the change.|Cost in terms of:<br>- Number, size, complexity of affected artifacts<br>- Effort<br>- Elapsed time<br>- Money (direct outlay or opportunity cost)<br>- Extend to which this modification affects other functions or quality attributes<br>- New defects introduces<br>- How long it took the system to adapt|

![[sample_concrete_modifiability_scenario.png]]

---

# Tactics for Modifiability
![[goal_of_modifiability_tactics.png]]

[[Coupling & Cohesion]]

Another characteristic is _the size of a module_. The bigger the module, there costlier and risky it is to modify. The chance of breaking something or introduce more bugs are higher. This also comes back to the **God Class**. Make sure the classes are as specialized as possible.

![[modifiability_tactics.png]]

## Increase Cohesion
- _Split module_: If a module consists of more responsibilities that are not cohesive, it's generally a good idea to split it up into multiple modules, in order to separate concerns.
- _Redistribute responsibility_: If a responsibility is contained within multiple modules, it always a good idea to restructure the modules and separate all the responsibilities once and for all. Having multiple modules covering a single responsibility is a recipe for disaster.

## Reduce coupling
- _Encapsulate_: [[Integrability#Encapsulate]]
- _Use intermediates_: [[Integrability#Use intermediaries]]
- _Abstract common services_: [[Integrability#Abstract Common Services]]
- _Restrict dependencies_: Restricting in this sense is, as it says, restricting. This could for example be a 3 layer architecture, where only the persistence layer should be able to query the data layer.

# Defer Binding
We want the system to be as flexible as possible, so we want to bind values as late as possible in the life cycle, although this comes at a cost, which bring actual use of the equation from before.

There are different tactics to bind at come or build time:
- _Component replacement_: Build or make script
- _[[Compile-time parameterization]]_: 
- _[[Aspects]]_: 

Tactics to bind values at deployment, startup time, or initialization time:
- _[[Configuration-time binding]]_: 
- _[[Resource files]]_:

Tactics to bind at runtime:
- _[[Discovery]]_: 
- _[[Interpret parameters]]_: 
- _[[Shared repositories]]_: 
- _[[Polymorphism]]_: 

# Patterns for Modifiability
## Client-Server Pattern
Web-server, basically. A constant service that serves whatever client that initiates a connection.

### Benefits
- The clients have no coupling what so ever
- "Easy" to scale, as we only need to give the server more horsepower. The clients are separate from client.
- Common services can be shared among multiple clients.

### Tradeoffs
- This pattern communicates over the internet, which brings its own problem, such as latency which affects [[Performance|performance]], and depending on what data the service send back and forth, may require extra attention on [[Security|security]].

## Plug-in (Microkernel) Pattern
Basically the same principle as a Linux kernel. Bare at its core, and as we assemble a given system, we "plug-in" modules and components, through fixed interfaces, that fit the case.

### Benefits
- Development is not limited to one team. As the interfaces are fixed, basically anyone can develop their own "plug-ins", update them independently, and service them.

### Tradeoffs
- Because anyone can develop plug-ins, it is easier to introduce [[Security|security]] vulnerabilities and privacy threats.

## Layers Pattern
The layered model we know and love.

### Benefits
- Allows for a lot of reuse, as there's high cohesion within layers.
- As the communication is grouped into _allowed-to-use_ relations, the number of interfaces are limited.

### Tradeoffs
- [[Performance]] can be impaired, if a call is made from the very top all the way down to the bottom.

## [[Publish-subscribe]]
The pubsub pattern runs on asynchronous events.

The publisher has no knowledge of the receiver, it just sends out events of defined types, and on the other side, the subscriber has no knowledge of any publishers, only the event types.
This results in loose coupling between the publishers and the subscribers.

There are three components to a pubsub:
- Publisher component
- Subscriber component
- Event bus, which acts as a middleman that manages the notifying in runtime.

### Benefits
- Very loose coupling. As long as the event-type is the same, and the event-value stays predictable, changes to either the publisher or subscriber has any impact on the other.
- Extension of the event-types or the number/variations of subscribers can be done with no impact on the other.
- As for everything else running over the internet, latency can occur if the pubsub gets substantial.
- As it is asynchronous, it's hard to predict when the subscriber gets the event.