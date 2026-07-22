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

### Core Technologies & Intellectual Property (IP)
Our solutions are powered by proprietary research, patent-pending architectures, and formal logic innovations:

* **Separation Logic-Based Non-Linear Memory Hazard Verification**
  * **The Tech**: Resolves non-affine hardware memory conflicts at the LLVM IR level by applying Separation Logic to reason about concurrent memory bank disjointness.
  * **Status**: Korean Patent Application Filed (Provisional Specification)
  * **Publication**: ["Separation Logic for Memory Conflict Detection in High-Level Synthesis" (Preprint DOI: 10.48550/arXiv.2607.07126)](https://doi.org/10.48550/arXiv.2607.07126)

```mermaid
flowchart TD
    A["Concurrent LLVM IR Memory Accesses"] --> B["Spatial Verification Engine<br/><i>(Separation Logic)</i>"]
    
    B -->|"Disjoint Memory Banks"| C["SMT Solver Verification<br/><i>(Pairwise Inequalities)</i>"]
    B -->|"Shared Memory Bank"| D["Spatial Contradiction<br/><i>(P ★ P ⇒ ┴)</i>"]
    
    C -->|"Proven Valid"| E["<b>Maximum Parallel Synthesis</b><br/>Collision-Free RTL"]
    D -->|"Conflicting / Unknown"| F["<b>Safe Sequential Fallback</b><br/>MUX-Driven Stall Logic"]

    %% Styling
    style A fill:#f8f9fa,stroke:#6c757d,stroke-width:1px
    style B fill:#e9ecef,stroke:#495057,stroke-width:2px
    style E fill:#d4edda,stroke:#28a745,stroke-width:2px
    style F fill:#fff3cd,stroke:#ffc107,stroke-width:2px