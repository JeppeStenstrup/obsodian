[[Quality Attribute MOC]]

![[Integration is a basic law of life; when we resist it, disintegration is the natural result#^quote]]

# Integrability

It is important to consider integration, when developing software.
If multiple developers are developing multiple components, it is crucial to consider the possible integration to each other, and the system in general.

A general abstract representation of the integration problem is:

A unit of software $C$, or a set of unit $\{C_1, C_2, \dots, C_n\}$, needs to be integrated into a system $S$.

$S$ might be a platform where we need to integrate $\{C_i\}$, or it could be an existing platform that already contains $\{C_1, C_2, \dots, C_n\}$, where we need to analyze the costs and technical risk for integrating $\{C_{n+1}, \dots, C_m\}$.

We assume that we have control over $S$, but the $\{C_i\}$ may be outside our control, provided by a third party for example. So our level of understanding of $\{C_i\}$ can vary, but the clearer we understand it, the more capable the design will be, and the more accurate the analysis will be.

As $S$ evolves, which it will do, integrability gets harder and harder to predict. Therefore, we need to develop our software by planning for the future.

Example: 
To plug a North American plug (an example of a $\{C_i\}$) into a North American socket (an interface provided by the electrical system $S$), the “integration” is trivial. However, integrating a North American plug into a British socket will require an adapter. And the device with the North American plug may only run on 110-volt power, requiring further adaptation before it will work in a British 220-volt socket. Furthermore, if the component was designed to run at 60 Hz and the system provides 70 Hz, the component may not operate as intended even though it plugs in just  The architectural decisions made by the creators of $S$ and $\{C_i\}$ - for example, to provide plug adapters or voltage adapters, or to make the component operate identically at different frequencies - will a the cost and risk of the integration.

---

# Integrability General Scenario
|Portion of Scenario|Description|Possible Values|
|-------------------|-----------|---------------|
|Source|Where does the stimulus come from?|One or more of the following:<br>- Mission/system stakeholder<br>- Component marketplace<br>- Component vendor|
|Stimulus|What is the stimulus? That is, what kind of integration is being described?|One of the following:<br>- Add new component<br>- Integrate new version of existing component<br>- Integrate existing components together in a new way|
|Artifact|What part of the system are involved in the integration?|One of the following:<br>- Entire system<br>- Specific set of components<br>- Component metadata<br>- Component configuration|
|Environment|What state is the system in when the stimulus occurs?|One of the following:<br>- Development<br>- Integration<br>- Deployment<br>- Runtime|
|Response|How will an "integrable" system respond to the stimulus?|One or more of the following:<br>- Changes are {completed, integrated, tested, deployed}<br>- Components in the new configuration are successfully and correctly (syntactically and semantically) exchanged information<br>- Components in the new configuration are successfully collaborating<br>- Components in the new configuration do not violate any resource limits|
|Response measure|How is the response measured?|One or more of the following:<br>Cost, in terms of on or more of:<br>- Number of components changed<br>- Percentage of code changed<br>- Lines of code changed<br>- Effort<br>- Money<br>- Calendar time<br>Effects on other quality attribute responses measures (to capture allowable tradeoffs)|
![[sample_integration_scenario.png]]

---

# Tactics for Integrability
Goal of integrability tactics
![[goal_of_integration_tactics.png]]

![[integrability_tactics.png]]

---

# Limit dependencies
## Encapsulate
Encapsulation is pretty much just the whole concept behind interfaces.
All communication to a component needs to be done through an interface, which means that all dependencies are eliminated.

This enables the ability to swap out components behind the interface, as long as it complies with the given interface. As for the components implementing the component through the interface, nothing has changed, as the methods, etc., consists.

This as a whole reduces the distance, data, syntactically, semantically, between $C$ and $S$.

## Use intermediaries
Intermediaries, such as [[Publish-subscribe|pubsub]] can be used to complete remove the dependencies between components.

## Abstract Common Services
Like we did when making the game on the 4th semester.
We take, for example, Shotgun and Rifle, which are not the same, but similar enough to categorize them together. This usually makes it possible to extract common attributes and methods, to create a common interface, which streamlines and enhances the system as a whole.

# Patterns for Integrability
- _Wrappers_: Service
- _Bridges_: Transients like C#-mappers
- _Mediators_: C# MediatR

## Benefits
- All three patterns allow access to an element without forcing a change to the element or its interface.

## Tradeoffs
- Creating any of the patterns requires up-front development work.
- All of the patterns will introduce some performance overhead while accessing the element, although typically this overhead is small.

![[Service-Oriented Architecture Pattern]]

![[Dynamic Discover]]