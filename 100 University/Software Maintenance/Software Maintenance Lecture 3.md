[[Software Maintenance Lecture MOC]]

# Lecture 3

## Concept Location
- Concepts location finds code snippets where a change is to be made
- [[Change request|Change requests]] are most often formulated in terms of domain concepts

## Partial Code comprehension
Large programs cannot be completely comprehended
- Minimum essential understanding
- Use an as-needed strategy
- Understand how certain specific concepts are reflected in the code

Just like when you visit big cities as a tourist: You find a way through the city to see all that you want, but don't have the complete knowledge of the quickest and cheapest way around.

## Concept Triangle
![[Pasted image 20220920082341.png]]
![[Pasted image 20220920082403.png]]
![[Pasted image 20220920082741.png]]

## Methodologies
- Human knowledge
- Traceability
- Dynamic search (execution traces)
- Static search
	- Dependency search
	- Pattern matching
	- Information retrieval techniques

## GREP Search Technique
GREP is an acronym for "Global Regular Expression Print".
It prints out the lines that contain a match for a regular expression, formulated by the programmer. The output will be investigated by the programmer.
```cs:Example
sudo netstat -plten | grep node
```

## Dependency Search Technique
[[CDG|Uses Class Dependency Graphs]]
- Extracted from the existing code

Local Functionality
- Consists of concepts that are actually implemented in the module and are not delegated to others

Composite functionality
- As the complete functionality of a module combined with all its supporting modules

Determined by reading code and documentation

## Dependency Search
...

## Status of components
![[Pasted image 20220920083617.png]]

### Start
![[Pasted image 20220920083633.png]]

### Classes to inspect
![[Pasted image 20220920083700.png]]

### Most likely supplier
![[Pasted image 20220920083715.png]]

### Next classes to inspect
![[Pasted image 20220920083733.png]]

### Wrong way and backtrack
![[Pasted image 20220920083758.png]]
![[Pasted image 20220920083814.png]]

### Concept location found
![[Pasted image 20220920083836.png]]

### Possible extension of the search
![[Pasted image 20220920083908.png]]
![[Pasted image 20220920083922.png]]

## Interactive Tool for Concept Location
![[Pasted image 20220920083949.png]]