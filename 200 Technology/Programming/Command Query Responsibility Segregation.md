---
aliases: CQRS
---
[[C Sharp]]

# Command Query Responsibility Segregation

CQRS is, at its core, a very simple pattern. It says that we should separate the implementation of commands (writes) from the queries (reads) in our system.

With CQRS we go from this:
![[CQRS_1.webp]]

To this:
![[CQRS_2.webp]]