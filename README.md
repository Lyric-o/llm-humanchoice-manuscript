# Distributional Few-Shot Personalization for Human-Anchored LLM Post-Training

Manuscript repository for the LLM-humanchoice project. It currently holds the **research proposal** (concise version, 2026-09-29). The repository is meant to be linked to Overleaf through GitHub.

**Idea.** Treat a probabilistic LLM judge as a *distribution-valued* black-box predictor and personalize it to humans with a few revealed labels. This extends the few-shot personalization (FSP) framework of Li & Zhang (arXiv:2601.01432) from scalar regression to conditional preference distributions. The personalized target then drives preference optimization of an open-weight policy, with a bound that carries the personalization error into the policy's excess risk.

## Overleaf

- **First link:** Overleaf → New Project → *Import from GitHub* → select this repository. Then set Menu → Settings → Compiler **pdfLaTeX**, Main document `main.tex`.
- **Day-to-day:** Overleaf Menu → *GitHub* → "Pull GitHub changes into Overleaf" or "Push Overleaf changes to GitHub".
- **Local edits:** run `git pull --rebase` before editing and push when done. Overleaf commits on your behalf when you sync from the web UI.

## Contents

| Path | Role |
|---|---|
| `main.tex` | Title, abstract, macros, section order |
| `sections/01_introduction.tex` | Problem, starting point (Li & Zhang), the three parts, related work |
| `sections/02_setup.tex` | Data, graded two-order judge protocol, summaries (p_J, t_J, o_J), target and risk |
| `sections/03_methods.tex` | Method I (D-FSP), Method II (label acquisition), Method III (FSP-PO) and the bridge proposition |
| `sections/04_theory.tex` | Assumptions and target results (upper bound, lower bound, adaptation) |
| `sections/05_experiments.tex` | E1–E5: estimation, information test, acquisition, robustness, post-training |
| `sections/06_contributions.tex` | Expected contributions |
| `references.bib` | Bibliography |

## Local build

```bash
pdflatex main && bibtex main && pdflatex main && pdflatex main
```

Build artifacts and `main.pdf` are git-ignored; Overleaf compiles its own PDF.
