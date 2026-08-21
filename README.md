# Stat 210A — Theoretical Statistics, Fall 2026

Source for the UC Berkeley Stat 210A course website, published at
<https://stat210a.berkeley.edu/fall-2026>.

Solutions, quizzes, and exams live in the companion private repository,
[`berkeley-stat210a/fall-2026-private`](https://github.com/berkeley-stat210a/fall-2026-private).
Nothing in this repository should reveal solutions to assigned work.

## Layout

| Path | Contents |
| --- | --- |
| `index.qmd` | Home page; renders the schedule from `schedule.yml` |
| `schedule.yml` | The course calendar — one entry per day, grouped by week |
| `_quarto.yml` | Site config: sidebar, URLs, analytics, render list |
| `_variables.yml` | Values behind `{{< var semester >}}`, `{{< var name >}}`, etc. |
| `reader/` | The course reader — one `.qmd` chapter per topic |
| `handwritten/` | Scanned handwritten lecture notes |
| `homework/` | Assignment PDFs, LaTeX sources, and data files |
| `recitation/` | Recitation and tutorial handouts |
| `old-exams/` | Past exams released to students |
| `assets/` | Sidebar logo, stylesheet, and the schedule EJS template |

## Editing the schedule

`schedule.yml` drives the table on the home page through
`assets/schedule.ejs`. Each entry looks like:

```yaml
- week: 3
  days:
    - date: "Sep 8"
      items:
        - type: "Lecture"
          id: "4"
          name: "Sufficiency"
          href: reader/sufficiency.qmd
          auxil:
            - id: "Handwritten notes"
              href: handwritten/lecture04-sufficiency.pdf
```

`type` must be one of `Lecture`, `Homework`, `Exam`, `Recitation`, or
`Tutorial` — each has a label colour in `assets/styles.css`. Several days
share a row automatically when they carry more than one item.

Two things to know about the numbering:

- Lecture `id` counts class meetings, but the `handwritten/lectureNN-*.pdf`
  files are numbered by topic. The two drift apart after the second
  Exponential Families lecture, so don't assume they match.
- Lecture 15 (Thu Oct 15) is a `TBD (extra lecture)` placeholder. Fall 2026
  has 28 lecture slots against Fall 2025's 27, because Veterans Day falls on
  a Wednesday and costs no class meeting.

## Building

Requires [Quarto](https://quarto.org/docs/get-started) and R (with
`rmarkdown` and `RColorBrewer`; a few reader chapters run R chunks).

```bash
quarto preview          # live preview at localhost
quarto render           # build into _site/
quarto render index.qmd # build a single page
```

`test-ons.qmd` is an Observable scratch page and is excluded from the render
list in `_quarto.yml`; it stays in the repo but is not published.

## Publishing

`.github/workflows/publish.yml` builds the site and pushes it to the
`gh-pages` branch. It is set to `workflow_dispatch` only — push-triggered
publishing is deliberately commented out, so changes go live only when the
workflow is run by hand from the Actions tab.

This site began as a fork of the Statistical Computing Facility's
[course-site-quarto](https://github.com/berkeley-scf/course-site-quarto)
template.
