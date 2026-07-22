---
title: HLS Solutions
parent: Solutions
layout: default
nav_order: 2
---

# Spatial Logic Solutions for High-Performance Hardware Synthesis
{: .fs-9 }

## The Challenge: The Non-Linear Memory Bottleneck in HLS
{: .fs-6 .fw-300 }

High-Level Synthesis (HLS) accelerates hardware development by converting high-level software code (C/C++) directly into parallel Register Transfer Level (RTL) hardware architectures, such as FPGAs. To maximize performance, HLS tools unroll loops and partition arrays across isolated physical memory banks to enable concurrent data access within a single clock cycle.  

* **Structural Memory Hazards:** When multiple concurrent operations attempt to access the same single-ported memory bank during the same clock cycle, hardware memory collisions occur.  
* **Legacy Polyhedral Limitations:** Traditional dependency solvers rely on geometric polyhedral models that require linear (affine) address calculations. When index formulas contain non-linear operations—such as modulo, division, dynamic pointer arithmetic, or symbolic register multiplication—these legacy tools break down.  
* **Artificial Performance Bottlenecks:** To remain safe, conventional tools over-approximate dependencies and conservatively serialize memory operations. This destroys parallel performance and injects costly multiplexer-driven stall logic into the synthesized hardware.  

## Our Solution: Spatial Verification via Separation Logic

Our framework resolves non-affine memory conflicts directly at the LLVM Intermediate Representation (IR) level by repurposing Separation Logic—a mathematical formalism designed for reasoning about disjoint physical resources.  

Instead of treating memory addresses as simple geometric integers, our solution models hardware memory banks as distinct spatial regions. This enables automatic detection of memory conflicts without requiring linear geometric constraints.  

```text
┌─────────────────────────────────────────────────────────┐
│              Concurrent LLVM IR Memory Accesses         │
└────────────────────────────┬────────────────────────────┘
                             │
                             ▼
┌─────────────────────────────────────────────────────────┐
│     Spatial Verification Engine (Separation Logic)      │
└──────────────┬────────────────────────────┬─────────────┘
               │                            │
   (Disjoint Memory Banks)        (Shared Memory Bank)
               │                            │
               ▼                            ▼
┌────────────────────────────┐┌───────────────────────────┐
│  SMT Solver Verification   ││  Spatial Contradiction    │
│  (Pairwise Inequalities)   ││      (P * P  =>  ┴)       │
└──────────────┬─────────────┘└─────────────┬─────────────┘
               │                            │
       (Proven Valid)               (Conflicting / Unknown)
               │                            │
               ▼                            ▼
┌────────────────────────────┐┌───────────────────────────┐
│ Maximum Parallel Synthesis ││ Safe Sequential Fallback  │
│    (Collision-Free RTL)    ││  (MUX-Driven Stall Logic) │
└────────────────────────────┘└───────────────────────────┘
```

### Key Technical Pillars

* **LLVM IR Integration:** Extracts flat 1D arithmetic address expressions directly from compiler getelementptr (GEP) instructions, bypassing complex multi-dimensional source code transformations.  
* **Conflict-Free Unrolling (CFU) Condition:** Formulates parallel basic block execution requirements using Separation Logic's separating conjunction ($*$). If two parallel operations target the same memory bank $k$, the logical expression $bank(k) * bank(k)$ triggers an automatic spatial contradiction ($P * P \Rightarrow ot$).  
* **Automated SMT Solver Translation:** Translates spatial disjointness requirements into a simple matrix of pairwise inequalities across immutable Static Single Assignment (SSA) registers. Downstream engines like Z3 automatically evaluate these conditions.  
* **Deterministic Sequential Fallback:** Handles undecidable non-linear integer arithmetic safely. If the solver returns Unknown or times out, the framework automatically falls back to sequential execution with multiplexer-driven stall logic, ensuring absolute safety.  
* **Theorem of Soundness:** Provides a rigorous mathematical proof bridging software SMT verification directly to physical Verilog RTL execution traces, ensuring synthesized hardware is immune to memory collisions.  

### Key Value & Business Benefits

| Feature | Legacy HLS Tools (Polyhedral) | Our Spatial Logic Framework |
| :--- | :--- | :--- |
| **Index Math Support** | Strictly limited to linear/affine equations | Full support for modulo, division, & non-linear terms |
| **Conflict Handling** | Conservative serialization on non-linear terms | Mathematical proof of parallel bank disjointness |
| **Hardware Efficiency** | High multiplexer & state-machine overhead | Optimized area usage & maximum clock cycle throughput |
| **Safety Guarantees** | Risk of conservative performance degradation | Mathematically proven trace safety via SMT oracle |
