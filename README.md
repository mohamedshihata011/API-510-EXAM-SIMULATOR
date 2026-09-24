# API 510 Exam Trainer

A single-page study app for the **API 510 Pressure Vessel Inspector** certification exam.
No build step, no backend — one `index.html` plus images. Progress is kept in the browser.

## What's in it

- **767 questions** drawn from past papers and study sets, de-duplicated.
- **Code-verified answers.** Every question was re-checked against the published text of
  API 510, API 576, API 577, ASME BPVC Sections V / VIII Div 1 / IX, and ASME PCC-1 / PCC-2.
  The clause is the authority, not the marking in the source files — 24 answers were corrected
  that way, and 595 questions now quote the governing clause verbatim with its page number.
- **Figures and tables from the codes.** 53 charts and tables (UCS-66 impact-test exemption
  curves, UG-84.1, UW-12, QW-451.1, T-276, PCC-2 501-3.3-1, the API 577 weld-defect
  radiographs and weld symbols, …) are cropped out of the standards and shown on answer reveal.
- **Worked solutions** step by step for every calculation question.
- **Five mock papers**, each split into a closed-book part (~106 questions) and an open-book
  part (~48) — the same closed-heavy balance as the real exam. Per-part timer, per-part score,
  a Done tick and a Reset.
- **Favourites** — star a question and it stays in its own section, untouched by exam resets.
- **Your own supporting images** — attach a screenshot to any question; it shows with the answer.
- Light and dark theme, works on phones.

## Closed vs open book

The split follows the usual convention for the exam:

| Closed book | Open book |
|---|---|
| API 510, API RP 571, 572, 576, 577, 578 | ASME BPVC V, VIII Div 1, IX · ASME PCC-2 · API 579, 580 |

## Run it locally

```bash
python3 -m http.server 8000     # then open http://localhost:8000
```

Opening `index.html` straight off the disk works too.

## Deploy

Static site, output directory is the repo root.

```bash
npx vercel            # preview
npx vercel --prod     # production
```

No environment variables and no build command are needed.

## Data and storage

Everything lives in `index.html`; the question bank is inlined as JSON. Scores, favourites,
exam state and attached images are stored in the browser's `localStorage` under
`api510trainer.v1`, so they stay on the device and never leave it.

## Note on the code extracts

The quoted clauses and the cropped figures are excerpts from copyrighted standards, included
here for personal study. Keep this repository private unless you hold the rights to
redistribute them.
