---
title: Legaltech Solutions
parent: Solutions
layout: default
nav_order: 3
---

# AI Precision Meets Legal Rigor: Next-Generation Summary Proceeding Automation
{: .fs-9 }

Processing high-volume minor traffic offenses—such as simple DUIs, unlicensed driving, and minor traffic casualties—creates a heavy administrative burden for prosecutors and judicial personnel. While standard Large Language Models (LLMs) excel at reading natural language, they rely on probabilities and frequently make math errors ("hallucinations") when calculating fine ranges or enforcing strict legal rules. In criminal law, where accuracy and accountability are paramount, standard generative AI falls short.  

To solve this, our framework introduces a **Neuro-Symbolic AI Solution**. By dividing responsibilities—using LLMs solely for language understanding and a formal math engine for rule calculations—we achieve trustworthy, mathematically proven sentencing predictions and automated document drafting.  

### Core Technologies & Intellectual Property (IP)
Our solutions are powered by proprietary research, patent-pending architectures, and formal logic innovations:

* **Neuro-Symbolic Framework for Legal Reasoning & Document Synthesis**
  * **The Tech**: Combines LLMs for grounded text extraction with an SMT formal logic engine to compute deterministic fine ranges and generate verifiable prosecutorial documents.
  * **Status**: Korean Patent Application Filed (Provisional Specification)
  * **Publication**: ["Neuro-Symbolic AI for Korean Criminal Law: Sentencing Prediction and Document Drafting" (Preprint DOI: 10.48550/arXiv.2607.19740)](https://doi.org/10.48550/arXiv.2607.19740)

## How The Solution Works

Our system transforms raw legal records into verified summary indictment documents through a clear 5-step pipeline:  


<div align="center" style="margin: 2rem 0; width: 100%;">
  <svg viewBox="0 0 940 100" xmlns="http://www.w3.org/2000/svg" style="width: 100%; height: auto; font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;">
    <defs>
      <marker id="arrow-law" viewBox="0 0 10 10" refX="6" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse">
        <path d="M 0 0 L 10 5 L 0 10 z" fill="#6c757d"/>
      </marker>
    </defs>

    <!-- Node 1: Raw Docs -->
    <rect x="10" y="20" width="120" height="60" rx="6" fill="#f8f9fa" stroke="#6c757d" stroke-width="1.5"/>
    <text x="70" y="46" text-anchor="middle" font-size="12" font-weight="600" fill="#212529">📄 Raw Legal</text>
    <text x="70" y="62" text-anchor="middle" font-size="12" font-weight="600" fill="#212529">Docs</text>

    <!-- Arrow 1 -->
    <line x1="130" y1="50" x2="150" y2="50" stroke="#6c757d" stroke-width="1.5" marker-end="url(#arrow-law)"/>

    <!-- Node 2: OCR -->
    <rect x="155" y="20" width="120" height="60" rx="6" fill="#f8f9fa" stroke="#6c757d" stroke-width="1.5"/>
    <text x="215" y="46" text-anchor="middle" font-size="12" font-weight="600" fill="#212529">1. OCR &amp;</text>
    <text x="215" y="62" text-anchor="middle" font-size="12" font-weight="600" fill="#212529">Parsing</text>

    <!-- Arrow 2 -->
    <line x1="275" y1="50" x2="295" y2="50" stroke="#6c757d" stroke-width="1.5" marker-end="url(#arrow-law)"/>

    <!-- Node 3: LLM Extraction -->
    <rect x="300" y="20" width="130" height="60" rx="6" fill="#f8f9fa" stroke="#6c757d" stroke-width="1.5"/>
    <text x="365" y="46" text-anchor="middle" font-size="12" font-weight="600" fill="#212529">2. LLM Fact</text>
    <text x="365" y="62" text-anchor="middle" font-size="12" font-weight="600" fill="#212529">Extraction</text>

    <!-- Arrow 3 -->
    <line x1="430" y1="50" x2="450" y2="50" stroke="#6c757d" stroke-width="1.5" marker-end="url(#arrow-law)"/>

    <!-- Node 4: Human Verification -->
    <rect x="455" y="20" width="140" height="60" rx="6" fill="#cce5ff" stroke="#004085" stroke-width="2"/>
    <text x="525" y="44" text-anchor="middle" font-size="12" font-weight="bold" fill="#004085">3. Human Verification</text>
    <text x="525" y="60" text-anchor="middle" font-size="10" font-style="italic" fill="#004085">(Human-in-the-Loop)</text>

    <!-- Arrow 4 -->
    <line x1="595" y1="50" x2="615" y2="50" stroke="#6c757d" stroke-width="1.5" marker-end="url(#arrow-law)"/>

    <!-- Node 5: Math Logic Engine -->
    <rect x="620" y="20" width="140" height="60" rx="6" fill="#d4edda" stroke="#155724" stroke-width="2"/>
    <text x="690" y="44" text-anchor="middle" font-size="12" font-weight="bold" fill="#155724">4. Math Logic Engine</text>
    <text x="690" y="60" text-anchor="middle" font-size="10" font-style="italic" fill="#155724">(Z3 SMT Solver)</text>

    <!-- Arrow 5 -->
    <line x1="760" y1="50" x2="780" y2="50" stroke="#6c757d" stroke-width="1.5" marker-end="url(#arrow-law)"/>

    <!-- Node 6: Output -->
    <rect x="785" y="20" width="145" height="60" rx="6" fill="#e2e3e5" stroke="#383d41" stroke-width="2"/>
    <text x="857" y="44" text-anchor="middle" font-size="12" font-weight="bold" fill="#212529">5. Verified Document</text>
    <text x="857" y="60" text-anchor="middle" font-size="12" font-weight="bold" fill="#212529">&amp; Decision Tree</text>
  </svg>
</div>
