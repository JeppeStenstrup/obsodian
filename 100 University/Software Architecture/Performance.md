[[Quality Attribute MOC]]

![[An ounce of performance is worth pounds of promises.#^quote]]

# Performance

Operations takes time. So when building architectures, it is important to consider scenarios that can impair the performance of a system.

Computations take time on the order of thousands of nanoseconds, disk access (SSD and HDD) takes time on the order of tens of milliseconds, and network access takes time ranging from hundreds of microseconds for intercontinental messages.

Performance is often linked to [[Scaling|scalability]] as it somewhat addresses performance, but in the way of scaling and still maintaining performance.

A way to monitor the performance of a system is to log the timings of potential computation heavy tasks.

---

# Performance General Scenario

A performance scenario begins with an event arriving at the system.
This event requires time to process, and while it is being processed, other events may be processed simultaneously.

|Portion of Scenario|Description|Possible Values|
|-------------------|-----------|---------------|
|Source|||
|Stimulus|||
|Artifact|||
|Environment|||
|Response|||
|Response measure|||

---

# Concurrency


---

# Tactics for Performance


---

# Patterns for Performance
