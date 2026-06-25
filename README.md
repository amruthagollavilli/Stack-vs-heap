#  Stack vs Heap in Java 

## Objective
This repository demonstrates how Java memory works using execution-based examples.

The goal is to understand:
- Where variables are stored (Stack vs Heap)
- How object references behave
- When objects become eligible for Garbage Collection

---

## Core Memory Model

### Stack
- Stores method call frames
- Stores local variables
- Stores references to objects (NOT objects themselves)
- Automatically cleared after method execution

### Heap
- Stores all objects created using `new`
- Shared across multiple references
- Managed by Garbage Collector

---

##  Experiments in This Repo

### 1. Local vs Instance Variable
- Local variables exist only inside method execution (stack frame)
- Instance variables exist inside the heap as part of the object

**Conclusion:** Scope affects references, not object storage.

---

### 2. Return Object vs Non-Return Object
- Returned object remains reachable outside the method
- Non-returned object becomes unreachable if no reference is stored

**Conclusion:** Object lifetime depends on reference escape.

---

### 3. Reference Overwrite Case
- When a reference is reassigned, previous object loses reference
- Unreferenced objects become eligible for GC

**Conclusion:** Java tracks references, not variable names.

---

## Important Insights

- Objects are always stored in Heap
- References are stored in Stack
- Multiple references can point to the same object
- GC only removes objects that are unreachable

---

## Summary

This project proves that Java memory management is **reference-driven**, not scope-driven.

Object lifetime depends entirely on whether it is reachable from the Stack.
