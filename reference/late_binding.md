# [Reference](../reference.md) / Late-Binding

Late-Binding refers to a practice of leaving decisions open as long as possible — of making commitments at "the last responsible moment".

The goal is to enable you to make decisions with the freshest-possible information. The practice assumes that there is a cost (even just psychological) to _changing_ a premature decision; and it seeks to avoid that.

One example of Late-Binding in compiled programming languages is dynamic linking versus static linking: by resolving a dependency at the last possible moment, dynamic linking allows a program to benefit from the freshest-possible version of its dependency.

Another implementation of Late-Binding is **_Set-Based Concurrent Design_** where you start with a field of possibilities and chip away at it with small decisions, gradually narrowing the design space until you arrive at a solution.
