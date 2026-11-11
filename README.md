# sling.ai.kr: website of SLING AI Inc.

The public website of SLING AI Inc. (슬링에이아이 주식회사): VPA (Vision-Predictor-Action), lightweight
AI control software for robot arms (VPA) and drones (Aero-VPA). Built with Jekyll and deployed to
GitHub Pages at <https://sling.ai.kr>.

## Pages

| URL | Source | Content |
| :--- | :--- | :--- |
| `/` | `index.md` | English home page: product, how it works, results, comparison, business model, market, traction, milestones, team, company |
| `/ko/` | `ko/index.md` | The same home page in Korean |
| `/solutions_vpa.html` | `solutions_vpa.md` | VPA for robot arms, technical details |
| `/aero_vpa.html` | `aero_vpa.md` | Aero-VPA for drones, technical details |
| `/solutions.html` | `solutions.md` | Products and the formal-verification research behind the patents |
| `/solutions_cnc.html`, `/solutions_hls.html`, `/solution_law.html` | same names | Research pages (not current product lines) |
| `/representative.html` | `representative.md` | CEO profile and publications |
| `/company.html` | `company.md` | Registration numbers, address, contact |

## Editing content

Text and numbers live in `_data/`, not in the templates:

| File | What it holds |
| :--- | :--- |
| `_data/home/en.yml` | Every sentence of the English home page |
| `_data/home/ko.yml` | Every sentence of the Korean home page (same structure as `en.yml`) |
| `_data/links.yml` | All external links: models, code, papers, patent, dissertation |
| `_data/company.yml` | Legal name, registration numbers, address, email, phone |
| `_data/vpa.yml` | Numbers and demo videos on the VPA page |
| `_data/aero.yml` | Numbers on the Aero-VPA page |

When you change a figure, change it in both `en.yml` and `ko.yml`.

To show a real drone flight image instead of the forest diagram, add `assets/media/drone_screen.png`
(2:1 frame works best); the home page picks it up automatically.

## Layout and style

* `_layouts/base.html`: page shell (head, header, footer, small scripts)
* `_layouts/home.html`: the home page, built from the sections in `_includes/home/`
* `_layouts/page.html`: inner pages (title band + text)
* `assets/css/site.css`: all styles, plain CSS (colors from the IR deck: navy `#22416C`, blue `#0055A5`, yellow `#FFD54F`)

## Local preview

```bash
bundle install
bundle exec jekyll serve
# open http://127.0.0.1:4000
```

## Deployment

Every push to `main` builds the site with `.github/workflows/pages.yml` and deploys it to GitHub
Pages. The custom domain `sling.ai.kr` is set in the repository's Settings → Pages.

## License

The deployment workflow is based on GitHub's starter workflows (MIT). The original template
license is kept in [`LICENSE`](LICENSE). Demo videos come from the
[Vision-Predictor-Action](https://github.com/ylee-sling/Vision-Predictor-Action) repository (GPL-3.0).
