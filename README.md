# Forge professional learning

Two certificated, self-paced courses for teachers. Twelve hours in total, portfolio-assessed, with no examination and no lesson observation.

**Live site:** https://asilivirtualschool-max.github.io/forge-courses/

| Course | Hours | What it covers |
|---|---|---|
| **Teaching at the Threshold** | 6 | Troublesome knowledge, liminality, skill levels, and teaching across the threshold |
| **AI for Teaching Practice** | 6 | What AI is good at, adapting what works, reading the evidence, researching your own practice |

Take Course 1 first. Course 2 assumes you can already name a threshold concept and the misconception under it, because those are what you adapt for and diagnose against.

## How it works

Each course is a single page with six panels — an introduction, four modules, and a portfolio workspace.

- **Progress and answers save to the browser.** There is no account, no server, and nothing is uploaded anywhere. `localStorage` only.
- **Self-test questions give feedback on wrong answers**, not just the right one. Open questions have a model answer you can reveal.
- **The portfolio workspace** collects the three assessed pieces per course and exports them as a plain text file you can send to whoever is certifying.
- **Print or save as PDF** expands every panel, so the whole course prints as a readable document.

## Structure

```
index.html                        landing page
programme.html                    how the two courses fit a teaching term
teaching-at-the-threshold.html    course 1
ai-for-teaching-practice.html     course 2
assets/site.css                   shared site styling
.nojekyll                         serve files as-is, no Jekyll processing
```

### Embedding a course elsewhere

Each course page is a thin shell wrapped around a self-contained fragment. To embed a course in another site, copy everything inside `<main>` from the course page — it carries its own scoped styles and script. All CSS is scoped under `.tct-course` and `.aitp-course`, so neither can leak styles into the host page, and both can sit on the same page without colliding. They use separate `localStorage` keys.

## Grounding

Course 1 draws on Meyer & Land on threshold concepts and liminality, Perkins on types of troublesome knowledge, Cummins on academic language, Erickson on concept-based curriculum, and ACER's skill development frameworks.

Course 2 is mapped to the [UNESCO AI Competency Framework for Teachers (2024)](https://www.unesco.org/en/articles/ai-competency-framework-teachers) — fifteen competencies across five dimensions, at the Acquire and Deepen levels.

## Local preview

No build step. Open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 8000
```

## Publishing

GitHub Pages, from `main` at root. `.nojekyll` is present so files starting with underscores are served correctly.
