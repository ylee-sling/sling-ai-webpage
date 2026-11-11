---
title: "Aero-VPA for drones"
heading: "Aero-VPA for drones"
seo_title: "Aero-VPA for drones | SLING AI"
description: >-
  Aero-VPA applies Vision-Predictor-Action to drone flight: a JEPA world model, a few-step
  flow-matching actor and a map-free safety shield, 18.13M parameters for a 15 W edge computer.
  In 180 simulated forest missions it reaches the goal in 52.2% of flights with the shield.
lede: >-
  The VPA architecture trained on flight data: the drone decides from its own camera, with no
  map, and a safety shield remembers the obstacles it has already passed.
wide: true
crumbs:
  - { label: "Products and research", url: "/solutions.html" }
---
{%- assign L = site.data.links -%}
{%- assign a = site.data.aero -%}
{%- assign t = site.data.home.en -%}
<div class="page-actions">
  <a class="button button--primary button--small" href="{{ L.aero_paper }}">Paper (Zenodo)</a>
  <a class="button button--small" href="{{ L.aero_code }}">Code (GitHub)</a>
  <a class="button button--small" href="{{ L.aero_model }}">Weights and flight videos (Hugging Face)</a>
  <a class="button button--small" href="{{ L.aero_data }}">Benchmark records</a>
</div>

<div class="note"><p><strong>Status:</strong> {{ a.status }}</p></div>

<figure class="figure">
{% include svg/forest.html alt="Top view of a forest: the drone's camera view, the path flown so far, two remembered trees and the remaining route to the goal" id="page" %}
  <figcaption>{{ t.products.items[1].caption }}</figcaption>
</figure>

## How it works

<div class="panels">
{%- for p in a.parts %}
  <div class="panel{% if forloop.last %} panel--solution{% endif %}">
    <h3>{{ forloop.index }}. {{ p.name }}</h3>
    <p>{{ p.text }}</p>
  </div>
{%- endfor %}
</div>

The world model and the actor are the same Vision-Predictor-Action design as [VPA for robot arms]({{ '/solutions_vpa.html' | relative_url }}): no language decoder in the control loop, so the cost of a decision does not grow with the length of the motion.

## Results in simulation

<dl class="spec">
{%- for m in a.metrics %}
  <dt>{{ m.label }}</dt>
  <dd><strong>{{ m.value }}</strong><small>{{ m.detail }}</small></dd>
{%- endfor %}
</dl>

<p class="figures-note">PX4 SITL with Gazebo Harmonic. The model card on <a href="{{ L.aero_model }}">Hugging Face</a> has the per-checkpoint and per-density tables, and <code>sim/paired_stats.py</code> in the <a href="{{ L.aero_code }}">code repository</a> recomputes every number from the <a href="{{ L.aero_data }}">published records</a>. These are simulation results with one training seed per recipe.</p>

## Parameter budget

| Module | Parameters | Role |
| :--- | :--- | :--- |
{% for p in a.params %}| {% if forloop.last %}**{{ p.module }}**{% else %}{{ p.module }}{% endif %} | {% if forloop.last %}**{{ p.count }}**{% else %}{{ p.count }}{% endif %} | {{ p.role }} |
{% endfor %}

{% include business_model.html %}

## Open release and licensing

* **Paper:** “{{ a.paper.title }}”, {{ a.paper.date }}: [Zenodo]({{ L.aero_paper }}) (CC BY 4.0)
* **Code:** [github.com/ylee-sling/Aero-VPA]({{ L.aero_code }}) (GPL-3.0-only)
* **Weights:** [huggingface.co/ylee-sling/aero-vpa]({{ L.aero_model }}) (GPL-3.0), six DAgger checkpoints with FPV flight videos
* **Benchmark data:** [huggingface.co/datasets/ylee-sling/aero-vpa-benchmark]({{ L.aero_data }}) (CC BY 4.0): every mission record, decision traces and the 36 test worlds

For commercial integration, proprietary licensing or defense adaptation, contact SLING AI.

<p><a class="button" href="mailto:{{ site.data.company.email }}?subject=Aero-VPA%20licensing">Contact us about licensing</a></p>
