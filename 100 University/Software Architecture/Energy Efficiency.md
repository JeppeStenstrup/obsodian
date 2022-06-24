[[Quality Attribute MOC]]

![[Energy is a bit like money If you have a positive balance, you can distribute it in various ways#^quote]]

# Energy Efficiency

Energy consumption is often not considered when putting together architectures. We often map our architecture in regards to [[Availability|availability]], [[Performance|performance]], [[Security|security]], etc., which up until recently because we thought of energy as being unlimited.

But in 2016, a report showed that data centers globally accounted for 3% of all energy consumption globally, where estimates are as high as 10%.

Therefore, we need to factor in energy efficiency at all times. Of course other [[Quality Attribute|QA]]s are important as to how the architecture functions, but we _need_ to at least consider the impact of consumption.

Most engineers lack knowledge of the subject entirely. It is not taught in the universities, and therefore the engineers have no concept of how to go about factoring energy efficiency in, and most importantly, monitoring it when the system goes live.

Energy efficiency is a constant tradeoff of [[Availability|availability]] and [[Performance|performance]], as larger servers, more servers, faster processors, etc., all contributes to heat output, which ultimately digs into the energy consumption. This is not an issue when running off of cloud services, but if the server is on premise, this has a huge impact. 

# Energy Efficiency General Scenarios
|Portion of Scenario|Description|Possible Values|
|-------------------|-----------|---------------|
|Source|This specifies who or what requests or initiates a request to conserve or manage energy.|End user, manager, system administrator, automated agent.|
|Stimulus|A request to conserve energy.|Total usage, maximum instantaneous usage, average usage, etc.|
|Artifacts|This specifies what is to be managed.|Specifies devices, servers, VMs, clusters, etc.|
|Environment|Energy is typically manages at runtime, but many interesting special cases exist, based on system characteristics.|Runtime, connected, battery-powered, low-battery mode, power-conservation mode.|
|Response|What actions the system takes to conserve or manage energy usage.|One or more of the following:<br>- Disable services<br>- Deallocate runtime services<br>- Change allocation of services to servers<br>- Run services at a lower consumption mode<br>- Allocate/deallocate servers<br>- Change levels of service<br>- Change scheduling|
|Response measure|The measures revolve around the amount of energy saved or consumed and the effects on other functions or quality attributes|Energy managed or saved in terms of:<br>- Maximum/average kilowatt load on the system<br>- Average/total amount of energy saved<br>- Total kilowatt hours used<br>- Time period during which the system must stay powered on<br>... While still maintaining a required level of functionality and acceptable levels of other quality attributes.|
![[sample_energy_efficiency_scenario.png]]

---

# Tactics for Energy Efficiency
Goal of energy efficiency tactics
![[goal_of_energy_efficiency_tactics.png]]

The three broad categories of resource utilization:
1. Resource monitoring
2. Resource allocation
3. Resource adaption

A "resource" is a computational device the consumes energy (_hardware resource_).

![[energy_efficiency_tactics.png]]

---

# Patterns for Energy Efficiency
## Sensor Fusion
Basically have a low-power sensor and a high-power sensor. If the low-power sensor detects some changes, that are worth accessing the high-power sensor for, it will. In that way, we don't spend unnecessary power on high-power tasks.

### Benefits
Stated above, we save a lot of energy by having a check for necessity.

### Tradeoffs
Consulting whether a high-power sensor needs to be accessed adds complexity in implementation.

## Kill Abnormal Tasks
Often found on mobile devices. A notification is sent stating that an app is using a lot of energy, and the user can decide whether or not it should be shut down. If the user does nothing, the task will be closed automatically after a certain amount of time.

### Benefits
It provides an automated "fail-safe" to ensure no wasted energy is consumed.

### Tradeoffs
The system will, it self, use energy in order to run the scans, and if no apps are using too much energy, this will, in it self, be energy wasted.

Furthermore, this system may encounter situations where an app is using a lot of power, although it is intended by the user, and then it's shut down in regards to intent. This is often seen by cloud-providing apps that are not "mainstream", where sync-features are disabled unintentionally.

## Power Monitor
The Power Monitor is implemented to shut down or limit resources based on usage. If parts of a system is not in use, it will be shut down to save resources. This is used many places, but used a lot in circuits where it can completely cut of power to certain areas of the board, ensuring that _no_ energy is run through.

### Benefits
This allows for intelligent savings of power, and can be further optimized by AI that tracks the users behavior, for example.

### Tradeoffs
Complexity in general.

It also adds a latency, if a shut off part of the system needs to be turned on again, since it needs to be started from a complete off-state.

---

# Monitor resources
_You can't manage what you can't measure._

1. _Metering_: Collect as much data, regarding energy consumption, from devices as possible, in **real time**. A data center can be measured from the power meter installed, other devices can be monitored through amp meters or watt-hour meters. For battery-operated devices, it is usually possible to gather information from the battery management system within the battery component.
2. _Static classification_: When operating from the cloud, real-time energy data is usually not accessible. We then estimate energy consumption based on general operations. This information regarding energy consumption is usually available directly from the service or manufacturer.
3. _Dynamic classification_: Like static classification, we estimate consumption based on classification, although we do it from experience and previous runs. We gather information and alter our estimations. This could be a simple table lookup, a regression model based on the knowledge gathered, or a simulation.

# Allocate resources
## Reduce usage
This is pretty self explanatory. Dim the screens light when it's dark, power off certain resources when the systems users are least likely to use the service, etc.

## Discovery
A discovery service is in place to let the client chose the best fitting service to utilize. This could be a cellphone on cellular fetching a specific service, for the service to gather a list of endpoints ranked by energy efficiency. These endpoints could be populated with visual data gathered from the [[Energy Efficiency#Monitor resources|monitored resources]].

## Schedule resources
This is a key attribute when talking [[Microservices|microservices]], as there are schedulers in place to optimally place users within certain clusters to balance out resource usage and [[Performance|performance]] and [[Availability|availability]].