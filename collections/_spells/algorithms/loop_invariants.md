---
layout: spell
date: 24-10-2024
---

An invariant is the property of being constant and unchanging.  A loop invariant formalises the description of a loop and is useful for understanding the process of an algorithm.

There are three parts ot a loop invariant:
- **Initialisation:** the condition that must hold true for the first iteration to begin.
- **Maintenance:** the condition that must be true before an iteration begins; preservation of the maintenance property is required for the loop to continue
- **Termination:** the condition that must be true for the loop to end.

I have chosen to add **Responsibility** as well into the loop invariant to outline the contribution the loop is making.

There is also the idea of the "interest", of which there is an interest index, interest location, and interest value.  There is additional preciseness required when discussing the interest because of the involvement of outer and inner loops.