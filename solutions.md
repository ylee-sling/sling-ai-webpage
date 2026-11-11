---
title: "Products and research"
heading: "Products and research"
seo_title: "Products and research | SLING AI"
description: >-
  SLING AI's products, VPA for robot arms and Aero-VPA for drones, and the formal-verification
  research behind the company's patents: CNC toolpath, FPGA HLS and legal-reasoning verification.
lede: >-
  What we sell today, and the formal-verification research the company grew out of.
---
{%- assign L = site.data.links -%}

## Products

Both products are the same Vision-Predictor-Action (VPA) software, trained on different data. They run on the machine's own low-power board and are released openly; companies that ship them inside their products buy a license.

### VPA for robot arms

Plans the next 16 movements of a robot arm in 10–14 ms with under 20 million parameters. In simulation (LIBERO-10, 10 household tasks), the two-camera policy succeeds in 40.0% of trials.

<p><a class="button button--small" href="{{ '/solutions_vpa.html' | relative_url }}">VPA technical details</a></p>

### Aero-VPA for drones

Flies a drone from its camera alone, with no map, and adds a safety shield that remembers obstacles for 15 s. In 180 simulated forest missions the shield raises goal reach from 21.1% to 52.2% and cuts crashes from 72% to 22%.

<p><a class="button button--small" href="{{ '/aero_vpa.html' | relative_url }}">Aero-VPA technical details</a></p>

## Research and intellectual property

SLING AI started from formal verification: proving with mathematics (separation logic and SMT solvers) that a program or a machine path cannot fail. That work produced the company's registered patent, and the same rule-based thinking runs through VPA's neuro-symbolic skill selector and Aero-VPA's deterministic safety shield. These projects are research and licensing assets, not current product lines.

| Research area | What it verifies |
| :--- | :--- |
| [CNC toolpaths]({{ '/solutions_cnc.html' | relative_url }}) | G-code toolpaths are checked for collisions with fixtures and prohibited zones before the machine moves. Registered Korean patent. |
| [FPGA high-level synthesis]({{ '/solutions_hls.html' | relative_url }}) | Non-linear memory-bank conflicts in HLS designs, detected at the LLVM IR level. Patent application filed. |
| [Legal reasoning]({{ '/solution_law.html' | relative_url }}) | Sentencing ranges and summary-indictment drafts computed by a logic engine instead of a probabilistic language model. Patent application filed. |

## Contact

Ask about a paid proof of concept, a technology license or investment: [{{ site.data.company.email }}](mailto:{{ site.data.company.email }}).
