[[Quality Attribute MOC]]

# Deployability

Deployment is a process that starts with coding and end with real users interacting with the system in a production environment.

Deployability refers to a software's ability to be deployed in a predictable and acceptable amount of time. The key here is predictable.

When our deployments are predictable, we can set up rules and checks to ensure that the deployed software lives up to the systems standards. This lowers the risk of failing and slowed down software.

Issues involved in deploying software:
- How does it arrive at its host (i.e., push, where updates deployed are unbidden, or pull, where users or administrators must explicitly request updates)?
- How is it integrated into an existing system? Can this be done while the existing system is executing?
- What is the medium, such as DVD, USB drive, or Internet delivery?
- What is the packaging (e.g., executable, app, plug-in)?
- What is the resulting integration into an existing system?
- What is the efficiency of executing the process?
- What is the controllability of the process?

Architects are primarily concerned with the degree to which the architecture supports deployments that are:
- _Granular_: Deployments can be of the whole system or of elements within a system. If the architecture provides options for  granularity of deployment, then certain risks can be reduced.
- _Controllable_: The architecture should provide the capability ti deploy at varying levels of granularity, monitor the operation of the deployed units, and roll back unsuccessful deployments.
- _Efficient_: The architecture should support rapid deployment (and, if needed, rollback) with a reasonable level of effort.

---

# Deployability General Scenario

|Portion of Scenario|Description|Possible Values|
|-------------------|-----------|---------------|
|Source|The trigger for the deployment.|End user, developer, system administrator, operations personnel, component marketplace, product owner.|
|Stimulus|What causes the trigger.|A new element is available to be deployed. This is typically a request to replace a software element with a new version (e.g., fix a defect, apply a security patch, upgrade to the latest release of a component or framework, upgrade to the latest version of an internally produced element.<br>New element is approved for incorporation.<br>An existing element/set of elements needs to be rolled back.|
|Artifacts|What is to be changed.|Specific components or modules, the system's platform, its user interface, its environment, or another system with which it interoperates. Thus the artifact might be a single software element, multiple software elements, or the entire system.|
|Environment|Staging, production (or a specific subset of either).|Full deployment.<br>Subset deployment to a specific portion of: users, VMs, containers, servers, platforms.|
|Response|What should happen.|Intercorporate the new components.<br>Deploy the new components.<br>Monitor the new components.<br>Roll back a previous deployment.|
|Response measure|A measure of cost, time, or process effectiveness for a deployment, or for a series of deployments over time.|Cost in terms of:<br>- Number, size, and complexity of affected artifacts<br>- Average/worst-case effort<br>- Elapsed clock or calendar time<br>- Money (direct outlay or opportunity cost)<br>- New defects introduced<br>Extend to which this deployment/rollback affects other functions or quality attributes.<br>Number of failed deployments.|

![[sample_concrete_deployability_scenario.png]]

# Tactics for deployability
Goal of deployability tactics:
![[goal_of_deployability_tactics.png]]
These tactics are often delivered by the [[Continuous integration & Continuous deployment|CI/CD]] infrastructure. 
![[deployability_tactics.png]]

