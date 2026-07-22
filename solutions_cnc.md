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

### Key Features
* **Deterministic Physical Grounding**: Before any AI generation occurs, our system extracts exact, deterministic Boundary Representations (B-Rep) directly from standard 3D CAD (STEP) files using the OpenCASCADE framework.
* **CAD-Augmented Generation (RAG)**: The explicitly extracted physical ground truth is padded with mathematically rigorous safety bounds and injected into the LLM's context window via a specialized Retrieval-Augmented Generation (RAG) pipeline to prevent spatial hallucinations.
* **Generator-Verifier Architecture**: The LLM operates as an initial "Generator" to synthesize candidate toolpaths based on natural language intent, while the domain-specific Separation Logic prover acts as a deterministic "Verifier" to evaluate the neural output for spatial disjointness.
* **Automated Self-Correction**: If the prover detects a logical collision (Spatial Data Race), it condenses the conflicting voxels into a precise mathematical bounding box. This localized, deterministic error signal is automatically translated into structured natural language feedback, guiding the LLM to refine its trajectory until a formal proof of safety is achieved and the code is "correct-by-construction".
