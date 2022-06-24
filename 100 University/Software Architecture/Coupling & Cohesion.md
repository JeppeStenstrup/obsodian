[[Concepts MOC]]

# Coupling & Cohesion

It's pretty obvious that a change that affects one module is easier and less expensive than a change that affects multiple modules.

## Coupling
If multiple modules' responsibility overlaps, a change to one of them is likely to affect them both.

We can quantify this overlap by measuring the probability that a modification to one module will propagate to the other. This relationship is called **coupling**, and high coupling is an enemy of modification.

## Cohesion
If a module contains more than one responsibility, the likelihood of change to a responsibility to spread out and affect more than just that responsibility are high.

As we've from the famous Jan Corfixen multiple times: "Avoid creating a **God Class**"