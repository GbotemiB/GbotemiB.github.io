# Academic Personal Website Design Specification

**Author:** Emmanuel Bolarinwa  
**Date:** 2026-09-18  
**Topic:** Academic & Researcher Portfolio Website  
**Framework:** `al-folio` (Jekyll) hosted on GitHub Pages via GitHub Actions  

---

## 1. Executive Summary & Goals

The objective of this project is to build, configure, and launch a personal academic hub and portfolio for **Emmanuel Bolarinwa** (Master of Science in Engineering Artificial Intelligence at Carnegie Mellon University Africa; AI Researcher at Lyngual Labs; Energy Systems Modeler at Open Energy Transition).

### Key Objectives:
- **Academic Presence:** Highlight research in speech and language technology for low-resource African languages (Yoruba-English code-switching) and open-source energy system modeling (PyPSA-Earth).
- **Automated Publications:** Manage publications through a single BibTeX file (`_bibliography/papers.bib`) that automatically formats entries, citation badges (Google Scholar, Altmetric), abstracts, and PDF links.
- **Dual CV Experience:** Provide an interactive, responsive web CV rendered from structured YAML (`_data/cv.yml`) while offering a one-click download and embedded preview of the official PDF resume (`assets/pdf/cv.pdf`).
- **Zero-Maintenance Deployment:** Automated CI/CD using GitHub Actions that builds the Jekyll site and deploys it to GitHub Pages whenever changes are pushed to GitHub.

---

## 2. Architecture & Tech Stack

- **Static Site Generator:** Jekyll with `al-folio` theme.
- **Bibliography & Citation Engine:** `jekyll-scholar` with KaTeX / MathJax support.
- **Styling & Theming:** Bootstrap with responsive mobile breakpoints and automatic Dark / Light mode toggle.
- **Hosting & CI/CD:** GitHub Pages deployed via GitHub Actions workflow (`.github/workflows/deploy.yml`).
- **Domain / URL:** Hosted on `<username>.github.io` (or a custom domain if configured later).

---

## 3. Site Structure & Navigation

The navigation bar will provide direct access to key academic sections:

```
[ Emmanuel Bolarinwa ]     About | Publications | Projects | Talks | CV | (Theme Toggle)
```

### Directory Layout
```
personal-website/
├── _config.yml               # Global configuration (name, title, affiliations, social links)
├── _bibliography/
│   └── papers.bib            # Master BibTeX database of peer-reviewed papers
├── _pages/
│   ├── about.md              # Homepage: bio, profile photo, news announcements, selected papers
│   ├── publications.md       # Full publications list grouped by year with filters and metrics
│   ├── cv.md                 # CV page with dual display (web timeline + PDF actions)
│   ├── projects.md           # Research and open-source software project showcases
│   └── talks.md              # Invited lectures, conference talks, and workshops
├── _data/
│   └── cv.yml                # Structured resume entries for web rendering
├── _news/                    # Markdown news snippets for homepage announcements
├── _projects/                # Dedicated markdown write-ups for key projects
├── assets/
│   ├── img/
│   │   └── prof_pic.jpg      # Profile photo (from https://lynguallabs.org/images/emmanuel.jpg)
│   └── pdf/
│       └── cv.pdf            # Official multi-page PDF curriculum vitae
└── .github/workflows/
    └── deploy.yml            # GitHub Actions build and deploy pipeline
```

---

## 4. Detailed Component Specifications

### 4.1 Profile & Landing Page (`about.md`, `_config.yml`)
- **Name:** Emmanuel Bolarinwa
- **Title / Role:** M.S. in Engineering Artificial Intelligence | CMU Africa
- **Affiliations:** Carnegie Mellon University Africa &bull; Lyngual Labs &bull; Open Energy Transition
- **Location:** Kigali, Rwanda / Lagos, Nigeria
- **Photo:** Saved to `assets/img/prof_pic.jpg` (downloaded from `https://lynguallabs.org/images/emmanuel.jpg`).
- **Social & Academic Links:**
  - GitHub: `gbotemiB` (`https://github.com/gbotemiB`)
  - LinkedIn: `emmanuel-bolarinwa` (`https://www.linkedin.com/in/emmanuel-bolarinwa/`)
  - Email: `gbotemibolarinwa@gmail.com`
  - Google Scholar: Emmanuel Bolarinwa
- **Homepage Sections:**
  - Main bio statement highlighting research focus on African low-resource NLP and energy modeling.
  - Latest news feed (`_news/`):
    - Deep Learning Indaba 2025 Paper Award.
    - NAACL / CALCS 2025 paper publication.
    - Youngest invited lecturer at International Centre for Hydropower (ICH), Nairobi.
  - Selected publications list (top 3 highlighted publications).

### 4.2 Publications Engine (`_bibliography/papers.bib`)
The bibliography file will be populated with 4 peer-reviewed works using `jekyll-scholar`:
1. **Closing the Gap in Low-Resource ASR: Leveraging Multilingual Models for Code-Switched Yoruba-English Speech**
   - *Venue:* Deep Learning Indaba 2025 / PMLR
   - *Authors:* Emmanuel Bolarinwa, O. Babatunde, V. Olufemi, K. Moshood, O. Williams
   - *Tags:* `abbr={PMLR}`, `bibtex_show={true}`, `award={Paper Award (Top 1%)}`
2. **Beyond Monolingual Limits: Fine-Tuning Monolingual ASR for Yoruba-English Code-Switching**
   - *Venue:* 7th Workshop on Computational Approaches to Linguistic Code-Switching (CALCS @ NAACL 2025)
   - *Authors:* O. B. Babatunde, V. T. Olufemi, E. T. Bolarinwa, K. Y. Moshood, C. C. Emezue
   - *Tags:* `abbr={NAACL/CALCS}`, `bibtex_show={true}`
3. **Challenging Multimodal LLMs with African Standardized Exams: A Document VQA Evaluation**
   - *Venue:* AfricaNLP @ ACL 2025
   - *Authors:* O. B. Babatunde, V. T. Olufemi, E. T. Bolarinwa, K. Y. Moshood
   - *Tags:* `abbr={ACL AfricaNLP}`, `bibtex_show={true}`
4. **A Low-Cost Electronic Nose Device**
   - *Venue:* International Journal of Information Research and Review (IJIRR 2024)
   - *Authors:* S. Aina, I. P. Gambo, O. A. Ogungbe, E. Bolarinwa, A. I. Oluwaranti
   - *Tags:* `abbr={IJIRR}`, `bibtex_show={true}`

### 4.3 Dual CV Page (`_pages/cv.md`, `_data/cv.yml`, `assets/pdf/cv.pdf`)
As requested, the CV page implements a dual experience:
- **Header Action:** Clear, styled `[ Download Official CV (PDF) ]` button linking to `/assets/pdf/cv.pdf`.
- **Primary View (Web CV):** Responsive timeline sections populated in `_data/cv.yml`:
  - Education (Carnegie Mellon University Africa, Obafemi Awolowo University).
  - Research Experience (Lyngual Labs, Microelectronics Research Group, PMCRG).
  - Open Source & Industry Experience (Open Energy Transition, Hamoye, Zuri).
  - Teaching Experience (Lyngual Labs Academy, ICH Kenya, IJAN Africa, OAU).
  - Honors & Awards (Deep Learning Indaba Paper Award, ICH youngest lecturer recognition).
  - Skills & Competencies (Python, PyTorch, PyPSA, GCP, Terraform, MLflow, etc.).
- **Alternative View (PDF Embed):** Embedded viewer toggle/container allowing visitors to view the formatted multi-page PDF directly within the browser window.

### 4.4 Projects Showcase (`_projects/`)
Dedicated project cards with screenshots, tech tags, and links:
1. **AfriLearner360:** Adaptive learning intelligence and culture-adapted curriculum generation for African primary education.
2. **Yoruba-English Code-Switching Speech Corpus:** 100-hour curated speech dataset across 10+ domains for low-resource ASR.
3. **PyPSA-Earth Modeling:** Concentrated solar power with thermal storage and Monte Carlo uncertainty quantification for national energy planning.
4. **GitHub Archive Data Pipeline:** Batch GCP analytics pipeline using Terraform, Prefect, PySpark, and dbt.

### 4.5 Talks & Teaching (`_pages/talks.md`)
- **ICH Workshop (Nairobi, Kenya):** *Modeling the Effects of Uncertainties in Energy Systems Using Monte Carlo Simulations* (Youngest invited lecturer).
- **Open Source Conference Africa (OSCA):** *Transparent Energy Planning with PyPSA-Earth and OpenStreetMap*.
- **Lyngual Labs Academy:** Live lectures on machine learning, feature engineering, and MLflow.

---

## 5. Deployment & CI/CD Specification

- **GitHub Actions Workflow (`.github/workflows/deploy.yml`):**
  - Triggers on `push` to branch `main`.
  - Sets up Ruby and Bundler.
  - Caches Ruby gems and dependencies for rapid builds (< 2 minutes).
  - Executes `bundle exec jekyll build`.
  - Deploys static output artifacts to the `gh-pages` branch or GitHub Pages environment.
- **Repository Setup:**
  - Branch protection on `main`.
  - GitHub Pages configured to serve from GitHub Actions workflow.

---

## 6. Verification & Quality Assurance Plan

1. **Jekyll Configuration & Lint:** Validate that `_config.yml` passes YAML linting and all site URLs / baseurls are set properly.
2. **BibTeX Verification:** Verify that `_bibliography/papers.bib` compiles without parse errors and correctly renders authors, abstracts, and DOIs.
3. **Image & Asset Integrity:** Ensure `prof_pic.jpg` downloads cleanly and displays at high resolution across desktop and retina mobile viewports.
4. **Responsive & Theming Check:** Test dark mode and light mode contrast across all pages (About, CV, Publications, Projects).
5. **PDF Link Verification:** Confirm that `cv.pdf` is accessible at `/assets/pdf/cv.pdf` and opens cleanly in new tabs.
