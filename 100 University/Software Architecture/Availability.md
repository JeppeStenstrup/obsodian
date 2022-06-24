[[Quality Attribute MOC]]

# Availability

A failures cause is called a _fault_. A fault can be either internal or external to the system under consideration.

Example: A user inputs non-accepted data into a form (fault), there are no sanitation or exception handling (failure), system crashes (unavailable).

Availability refers to a property of software - namely, that it is there and ready to carry out its task when you need it to be.

It encompasses the ability of a system to mask or repair faults such that they don’t become failures.

This ensures that the service outtage does not exceed a required value over a specified amount of time, and further builds on top of reliabilty, rubustness, and any other [[Quality Attribute|QA]] that involves a concept of unacceptable failure.

A systems failures are observable by users (in one way or another).

---

# Availability General Scenario

|Portion of Scenario|Description|Possible Values|
|-------------------|-----------|---------------|
|Source|This specifies where the fault comes from|Internal/external: people, hardware, software,| physical infrastructure, physical environment
|Stimulus|The stimulus to an availability scenario is a fault|Fault: omission, crash, incorrect timing, incorrect response
|Artifact|This specifies which portions of the system are responsible for and affected by the fault|Processors, communication channels, storage, processes, affected artifacs in the system's environment|
|Environment|We may be interested in not only how a system behaves in its "normal" encironment, but also how it behaves in situations such as when it is already recivering from a fault.|Normal operation, startup, shutdown, repair mode, degraded operation, overloaded operation|
|Response|The most commonly desired response is to prevent the fault from becoming a failure, but other responses may also be important, such as notifying people or logging the fault for later analysis. This section specifies the desired system response|Prevent the fault from becoming a failure.<br>Detect the fault:<br>- Log the fault<br>- Notify the appropriate entities (people or systems)<br>- Recover from the fault<br>- Disable the source of events causing the fault<br>- Be temporarily unavailable while a repair is being effected<br>- Fix or mask the fault/failure or contain the damage it caused<br>- Operate in a degraded mode while a repair is being effected|
|Response measure|We may focus on a number of measures of availability, depending on the criticality of the service being provided|- Time or time interval when the system must be available<br>- Availability percentage (e.g., 99.999 percent)<br>- Time to detect the fault<br>- Time to repair the fault<br>- Time or time interval in which the system can be in degraded mode<br>- Proportion (e.g., 99 percent) or rate (e.g., up to 100 per second) of a certain class of faults that the system prevents, or handles without failing|

![[sample_concrete_availability_scenario.png]]

# Tactics for Availablity
Goal of availablity tactics
![[goal_of_availability_tactics.png]]

The tactics have one of three purposes:
1. Fault detection
2. Fault recovery
3. Fault prevention

![[availablity_tactics.png]]

---

# Patterns for availability
## Active redundancy (hot spare)
Active redundancy is when you have an active system and a redundant system running in parallel. The way the redundant system works is, that there is a group of processing nodes, called the [[Protection Group|protection group]], where one or more nodes are active, and the remainder of nodes are called the redundant spares. The redundant spares processes the same input as the active nodes, to remain in a identical state.
Should there be a failure in on of the active nodes, the spare nodes can quickly take its place to ensure proper availability.

One active node and one redundant node is often referred to as "one-plus-one redundancy".

## Passive redundancy (warm spare)
Assuming a stateful system, then this is almost the same as "Active redundancy".

This differs in only one place, and that is that only the active nodes process data. They then periodically send the updated state to the spare nodes.

This balances out how compute-intensive the system is, i.e., cheaper, but also poses the risk of potential loss of data, and lower availability.

## Spare (cold spare)
In this configuration, the spare nodes receive no updates regarding the state.
Should a failure occur within an active node, a "cold spare"-node is spun up on a [[Power-on-reset Procedure|power-on-reset procedure]].
This is a slow procedure, so this lowers the availability, and is therefore not suited for most projects with an availability requirement.

## Benefits/Tradeoffs
### Benefits
The more "redundant" nodes there are, the shorter periods of downtime there is.

### Tradeoffs
The primary tradeoff with these patterns are the additional cost of operation. If you have hot spares throughout the system, you practically have multiple identical systems running in order to serve one.

Furthermore, the additional complexity added as the system has to be setup to support the provision of spares.