# DAWA Trial Website

Source code for the **DAWA** (Digital Antibiotic stewardship and Training for Wahudumu wa Afya) trial website.

- **Sponsor:** Centre for Primary Care and Public Health (Unisanté), University of Lausanne, Switzerland
- **Partners:** Ifakara Health Institute (IHI), Tanzania; Zanzibar Ministry of Health
- **Funding:** Swiss National Science Foundation (SNSF) — PZ00P3\_216330; Cadot Prize, University of Lausanne

---

## Repository Structure

```
DAWA_website/
│
├── en/                        # English version (Quarto project)
│   ├── _quarto.yml            # Site configuration: navbar, theme, output path
│   ├── index.qmd              # Home page
│   ├── Background.qmd         # AMR background and rationale
│   ├── Design.qmd             # Study design (DAWA I–III)
│   ├── Intervention.qmd       # ZanEMR-AS and Antibiotic Stewardship Club
│   ├── Protocol.qmd           # Protocol versions and ethics history
│   ├── Publications.qmd       # Publications list
│   ├── Principal.qmd          # Team page
│   ├── Funding.qmd            # Partners and funding
│   ├── news.qmd               # News and updates
│   └── images/                # Images used by English pages
│
├── sw/                        # Swahili version (Kiswahili) — mirrors en/
│   ├── _quarto.yml            # Same structure as en/_quarto.yml, Swahili labels
│   ├── index.qmd
│   ├── Background.qmd
│   ├── Design.qmd
│   ├── Intervention.qmd
│   ├── Protocol.qmd
│   ├── Publications.qmd
│   ├── Principal.qmd
│   ├── Funding.qmd
│   ├── news.qmd
│   └── images/
│
├── docs/                      # Compiled output — served by GitHub Pages
│   ├── index.html             # Root redirect to en/index.html
│   ├── en/                    # Rendered English site
│   └── sw/                    # Rendered Swahili site
│
├── styles.css                 # Shared SCSS/CSS theme (Quarto custom styles)
├── DAWA_website.Rproj         # RStudio project file
└── README.md
```

**Key principle:** `en/` and `sw/` are two independent Quarto website projects. Every page that exists in `en/` must have a matching page in `sw/`, and vice versa — the language switcher in the navbar links between corresponding pages by file name.

---

## How to Render

You need [Quarto](https://quarto.org/docs/get-started/) installed. Render each language version separately from the repo root:

```bash
# English
quarto render en/

# Swahili
quarto render sw/
```

Output is written to `docs/en/` and `docs/sw/` respectively, as configured in each `_quarto.yml`. After rendering both, `docs/` is ready to be served by GitHub Pages.

To preview a single language locally (with live reload):

```bash
quarto preview en/
# or
quarto preview sw/
```

### Adding a new page

1. Create `en/NewPage.qmd` with your content.
2. Create the matching `sw/NewPage.qmd` with the Swahili translation.
3. Add an entry for `NewPage.qmd` to the `navbar` section in both `en/_quarto.yml` and `sw/_quarto.yml`.
4. Re-render both projects.

---

## PS

1. **ClinicalTrials.gov link:** Once registered, add the registry URL to the right-hand side of the navbar in both `_quarto.yml` files:
   ```yaml
   right:
     - icon: folder
       text: Registry
       href: https://clinicaltrials.gov/study/NCTXXXXXXXX
   ```

---

## Acknowledgements

This repository is adapted from the website of the **RETUNE trial** — *"Offer of a menu of different nicotine substitute products to REduce Tobacco Use iN pEople living with HIV"* — a pragmatic randomized trial within the Swiss HIV Cohort Study.

The RETUNE website was designed and built by **[Christof Schönenberger](https://github.com/christofmanuel)** (University Hospital Basel), whose clean Quarto structure, multilingual setup, and thoughtful design provided the direct foundation for this site. Kudos to Christof for making his work openly available and for the inspiration!