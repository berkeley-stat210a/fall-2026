# Fall 2026 setup — outstanding items

First lecture is **Thursday, August 27**. Not published to students until you run
the publish workflow (Actions tab → Quarto Publish), which is `workflow_dispatch`
only.

This file is not part of the site: `_quarto.yml`'s render list is `**/*.qmd`, so
no `.md` file is published.

## Before the first lecture

- [ ] **Push both repos.** `fall-2026` has 5 unpushed commits, `fall-2026-private`
      has 2. The Fall 2025 content sync is already pushed; everything after it isn't.
- [ ] **Republish the site**, then confirm the eight draft reader chapters are gone
      from `gh-pages`. They went live in your earlier publish and are excluded now,
      but stale files can survive a republish:
      ```bash
      curl -sS -o /dev/null -w '%{http_code}\n' https://stat210a.berkeley.edu/fall-2026/reader/multiple-testing.html
      ```
      `404` means clear. `200` means the branch needs cleaning.

## Syllabus TBDs

| | Line | Item |
| --- | --- | --- |
| [ ] | `syllabus.qmd:10` | Your office hours location (time is set: W 3–4, Th 3:30–4:30) |
| [ ] | `syllabus.qmd:13` | Chase's office hour time **and** Zoom link |
| [ ] | `syllabus.qmd:19` | Tutorial section times and locations |
| [ ] | `syllabus.qmd:28` | Final exam review time, Friday December 11 |

**`syllabus.qmd:13` is a broken link right now.** `[Zoom](link TBD)` renders as
`<a href="link TBD">`, which 404s for anyone who clicks it. If the real link isn't
ready before you publish, make it plain text rather than leaving a live dead link.

## Tutorial sections

Everything here is blocked on picking days and times.

- [ ] **Set the days/times**, then add tutorial entries to `schedule.yml` — there
      are currently none. `.label-Tutorial` already has a colour in
      `assets/styles.css`, so entries will render correctly as soon as they exist.
- [ ] **Resolve the contradiction between `syllabus.qmd:19` and `:23`.** Line 19
      says times are TBD; line 23 already tells Wednesday sections what to do on
      Veterans Day.
- [ ] **Decide how many problems each student is called on**, and whether to state
      it. Tutorial correctness is 20% of the grade, and students currently have no
      way to know what one problem is worth.

## Schedule

- [ ] **Lecture 15, Thursday October 15, is a `TBD (extra lecture)` placeholder**
      (`schedule.yml:203`). Fall 2026 has 28 lecture slots against Fall 2025's 27,
      because Veterans Day falls on a Wednesday. You were considering more on
      minimax, possibly a lecture on inspection games. It's parked after Minimax
      Estimation; moving it shifts every later lecture by one slot.
- [ ] **Decide whether quizzes appear on the calendar.** There are none in
      `schedule.yml`. Twelve quizzes, Tuesdays from September 8 through December 1,
      skipping November 24 in Thanksgiving week.
- [ ] **Consider stating the counts in the syllabus** — 12 quizzes, 12 problem sets,
      ~11 tutorials. Without denominators, students can't judge what four drops
      are worth.

## Absence policy — remaining gaps

The policy is settled: four excused assignments with a presumption of valid cause,
additional requests evaluated substantively, unused excuses becoming drops chosen
to maximize the final grade.

- [ ] **Say what happens if a fifth request is declined.** It's inferable — the work
      counts as missed — but it's the first question a student will ask in that
      conversation.
- [ ] **Optional:** you decided against stating that you grant these in nearly all
      cases. Worth revisiting only if the paragraph starts reading as stricter than
      you intend.

## Course content, when there's time

- [ ] `reader/empirical-bayes.qmd` is titled "The James-Stein Estimator", duplicating
      `reader/jamesstein.qmd`. Probably a superseded draft.
- [ ] `reader/asymptotics.qmd` and `reader/convergence.qmd` overlap substantially.
      Relevant if the extra lecture slot ends up going to asymptotics after all.
- [ ] Eight reader chapters are written but excluded from the site
      (`_quarto.yml` render list). They cover the topics that nine lecture entries
      currently point at `under-construction.qmd`: testing in linear models,
      asymptotics, MLE, likelihood-based inference, multiple testing.
- [ ] `fall-2026-private` has variant files worth a look: `final2019_bad.tex`,
      `final2020_toohard.tex`, `solution2025-broken.{tex,pdf}`, `solution2025-draft.tex`,
      plus several `-old` and `-extra` homework solutions. Some are deliberate; the
      `-broken` ones probably aren't.
