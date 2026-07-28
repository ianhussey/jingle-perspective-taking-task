# A jingle assessment of the Perspective Taking Protocol

Materials, data, and analysis code for a study of the psychometric properties of the McHugh/Barnes-Holmes Perspective Taking Protocol (PTP), assessed against established self-report and behavioural measures of perspective taking, empathy, and theory of mind. 

Hussey, I., & Elson, M. (2026). *The RFT Perspective Taking Protocol has very poor reliability and convergent validity with other measures of perspective taking, empathy, and theory of mind: A jingle assessment.* https://github.com/ianhussey/jingle-perspective-taking-task

## The question

The PTP was developed within Relational Frame Theory as a protocol to assess and train deictic relational responding in children. It has increasingly been used as a measure of individual differences in adults, which presupposes two things that had not been tested: that its scores are reliable, and that they are valid indicators of a perspective-taking trait. This study tests both, and asks whether calling it a perspective-taking measure is a jingle fallacy — the assumption that similarly named measures measure similar things.

134 adults completed a 9-item PTP (3 simple, 4 reversed, 2 double-reversed trials) online alongside a battery of comparison measures; 98 of them provided usable data at both waves, 10 days apart.

Comparison measures. Interpersonal Reactivity Index (IRI), Empathy Quotient (EQ, with Lawrence et al. subscales), Pictorial Empathy Test (PET), Single Item Trait Empathy Scale (SITES), Reading the Mind in the Eyes Test (RMET), Perspective-Taking Task for Adults (PTT-A).

## Headline results

| | PTP total | Comparison measures |
|---|---|---|
| Internal consistency (α) | .40 [.24, .54] | .68–.92 (except EQ social skills, .49) |
| Test–retest (ICC₂,₁, 10 days) | .08 [−.12, .27] | .69–.90 |
| Mean correlation with other measures | .01 [−.01, .04] | .28 [.20, .36] among themselves |

The PTP's three trial-type subscales do not cohere with one another (*r* = −.08 to .22), and disattenuating for unreliability does not recover any convergence. Full results, including Spearman robustness checks and a moderator meta-analysis, are in [`code/3_analysis.html`](code/3_analysis.html).

## Reproducing the analyses

Run the `.Rmd` files in `code/` in order; each knits to a self-contained `.html` of the same name, and `3_analysis.Rmd` writes every figure to `code/plots/` as both PNG (600 dpi) and PDF.

| File | What it does |
|---|---|
| `1_power_analysis.Rmd` | A priori precision analysis: *N* needed to estimate an ICC to within ±0.20 |
| `2_processing.Rmd` | Raw Qualtrics export → scored scales, exclusions, anonymised processed data |
| `3_analysis.Rmd` | Reliability, correlations, SD-bounds checks, meta-analysis, all figures |

Built with R 4.5.2. Packages: `correlation`, `see`, `metafor`, `psych`, `irr`, `lavaan`, `mirt`, `strait`, `ggplot2`, `patchwork`, `ggrain`, `ggstance`, `ggrepel`, `scales`, `dplyr`, `tidyr`, `stringr`, `forcats`, `purrr`, `readr`, `janitor`, `insight`, `knitr`, `kableExtra`, `ICC.Sample.Size`, `assertthat`.

[`strait`](https://github.com/ianhussey/strait) is not on CRAN: `remotes::install_github("ianhussey/strait")`.

Figures are saved at the size they appear at in the manuscript (A4 with 1 inch margins), with text and point sizes scaled to match, so they render at their final size rather than being rescaled by a word processor. Insert them at 100% scale.

## Repository contents

```
code/           analysis scripts (.Rmd) and their rendered output (.html)
  plots/        all figures, as PNG (600 dpi) and PDF
data/
  raw/          raw Qualtrics export
  processed/    scored, anonymised data used by the analyses, plus a codebook
measures/       the measures as administered
  mchughtrials/             PTP trial sets and their scoring
  qualtrics implementation/ the Qualtrics survey file (.qsf)
reports/        manuscript, preprint, and the associated Bachelor's thesis
```

`data/processed/data_processed.csv` is one row per participant per timepoint, with item-level responses, scale and subscale scores, completeness flags, and `exclude_master` (participants who failed either embedded attention check). Directly identifying information is not shared and is excluded from this repository via `.gitignore`.

## Provenance

Data collection was conducted as part of Markus Dieterich's Bachelor's thesis at the Faculty of Psychology, Ruhr University Bochum, while both authors were employed there. The thesis is in `reports/thesis/`.

## Licence

(c) Ian Hussey 2023-2026

All data and text is [CC BY 4.0](LICENSE) licensed.

All code is MIT licensed.
