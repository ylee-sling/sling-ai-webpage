---
title: "Company"
heading: "Company information"
seo_title: "Company information | SLING AI"
description: >-
  SLING AI Inc. (슬링에이아이 주식회사), founded February 9, 2026 in Incheon, Republic of Korea.
  Registration numbers, address and contact details.
lede: >-
  SLING AI Inc. develops VPA, lightweight AI control software for robot arms and drones,
  and licenses it to the companies that build and run them.
---
{%- assign c = site.data.company -%}
{%- assign tel = c.phone | remove: " " | remove: "-" -%}

## Corporate overview

<dl class="spec">
  <dt>Company name</dt>
  <dd>{{ c.name }} ({{ c.name_ko }})</dd>
  <dt>Founder and CEO</dt>
  <dd>{{ c.ceo_en }}</dd>
  <dt>Date of incorporation</dt>
  <dd>{{ c.founded_en }}</dd>
  <dt>Business registration no. (사업자등록번호)</dt>
  <dd>{{ c.business_registration }}</dd>
  <dt>Corporate registration no. (법인등록번호)</dt>
  <dd>{{ c.corporate_registration }}</dd>
  <dt>Email</dt>
  <dd><a href="mailto:{{ c.email }}">{{ c.email }}</a></dd>
  <dt>Phone</dt>
  <dd><a href="tel:{{ tel }}">{{ c.phone }}</a></dd>
  <dt>Website</dt>
  <dd><a href="{{ c.website }}">sling.ai.kr</a></dd>
</dl>

## What we do

* **Products:** [VPA for robot arms]({{ '/solutions_vpa.html' | relative_url }}) and [Aero-VPA for drones]({{ '/aero_vpa.html' | relative_url }}), AI control software that runs on the machine's own low-power board
* **Revenue:** on-site software subscriptions after a paid proof of concept, and per-unit technology licensing for robot, drone and chip makers
* **Industry:** information and communications; professional, scientific and technical services
* **Business type:** system software development and supply; intellectual property licensing and implementation; computer systems integration

## Location

* **Address:** {{ c.address_en }}
* **Address (Korean):** {{ c.address_ko }}

SLING AI is located in {{ c.office_en }} ({{ c.office_ko }}). Please contact us by email or phone to arrange a meeting or visit.

<p><a class="button button--primary" href="mailto:{{ c.email }}?subject=SLING%20AI%20inquiry">Email {{ c.email }}</a> <a class="button" href="{{ '/' | relative_url }}">Back to home</a></p>
