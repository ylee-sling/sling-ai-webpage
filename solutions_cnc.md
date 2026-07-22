---
title: CNC Solutions
parent: Solutions
layout: default
nav_order: 1
---

# Formal Verification of CNC Trajectories via Separation Logic
{: .fs-9 }

Traditional geometric simulations used for safety verification are computationally expensive, require repetitive testing when requirements change, and lack deterministic proofs of safety. SLING AI provides a revolutionary formal verification framework that conceptualizes the physical CNC workspace as a "Spatial Heap," treating physical occupancy as a strictly managed logical memory resource.

### Core Technologies & Intellectual Property (IP)
Our solutions are powered by proprietary research and patented architectures:

* **Separation Logic-based G-code Collision Pre-verification**
  * **The Tech**: A technology that mathematically verifies that toolpaths do not overlap with prohibited zones by applying 'Separation Logic' to G-code analysis.
  * **Status**: 
    * Korean Patent Application Filed (Feb 2026, App No. [10-2026-0033761](https://doi.org/10.8080/1020260033761); Under Examination)
    * Subsequent Korean Patent Application Filed (May 2026, App No. 10-2026-0080180; Provisional Specification)
    * Subsequent Korean Patent Application Filed (May 2026, App No. 10-2026-0088912; Provisional Specification)
  * **Publication**: [Preprint (DOI): 10.48550/arXiv.2605.10437](https://doi.org/10.48550/arXiv.2605.10437)

<div align="center" style="margin: 2rem 0; width: 100%;">
  <svg viewBox="0 0 680 320" xmlns="http://www.w3.org/2000/svg" style="width: 100%; max-width: 680px; height: auto; font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;">
    <defs>
      <marker id="arr-cnc" viewBox="0 0 10 10" refX="6" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse">
        <path d="M 0 0 L 10 5 L 0 10 z" fill="#6c757d"/>
      </marker>
    </defs>
    <rect x="190" y="10" width="300" height="42" rx="6" fill="#f8f9fa" stroke="#6c757d" stroke-width="1.5"/>
    <text x="340" y="36" text-anchor="middle" font-size="13" font-weight="600" fill="#212529">G-Code Trajectory &amp; Kinematics</text>
    <line x1="340" y1="52" x2="340" y2="80" stroke="#6c757d" stroke-width="1.5" marker-end="url(#arr-cnc)"/>
    <rect x="160" y="80" width="360" height="50" rx="6" fill="#e9ecef" stroke="#495057" stroke-width="2"/>
    <text x="340" y="101" text-anchor="middle" font-size="13" font-weight="bold" fill="#212529">Parser &amp; Discrete Spatial Set Translation</text>
    <text x="340" y="119" text-anchor="middle" font-size="11" font-style="italic" fill="#495057">(Minkowski Sum Safety Footprint Expansion)</text>
    <line x1="340" y1="130" x2="340" y2="155" stroke="#6c757d" stroke-width="1.5" marker-end="url(#arr-cnc)"/>
    <rect x="160" y="155" width="360" height="50" rx="6" fill="#e9ecef" stroke="#495057" stroke-width="2"/>
    <text x="340" y="176" text-anchor="middle" font-size="13" font-weight="bold" fill="#212529">Separation Logic Prover Engine</text>
    <text x="340" y="194" text-anchor="middle" font-size="11" font-style="italic" fill="#495057">(Spatial Heap Disjointness Evaluation)</text>
    <path d="M 250 205 L 160 245" stroke="#6c757d" stroke-width="1.5" fill="none" marker-end="url(#arr-cnc)"/>
    <path d="M 430 205 L 520 245" stroke="#6c757d" stroke-width="1.5" fill="none" marker-end="url(#arr-cnc)"/>
    <rect x="40" y="245" width="240" height="52" rx="6" fill="#d4edda" stroke="#28a745" stroke-width="2"/>
    <text x="160" y="267" text-anchor="middle" font-size="13" font-weight="bold" fill="#155724">Deterministic Spatial Safety</text>
    <text x="160" y="285" text-anchor="middle" font-size="11" fill="#155724">Collision-Free Execution</text>
    <rect x="400" y="245" width="240" height="52" rx="6" fill="#f8d7da" stroke="#dc3545" stroke-width="2"/>
    <text x="520" y="267" text-anchor="middle" font-size="13" font-weight="bold" fill="#721c24">Spatial Data Race Detected</text>
    <text x="520" y="285" text-anchor="middle" font-size="11" fill="#721c24">Pre-execution Collision Flag</text>
  </svg>
</div>

### Key Features
* **Parser-Prover Handshake**: Our architecture strictly decouples continuous machine kinematics from formal logic. A parser translates continuous tool trajectories and safety buffers into discrete spatial sets before evaluation, enabling tractable logical inference.
* **Deterministic Collision Detection**: Physical collisions are mathematically redefined as logical "Spatial Data Races". The system deterministically detects collisions prior to execution when the separating conjunction fails to establish spatial disjointness between the tool and environmental fixtures.
* **Robust Safety Margins**: To account for real-world mechanical uncertainties such as servo lag or tool deflection, we mathematically expand the tool's spatial footprint using discrete Minkowski sum operations to guarantee worst-case safety margins.
* **Multi-Axis & Multi-Tool Scalability**: By extending our framework with Concurrent Separation Logic (CSL), the system natively verifies complex collaborative environments and 5-axis Table-Table configurations. It achieves this by treating independent cutting tools and moving workpieces as concurrent, dynamically mutable spatial threads moving through an absolute coordinate system.

---

## Correct-by-Construction Neuro-Symbolic G-Code Generation
{: .fs-8 }

While Large Language Models (LLMs) offer unprecedented potential for automating code synthesis, applying them directly to cyber-physical systems introduces severe risks due to spatial hallucinations and a lack of deterministic safety guarantees. SLING AI bridges this gap with a two-way neuro-symbolic architecture that marries the creative generative capabilities of LLMs with the absolute mathematical rigor of a Separation Logic prover.

### Core Technologies & Intellectual Property (IP)
* **Neuro-Symbolic G-code Generation & Verification Architecture**
  * **The Tech**: A hybrid architecture that combines LLM-based G-code generation with our separation logic-based prover to ensure that AI-generated codes are safe.
  * **Status**: 
    * Korean Patent Application Filed (May 2026, App No. 10-2026-0083867; Provisional Specification)
    * Korean Patent Application Filed (May 2026, App No. 10-2026-0090306; Provisional Specification)
  * **Publication**: [Preprint (DOI): 10.48550/arXiv.2605.10568](https://doi.org/10.48550/arXiv.2605.10568)

<div align="center" style="margin: 2rem 0; width: 100%;">
  <svg viewBox="0 0 740 330" xmlns="http://www.w3.org/2000/svg" style="width: 100%; max-width: 740px; height: auto; font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;">
    <defs>
      <marker id="arr-ns" viewBox="0 0 10 10" refX="6" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse">
        <path d="M 0 0 L 10 5 L 0 10 z" fill="#6c757d"/>
      </marker>
      <marker id="arr-green" viewBox="0 0 10 10" refX="6" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse">
        <path d="M 0 0 L 10 5 L 0 10 z" fill="#28a745"/>
      </marker>
      <marker id="arr-red" viewBox="0 0 10 10" refX="6" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse">
        <path d="M 0 0 L 10 5 L 0 10 z" fill="#dc3545"/>
      </marker>
    </defs>
    <rect x="10" y="20" width="150" height="55" rx="6" fill="#f8f9fa" stroke="#6c757d" stroke-width="1.5"/>
    <text x="85" y="42" text-anchor="middle" font-size="12" font-weight="bold" fill="#212529">3D CAD (STEP)</text>
    <text x="85" y="58" text-anchor="middle" font-size="10" fill="#6c757d">B-Rep Extraction</text>
    <line x1="160" y1="47" x2="190" y2="47" stroke="#6c757d" stroke-width="1.5" marker-end="url(#arr-ns)"/>
    <rect x="195" y="20" width="160" height="55" rx="6" fill="#cce5ff" stroke="#004085" stroke-width="2"/>
    <text x="275" y="42" text-anchor="middle" font-size="12" font-weight="bold" fill="#004085">LLM Generator</text>
    <text x="275" y="58" text-anchor="middle" font-size="10" fill="#004085">(CAD-RAG Pipeline)</text>
    <line x1="355" y1="47" x2="385" y2="47" stroke="#6c757d" stroke-width="1.5" marker-end="url(#arr-ns)"/>
    <rect x="390" y="20" width="140" height="55" rx="6" fill="#f8f9fa" stroke="#6c757d" stroke-width="1.5"/>
    <text x="460" y="42" text-anchor="middle" font-size="12" font-weight="600" fill="#212529">Candidate G-Code</text>
    <text x="460" y="58" text-anchor="middle" font-size="10" fill="#6c757d">Synthesized Path</text>
    <line x1="530" y1="47" x2="560" y2="47" stroke="#6c757d" stroke-width="1.5" marker-end="url(#arr-ns)"/>
    <rect x="565" y="10" width="160" height="130" rx="6" fill="#e9ecef" stroke="#495057" stroke-width="2"/>
    <text x="645" y="35" text-anchor="middle" font-size="13" font-weight="bold" fill="#212529">Separation Logic</text>
    <text x="645" y="52" text-anchor="middle" font-size="13" font-weight="bold" fill="#212529">Verifier</text>
    <text x="645" y="75" text-anchor="middle" font-size="10" font-style="italic" fill="#495057">(Disjointness Check)</text>
    <line x1="645" y1="140" x2="645" y2="230" stroke="#28a745" stroke-width="2" marker-end="url(#arr-green)"/>
    <text x="655" y="190" font-size="11" font-weight="bold" fill="#28a745">Proven Safe</text>
    <path d="M 565 110 L 275 110" stroke="#dc3545" stroke-width="2" fill="none" marker-end="url(#arr-red)"/>
    <text x="380" y="102" font-size="11" font-weight="bold" fill="#dc3545">Collision Detected (Spatial Data Race)</text>
    <rect x="195" y="130" width="160" height="50" rx="6" fill="#f8d7da" stroke="#dc3545" stroke-width="1.5"/>
    <text x="275" y="152" text-anchor="middle" font-size="11" font-weight="bold" fill="#721c24">Automated Self-Correction</text>
    <text x="275" y="168" text-anchor="middle" font-size="10" fill="#721c24">Bounding Box Feedback</text>
    <line x1="275" y1="130" x2="275" y2="80" stroke="#dc3545" stroke-width="2" marker-end="url(#arr-red)"/>
    <rect x="530" y="235" width="200" height="55" rx="6" fill="#d4edda" stroke="#28a745" stroke-width="2"/>
    <text x="630" y="257" text-anchor="middle" font-size="12" font-weight="bold" fill="#155724">Correct-by-Construction</text>
    <text x="630" y="273" text-anchor="middle" font-size="11" fill="#155724">Formally Verified Code</text>
  </svg>
</div>

### Key Features
* **Deterministic Physical Grounding**: Before any AI generation occurs, our system extracts exact, deterministic Boundary Representations (B-Rep) directly from standard 3D CAD (STEP) files using the OpenCASCADE framework.
* **CAD-Augmented Generation (RAG)**: The explicitly extracted physical ground truth is padded with mathematically rigorous safety bounds and injected into the LLM's context window via a specialized Retrieval-Augmented Generation (RAG) pipeline to prevent spatial hallucinations.
* **Generator-Verifier Architecture**: The LLM operates as an initial "Generator" to synthesize candidate toolpaths based on natural language intent, while the domain-specific Separation Logic prover acts as a deterministic "Verifier" to evaluate the neural output for spatial disjointness.
* **Automated Self-Correction**: If the prover detects a logical collision (Spatial Data Race), it condenses the conflicting voxels into a precise mathematical bounding box. This localized, deterministic error signal is automatically translated into structured natural language feedback, guiding the LLM to refine its trajectory until a formal proof of safety is achieved and the code is "correct-by-construction".