---
title: "VPA for robot arms"
heading: "VPA for robot arms"
seo_title: "VPA for robot arms | SLING AI"
description: >-
  Vision-Predictor-Action (VPA) for robot arms: a neuro-symbolic milestone planner plus a
  flow-matching motion solver that plans each chunk of arm motion in 10–14 ms. Open paper,
  code and weights.
lede: >-
  A robot-arm controller that skips word-by-word decoding: a neuro-symbolic milestone planner
  picks the next step and a flow-matching solver writes the whole motion toward it.
wide: true
crumbs:
  - { label: "Products and research", url: "/solutions.html" }
---
{%- assign L = site.data.links -%}
<div class="page-actions">
  <a class="button button--primary button--small" href="{{ L.vpa_paper }}">Paper (Zenodo)</a>
  <a class="button button--small" href="{{ L.vpa_arxiv }}">arXiv {{ site.data.vpa.paper.arxiv_id }}</a>
  <a class="button button--small" href="{{ L.vpa_code }}">Code (GitHub)</a>
  <a class="button button--small" href="{{ L.vpa_model }}">Model weights (Hugging Face)</a>
</div>

<div class="note"><p><strong>Status:</strong> {{ site.data.vpa.status }}</p></div>

{% include vpa_showcase.html %}

{% include architecture.html %}

{% include benchmarks.html %}

{% include vpa_demo.html %}

{% include business_model.html %}

## Research and intellectual property

* **Paper:** “{{ site.data.vpa.paper.title }}”, {{ site.data.vpa.paper.date }}: [Zenodo]({{ L.vpa_paper }}), [arXiv:{{ site.data.vpa.paper.arxiv_id }}]({{ L.vpa_arxiv }})
* **Earlier framework paper:** “NS-JEPA: Towards Efficient Embodied AI via Neuro-Symbolic Joint-Embedding Predictive Architecture”, September 2026: [Zenodo]({{ L.nsjepa_paper }})
* **Code:** [github.com/ylee-sling/Vision-Predictor-Action]({{ L.vpa_code }}) (GPL-3.0)
* **Weights:** [huggingface.co/ylee-sling/vpa-libero10]({{ L.vpa_model }}), one- and two-camera LIBERO-10 policies in PyTorch and safetensors formats
* **Patents:** applications filed for VPA's core technology
* **Same architecture for drones:** [Aero-VPA]({{ '/aero_vpa.html' | relative_url }})

Commercial use inside a proprietary product needs a license from SLING AI.

<p><a class="button" href="mailto:{{ site.data.company.email }}?subject=VPA%20licensing">Contact us about licensing</a></p>
