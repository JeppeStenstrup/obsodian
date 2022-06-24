[[Software Architecture]]

# Architecture
## Why is architecture the focus, and not just functionality?
If we only cared about functionality, there would be no need to consider how it’s all tied together. We would just build a monolith containing everything and ship it to the customer.

But this approach is flawed, maintainability gets harder by the minute, extending to meet specific customers are difficult and time consuming, etc.

## What is architecture good for?
Structure. We can map out the whole system, and what communicates with what, without going into too much technical detail.

This allows every entity to to be built in a way that makes the most sense, without having to work side by side with every other entity in the architecture. This also makes it easier to delegate responsibilities.