# Distributional Few-Shot Personalization for Human-Anchored LLM Post-Training

Manuscript repository for the LLM-humanchoice project. It currently holds **research proposal draft v0.1** (2026-09-28). The repository is meant to be linked to Overleaf through GitHub.

**Idea.** Treat a probabilistic LLM judge as a *distribution-valued* black-box predictor and personalize it to humans with a few revealed labels. This extends the few-shot personalization (FSP) framework of Li & Zhang (arXiv:2601.01432) from scalar regression to conditional preference distributions. The personalized target then drives preference optimization of an open-weight policy, with a bound that carries the personalization error into the policy's excess risk.

## Overleaf

- **First link:** Overleaf → New Project → *Import from GitHub* → select this repository. Then set Menu → Settings → Compiler **pdfLaTeX**, Main document `main.tex`.
- **Day-to-day:** Overleaf Menu → *GitHub* → "Pull GitHub changes into Overleaf" or "Push Overleaf changes to GitHub".
- **Local edits:** run `git pull --rebase` before editing and push when done. Overleaf commits on your behalf when you sync from the web UI.

## Contents

| Path | Role |
|---|---|
| `main.tex` | Title, abstract, macros, theorem environments, section order |
| `sections/01_motivation.tex` | Problem, statistical template (Li & Zhang), RQ1–RQ3 |
| `sections/02_positioning.tex` | Closest prior work (table), claimed gap, claims not made |
| `sections/03_setup.tex` | Data, embeddings, link $T$, localization variable $Z$ (design decision D1) |
| `sections/04_dfsp.tex` | Method I: vector-valued local smoothing, D-FSP estimator, adaptation, two channels |
| `sections/05_theory.tex` | Risks; Prop. 1 (scalar vs distributional); Prop. 2 (judge budget); Targets A–C |
| `sections/06_acquisition.tex` | Method II: design rule from local discrepancy complexity; Target D |
| `sections/07_post_training.tex` | Method III: FSP-PO; Props. 3–4 (bridge); Target E; design decision D2 |
| `sections/08_experiments.tex` | E0–E6, arms, metrics, decision gates G1–G3 |
| `sections/09_risks.tex` | Hypothesis, risk register, contributions, titles |
| `references.bib` | Bibliography (2025–26 entries checked against arXiv on 2026-09-28) |

**Status legend in the PDF.** *Propositions/Lemmas* are proved in the draft. *Target results* are claims still to be established. Red `TODO` markers are open decisions (dataset, judge models, policy model).

## Local build

```bash
pdflatex main && bibtex main && pdflatex main && pdflatex main
```

Build artifacts and `main.pdf` are git-ignored; Overleaf compiles its own PDF.
