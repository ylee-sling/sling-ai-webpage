---
title: "CEO profile"
heading: "Dr. Yeonseok Lee, Founder and CEO"
seo_title: "Dr. Yeonseok Lee, Founder and CEO | SLING AI"
description: >-
  Dr. Yeonseok Lee founded SLING AI Inc. in 2026. Ph.D. in Informatics from Nagoya University
  (program verification with separation logic); author of VPA and Aero-VPA.
lede: >-
  Ph.D. in Informatics from Nagoya University. Designed and built VPA and Aero-VPA, and
  specializes in proving with mathematics that programs run without errors.
---
{%- assign L = site.data.links -%}
<div class="person person--page">
  <img class="person__photo" src="{{ '/assets/images/ceo_pic_600.jpg' | relative_url }}" alt="Portrait of Dr. Yeonseok Lee" width="600" height="771">
  <div class="person__body">
    <h2 class="person__name">Dr. Yeonseok Lee (이연석, 李淵錫)</h2>
    <p class="person__role">Founder and CEO, SLING AI Inc.</p>
    <p><strong>Research areas:</strong> theory of computation, symbolic logic, separation logic, program verification, embodied AI control</p>
    <p><strong>Languages:</strong> Korean (native), English (fluent), Japanese (fluent, JLPT N1)</p>
    <p class="person__links">
      <a href="{{ L.linkedin }}">LinkedIn</a>
      <a href="#publications">Publications</a>
      <a href="mailto:{{ site.data.company.email }}">{{ site.data.company.email }}</a>
    </p>
  </div>
</div>

> “Symbolic Logic Inspires Normal and General AI. At SLING AI, we unite mathematical logic with AI models so that machines operate safely, predictably and reliably.”

## Education

| Period | Institution | Degree |
| :--- | :--- | :--- |
| 2023–2026 | Nagoya University, Graduate School of Informatics | Doctor of Informatics |
| 2021–2023 | Nagoya University, Graduate School of Informatics | Master of Informatics |
| 2015–2021 | Hanyang University, College of Engineering | B.S. in Information Systems |
| 2012–2015 | Wonju High School | Graduated |

### Doctoral dissertation

* **Title:** Theoretical Studies of Program Verification Based on Separation Logic
* **Original:** [Nagoya University Academic Repository]({{ L.thesis }})
* **Mirror:** [Zenodo, DOI 10.5281/zenodo.21979211]({{ L.thesis_mirror }})
* **Korean national registry:** search for the author 이연석 in the [NRF Foreign Doctoral Dissertation System](https://dr.nrf.re.kr/) (논문검색).

## Experience

| Period | Organization | Role |
| :--- | :--- | :--- |
| Feb 2026 – present | SLING AI Inc. | Founder and CEO |
| Apr 2025 – Dec 2025 | NTT DATA TOKAI Corporation, Nagoya, Japan | Systems engineer |
| Feb 2017 – Feb 2019 | Republic of Korea Air Force, 11th Fighter Wing | Aircraft weapons maintenance (Staff Sergeant, honorable discharge) |

## Awards

| Year | Award |
| :--- | :--- |
| 2025 | Encouragement Award in Computer Science, Information Processing Society of Japan (IPSJ) |
| 2022 | Best Presentation Award, Japan Society for Software Science and Technology (JSSST) |
| 2022 | Student Encouragement Award, Japan Society for Software Science and Technology (JSSST) |

## Publications {#publications}

### Preprints

* **2026. Aero-VPA: Few-Step Flow-Matching Control over Non-Reconstructive JEPA Latents for Agile Flight on Edge Hardware.**
  [Zenodo]({{ L.aero_paper }}), [GitHub]({{ L.aero_code }}), [Hugging Face]({{ L.aero_model }})
* **2026. Vision-Predictor-Action: Towards Efficient Embodied AI via Neuro-Symbolic JEPA Predictors.**
  [Zenodo]({{ L.vpa_paper }}), [arXiv:2610.15556]({{ L.vpa_arxiv }}), [GitHub]({{ L.vpa_code }}), [Hugging Face]({{ L.vpa_model }})
* **2026. NS-JEPA: Towards Efficient Embodied AI via Neuro-Symbolic Joint-Embedding Predictive Architecture.**
  [Zenodo]({{ L.nsjepa_paper }})
* **2026. Neuro-Symbolic AI for Korean Criminal Law: Sentencing Prediction and Document Drafting.**
  [DOI 10.48550/arXiv.2607.19740](https://doi.org/10.48550/arXiv.2607.19740)
* **2026. Separation Logic for Memory Conflict Detection in High-Level Synthesis.**
  [DOI 10.48550/arXiv.2607.07126](https://doi.org/10.48550/arXiv.2607.07126)
* **2026. Two preprints on separation-logic G-code collision verification and neuro-symbolic G-code generation.**
  [DOI 10.48550/arXiv.2605.10437](https://doi.org/10.48550/arXiv.2605.10437), [DOI 10.48550/arXiv.2605.10568](https://doi.org/10.48550/arXiv.2605.10568)

### Peer-reviewed papers

* **2025. Incorrectness separation logic with arrays and pointer arithmetic.**
  Journal of Information Processing, Vol. 33. [DOI 10.2197/ipsjjip.33.826](https://doi.org/10.2197/ipsjjip.33.826)
* **2024. Relative completeness of incorrectness separation logic.**
  APLAS 2024, Lecture Notes in Computer Science, Vol. 15194. [DOI 10.1007/978-981-97-8943-6_13](https://doi.org/10.1007/978-981-97-8943-6_13)
* **2023. Decidable entailment checking for concurrent separation logic with fractional permissions.**
  Computer Software, Vol. 40, Issue 4. [DOI 10.11309/jssst.40.4_67](https://doi.org/10.11309/jssst.40.4_67)

### Patents

* Registered Korean patent: pre-detecting machine collisions by simulation (application no. [10-2026-0033761]({{ L.patent }}))
* Several further applications filed, including VPA's core technology

<p><a class="button" href="{{ '/company.html' | relative_url }}">Company information</a></p>
