---
title: HLS Solutions
parent: Solutions
layout: default
nav_order: 2
---

# Spatial Logic Solutions for High-Performance Hardware Synthesis
{: .fs-9 }

## The Challenge: Non-Linear Memory Bottlenecks in HLS
{: .fs-6 .fw-300 }

High-Level Synthesis (HLS) accelerates hardware development by converting high-level software code (C/C++) directly into parallel Register Transfer Level (RTL) hardware architectures, such as FPGAs. To improve performance, HLS tools unroll loops and partition arrays across isolated physical memory banks to enable concurrent data access within a single clock cycle.  

* **Structural Memory Hazards:** When multiple concurrent operations attempt to access the same single-ported memory bank during the same clock cycle, hardware memory collisions occur.  
* **Polyhedral Analysis Limitations:** Traditional dependency solvers rely on geometric polyhedral models that require linear (affine) address calculations. When index formulas contain non-linear operations—such as modulo, division, dynamic pointer arithmetic, or symbolic register multiplication—these methods often struggle to verify memory independence.  
* **Performance Bottlenecks:** To ensure safety, conventional tools over-approximate dependencies and conservatively serialize memory operations. This can restrict parallel performance and introduce multiplexer-driven stall logic into the synthesized hardware.  

## Our Solution: Spatial Verification via Separation Logic

Our framework addresses non-affine memory conflicts at the LLVM Intermediate Representation (IR) level by applying Separation Logic—a mathematical formalism designed for reasoning about disjoint physical resources.  

Instead of treating memory addresses purely as geometric integers, our approach models hardware memory banks as distinct spatial regions. This enables memory conflict detection without relying strictly on linear geometric constraints.  

### Core Technologies & Intellectual Property (IP)
Our solutions are based on original research and patent-pending architectures:

* **Separation Logic-Based Non-Linear Memory Hazard Verification**
  * **The Tech**: Analyzes non-affine hardware memory conflicts at the LLVM IR level by applying Separation Logic to evaluate concurrent memory bank disjointness.
  * **Status**: Korean Patent Application Filed (Provisional Specification)
  * **Paper**: ["Separation Logic for Memory Conflict Detection in High-Level Synthesis" (Preprint DOI: 10.48550/arXiv.2607.07126)](https://doi.org/10.48550/arXiv.2607.07126)


<div align="center" style="margin: 2rem 0;">
  <svg viewBox="0 0 680 360" xmlns="http://www.w3.org/2000/svg" style="width: 100%; max-width: 680px; height: auto; font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;">
    <defs>
      <marker id="arr" viewBox="0 0 10 10" refX="6" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse">
        <path d="M 0 0 L 10 5 L 0 10 z" fill="#6c757d"/>
      </marker>
    </defs>

    <!-- Node 1 -->
    <rect x="190" y="10" width="300" height="42" rx="6" fill="#f8f9fa" stroke="#6c757d" stroke-width="1.5"/>
    <text x="340" y="36" text-anchor="middle" font-size="13" font-weight="600" fill="#212529">Concurrent LLVM IR Memory Accesses</text>
    <line x1="340" y1="52" x2="340" y2="80" stroke="#6c757d" stroke-width="1.5" marker-end="url(#arr)"/>

    <!-- Node 2 -->
    <rect x="160" y="80" width="360" height="50" rx="6" fill="#e9ecef" stroke="#495057" stroke-width="2"/>
    <text x="340" y="102" text-anchor="middle" font-size="14" font-weight="bold" fill="#212529">Spatial Verification Engine</text>
    <text x="340" y="120" text-anchor="middle" font-size="12" font-style="italic" fill="#495057">(Separation Logic)</text>

    <!-- Branch Arrows -->
    <path d="M 250 130 L 160 180" stroke="#6c757d" stroke-width="1.5" fill="none" marker-end="url(#arr)"/>
    <path d="M 430 130 L 520 180" stroke="#6c757d" stroke-width="1.5" fill="none" marker-end="url(#arr)"/>
    <text x="175" y="150" font-size="11" fill="#495057">Disjoint Memory Banks</text>
    <text x="435" y="150" font-size="11" fill="#495057">Shared Memory Bank</text>

    <!-- Branch Left -->
    <rect x="50" y="180" width="220" height="48" rx="6" fill="#f8f9fa" stroke="#6c757d" stroke-width="1.5"/>
    <text x="160" y="202" text-anchor="middle" font-size="12" font-weight="600" fill="#212529">SMT Solver Verification</text>
    <text x="160" y="218" text-anchor="middle" font-size="11" fill="#6c757d">(Pairwise Inequalities)</text>

    <!-- Branch Right -->
    <rect x="410" y="180" width="220" height="48" rx="6" fill="#f8f9fa" stroke="#6c757d" stroke-width="1.5"/>
    <text x="520" y="202" text-anchor="middle" font-size="12" font-weight="600" fill="#212529">Spatial Contradiction</text>
    <text x="520" y="218" text-anchor="middle" font-size="11" fill="#dc3545">(bank(k) ∗ bank(k) ⇒ ┴)</text>

    <!-- Final Arrows -->
    <line x1="160" y1="228" x2="160" y2="260" stroke="#6c757d" stroke-width="1.5" marker-end="url(#arr)"/>
    <line x1="520" y1="228" x2="520" y2="260" stroke="#6c757d" stroke-width="1.5" marker-end="url(#arr)"/>

    <!-- Final Nodes -->
    <rect x="40" y="260" width="240" height="52" rx="6" fill="#d4edda" stroke="#28a745" stroke-width="2"/>
    <text x="160" y="282" text-anchor="middle" font-size="13" font-weight="bold" fill="#155724">Optimized Parallel Synthesis</text>
    <text x="160" y="300" text-anchor="middle" font-size="11" fill="#155724">Collision-Free RTL</text>

    <rect x="400" y="260" width="240" height="52" rx="6" fill="#fff3cd" stroke="#ffc107" stroke-width="2"/>
    <text x="520" y="282" text-anchor="middle" font-size="13" font-weight="bold" fill="#856404">Safe Sequential Fallback</text>
    <text x="520" y="300" text-anchor="middle" font-size="11" fill="#856404">MUX-Driven Stall Logic</text>
  </svg>
</div>