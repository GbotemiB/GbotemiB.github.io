# Academic Personal Website Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build, configure, and prepare for deployment a full academic hub and personal portfolio website for Emmanuel Bolarinwa using the `al-folio` Jekyll framework on GitHub Pages.

**Architecture:** A static academic site built on Jekyll and `al-folio`, driven by central YAML configuration (`_config.yml`), automated BibTeX citation parsing (`_bibliography/papers.bib`), dual web/PDF CV management (`_data/cv.yml` and `assets/pdf/cv.pdf`), and automated CI/CD deployment via GitHub Actions (`.github/workflows/deploy.yml`).

**Tech Stack:** Jekyll, Ruby, Liquid templating, `jekyll-scholar`, BibTeX, Bootstrap/Sass, KaTeX/MathJax, GitHub Actions, GitHub Pages.

## Global Constraints

- **User Rules:** NEVER run `git push` or auto-commit. Stage only (`git add`) and output suggested commit messages for the user.
- **Permissions:** Confirm with the user before making code changes; the user must authorize execution.
- **Structure:** Follow `al-folio` canonical directory layout strictly to ensure compatibility with GitHub Actions.
- **Assets:** Download Emmanuel's profile photo from `https://lynguallabs.org/images/emmanuel.jpg` to `assets/img/prof_pic.jpg`.

---

### Task 1: Repository Initialization & al-folio Scaffolding

**Files:**
- Create/Initialize: `.git`, `.gitignore`, `Gemfile`, `Gemfile.lock`, `_layouts/`, `_includes/`, `_sass/`, `assets/`
- Test: Directory presence and `.gitignore` integrity

**Interfaces:**
- Consumes: None
- Produces: Base directory tree and build configuration for Jekyll and `al-folio`

- [ ] **Step 1: Initialize git repository and configure .gitignore**
  Initialize git if not already present and ensure `.gitignore` excludes `_site/`, `.jekyll-cache/`, `.sass-cache/`, and `.superpowers/`.
- [ ] **Step 2: Scaffold core al-folio template layout and assets**
  Set up the necessary layout templates (`default.html`, `page.html`, `post.html`, `bib.html`, `cv.html`), includes (header, footer, nav, social icons, scripts), and SCSS stylesheets.
- [ ] **Step 3: Create Gemfile with Jekyll and jekyll-scholar dependencies**
  Configure `Gemfile` specifying `github-pages`, `jekyll`, `jekyll-scholar`, and `webrick`.
- [ ] **Step 4: Verify scaffolding integrity**
  Confirm required directories (`_layouts`, `_includes`, `_sass`, `_bibliography`, `_data`, `_pages`, `_news`, `_projects`, `assets`) exist and files are properly formatted.
- [ ] **Step 5: Stage changes**
  Stage created files with `git add` and suggest commit message: `chore: scaffold al-folio template structure`.

---

### Task 2: Global Configuration & Profile Assets

**Files:**
- Create/Modify: `_config.yml`
- Asset: `assets/img/prof_pic.jpg`
- Test: YAML syntax validation

**Interfaces:**
- Consumes: Emmanuel's resume details and photo URL
- Produces: Site-wide metadata, author links, navigation menu, and profile image

- [ ] **Step 1: Download and store profile photo**
  Download `https://lynguallabs.org/images/emmanuel.jpg` to `assets/img/prof_pic.jpg` and verify file dimensions and validity.
- [ ] **Step 2: Configure `_config.yml` with Emmanuel's details**
  Populate:
  - `title: Emmanuel Bolarinwa`
  - `first_name: Emmanuel`, `last_name: Bolarinwa`
  - `email: gbotemibolarinwa@gmail.com`
  - `description: M.S. Engineering AI Student at CMU Africa | AI Researcher & Energy Systems Modeler`
  - `github_username: gbotemiB`
  - `linkedin_username: emmanuel-bolarinwa`
  - `scholar_userid: Emmanuel Bolarinwa`
  - Enable plugins: `jekyll-scholar`, `jekyll-sitemap`, `jekyll-feed`
- [ ] **Step 3: Validate `_config.yml` syntax**
  Verify YAML structure using a python/ruby YAML parser to ensure no syntax errors.
- [ ] **Step 4: Stage changes**
  Run `git add _config.yml assets/img/prof_pic.jpg` and suggest commit message: `feat: configure personal profile metadata and avatar`.

---

### Task 3: Landing Page & Announcements Feed

**Files:**
- Create: `_pages/about.md`
- Create: `_news/announcement_1.md`, `_news/announcement_2.md`, `_news/announcement_3.md`
- Test: Frontmatter validation and markdown rendering check

**Interfaces:**
- Consumes: `_config.yml` settings, news snippets, and resume summary
- Produces: Homepage `/` with bio hero, news widget, and selected publications block

- [ ] **Step 1: Write `_pages/about.md`**
  Craft the landing page with frontmatter (`layout: about`, `title: about`, `permalink: /`, `subtitle: Master of Science in Engineering AI | CMU Africa`, `profile: { align: right, image: prof_pic.jpg }`). Include narrative bio describing low-resource speech recognition (Yoruba-English) and open-source energy system modeling (PyPSA-Earth).
- [ ] **Step 2: Add news items in `_news/`**
  - `_news/2025-09-01-indaba-award.md`: Paper Award at Deep Learning Indaba 2025 (Top 1% of submissions).
  - `_news/2025-05-15-naacl-paper.md`: Acceptance of Yoruba-English code-switching ASR paper at CALCS @ NAACL 2025.
  - `_news/2024-11-20-ich-lecture.md`: Youngest invited lecturer at International Centre for Hydropower (ICH) Workshop in Nairobi, Kenya.
- [ ] **Step 3: Verify markdown frontmatter**
  Check that dates and permalinks are consistent and sorted chronologically.
- [ ] **Step 4: Stage changes**
  Run `git add _pages/about.md _news/` and suggest commit message: `feat: add about page and news announcements`.

---

### Task 4: Automated Bibliography & Publications

**Files:**
- Create: `_bibliography/papers.bib`
- Create: `_pages/publications.md`
- Test: BibTeX syntax parsing

**Interfaces:**
- Consumes: 4 peer-reviewed papers from Emmanuel's CV
- Produces: Dynamic `/publications/` page with badges, filters, and BibTeX popups

- [ ] **Step 1: Create `_bibliography/papers.bib`**
  Encode the 4 publications in standard BibTeX format with extra `al-folio` tags:
  1. `bolarinwa2025closing` (Deep Learning Indaba / PMLR) with `award={Paper Award, Top 1%}`, `abbr={PMLR}`.
  2. `babatunde2025beyond` (CALCS @ NAACL 2025) with `abbr={NAACL/CALCS}`.
  3. `babatunde2025challenging` (AfricaNLP @ ACL 2025) with `abbr={ACL AfricaNLP}`.
  4. `aina2024lowcost` (IJIRR 2024) with `abbr={IJIRR}`.
- [ ] **Step 2: Create `_pages/publications.md`**
  Configure frontmatter (`layout: page`, `permalink: /publications/`, `title: publications`, `nav: true`, `nav_order: 1`). Include search bar and year-based grouping.
- [ ] **Step 3: Validate BibTeX syntax**
  Run Python `bibtexparser` (or regex test) to confirm zero syntax errors and valid keys.
- [ ] **Step 4: Stage changes**
  Run `git add _bibliography/papers.bib _pages/publications.md` and suggest commit message: `feat: add automated BibTeX publications database and page`.

---

### Task 5: Dual CV Page & Data Setup

**Files:**
- Create: `_data/cv.yml`
- Create: `_pages/cv.md`
- Create/Place: `assets/pdf/cv.pdf`
- Test: YAML data validation and PDF presence

**Interfaces:**
- Consumes: Emmanuel's full resume sections (Education, Experience, Teaching, Awards, Skills)
- Produces: Responsive web CV and PDF download/embed on `/cv/`

- [ ] **Step 1: Create `_data/cv.yml`**
  Populate structured sections:
  - Education (Carnegie Mellon University Africa, Obafemi Awolowo University)
  - Research Experience (Lyngual Labs, Microelectronics Research Group, PMCRG)
  - Work & Open Source Experience (Open Energy Transition, Hamoye, Zuri)
  - Teaching Experience (Lyngual Labs Academy, ICH Kenya, IJAN Africa, OAU)
  - Awards & Honors (DL Indaba 2025 Paper Award, ICH youngest lecturer)
  - Skills (Languages, Machine Learning, Energy & Geospatial, Cloud & Data Engineering)
- [ ] **Step 2: Create `_pages/cv.md` supporting dual view**
  Add frontmatter (`layout: cv`, `permalink: /cv/`, `title: cv`, `nav: true`, `nav_order: 2`, `cv_pdf: cv.pdf`).
  Add top download action button linking to `/assets/pdf/cv.pdf`, web timeline sections, and embedded PDF viewer toggle.
- [ ] **Step 3: Place PDF in `assets/pdf/cv.pdf`**
  Create directory `assets/pdf/` and place the initial CV document.
- [ ] **Step 4: Verify CV YAML and links**
  Validate that `cv.yml` parses cleanly and links between web and PDF work properly.
- [ ] **Step 5: Stage changes**
  Run `git add _data/cv.yml _pages/cv.md assets/pdf/` and suggest commit message: `feat: implement dual web and PDF curriculum vitae page`.

---

### Task 6: Projects Showcase & Talks Pages

**Files:**
- Create: `_projects/afrilearner360.md`, `_projects/yoruba_corpus.md`, `_projects/pypsa_earth.md`, `_projects/gh_archive.md`
- Create: `_pages/projects.md`
- Create: `_pages/talks.md`
- Test: Project card metadata and links verification

**Interfaces:**
- Consumes: Project details from resume (AfriLearner360, Yoruba speech corpus, PyPSA-Earth, GH Archive)
- Produces: `/projects/` showcase and `/talks/` lectures archive

- [ ] **Step 1: Create individual project files in `_projects/`**
  Write detailed cards with tags, descriptions, GitHub links, and categories.
- [ ] **Step 2: Create `_pages/projects.md`**
  Add projects index page with category filtering (`research`, `open-source`, `data-engineering`).
- [ ] **Step 3: Create `_pages/talks.md`**
  Detail invited talks: ICH Kenya (uncertainty modeling with Monte Carlo), OSCA (PyPSA-Earth & OSM), and Lyngual Labs Academy.
- [ ] **Step 4: Stage changes**
  Run `git add _projects/ _pages/projects.md _pages/talks.md` and suggest commit message: `feat: add projects showcase and talks archive`.

---

### Task 7: GitHub Actions CI/CD Workflow & GitHub Pages Setup

**Files:**
- Create: `.github/workflows/deploy.yml`
- Test: GitHub Actions workflow schema validation

**Interfaces:**
- Consumes: Full repository codebase
- Produces: Automated build and deployment to GitHub Pages (`gh-pages` branch)

- [ ] **Step 1: Write `.github/workflows/deploy.yml`**
  Configure workflow:
  - Trigger: `push` to `main` and `workflow_dispatch`.
  - Permissions: `contents: write`, `pages: write`, `id-token: write`.
  - Steps: Checkout repository, setup Ruby with caching, install dependencies with Bundler, run `bundle exec jekyll build`, deploy to GitHub Pages.
- [ ] **Step 2: Add README.md with deployment and maintenance guide**
  Document how Emmanuel can update papers, add news, edit CV, and push to GitHub to auto-deploy.
- [ ] **Step 3: Stage changes**
  Run `git add .github/ README.md` and suggest commit message: `ci: configure automated GitHub Pages deployment workflow`.

---

### Task 8: Verification & End-to-End Validation

**Files:**
- Validate all repository files and links
- Test: Check YAML validity, BibTeX formatting, responsive assets, and print suggested git instructions

- [ ] **Step 1: Run comprehensive YAML and BibTeX syntax checks**
  Execute python validation script verifying `_config.yml`, `_data/cv.yml`, all frontmatter in `_pages/`, and `_bibliography/papers.bib`.
- [ ] **Step 2: Verify asset presence and permissions**
  Confirm `assets/img/prof_pic.jpg` is non-empty and accessible, and `assets/pdf/cv.pdf` is in place.
- [ ] **Step 3: Print user guide and git status**
  Display `git status` summary and provide the exact commands for Emmanuel to create his GitHub repo, set the remote, and push when ready.
