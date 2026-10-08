# Databricks Data Engineer Associate: practice exam (unofficial)

A free, single-page study site for the **Databricks Certified Data Engineer Associate** exam, built around the official exam guide dated **May 4, 2026**.

> **Unofficial.** This project is not affiliated with, endorsed by, or sponsored by Databricks. Questions, notes and simulators were written with AI assistance and checked against Databricks documentation where a source is shown. Always confirm against the [official exam guide](https://www.databricks.com/learn/certification/data-engineer-associate) and [docs.databricks.com](https://docs.databricks.com).

## What's inside

- **Mixed practice exams.** Each exam has 45 questions drawn from a 311-question bank, using the exam guide's section weights (3 / 9 / 10 / 7 / 5 / 4 / 7). Questions you got wrong come up most often, then ones you haven't seen, so every exam is different. There's an optional 90-minute timer, flags, an answer sheet, and a full review with explanations and doc links.
- **Study notes** for all seven exam sections, each with a 10-question section practice.
- **12 deep dives with interactive examples:**
  - Unity Catalog permissions simulator
  - Row filters, column masks and ABAC ("see the table as…")
  - View vs materialized view vs streaming table stepper
  - Ingestion tool chooser
  - Auto Loader schema evolution
  - SQL joins explorer
  - Window functions
  - NULL handling
  - Delta history and time travel
  - Lakeflow Jobs Run if simulator
  - Spark UI diagnosis
  - Bundle target resolver
- **Tools:**
  - Hands-on lab checklist
  - Progress-over-time chart
  - Flashcards
  - Backup and restore of your progress
- **PDF export** of any attempt or of your full history.

## Your progress stays in your browser

There's no login and no server. Everything you do (exam history, lab ticks, flashcard boxes) is saved in your browser's `localStorage` for this site:

- Every visitor automatically has their own private history. Nobody else can see it.
- Progress is per browser and per device. Use **Tools → Back up or move progress** to export a JSON file and import it somewhere else.
- Clearing site data or using private browsing removes it.

## Publish on GitHub Pages

1. Create a new **public** repository on GitHub.
2. Upload `index.html` and `README.md` to the root of the `main` branch. Don't upload any personal progress file.
3. Go to **Settings → Pages**, set **Source** to *Deploy from a branch*, choose `main` and `/ (root)`, then save.
4. After a minute or two, the site is live at `https://<your-username>.github.io/<repository-name>/`.

## How it's built

- One self-contained `index.html`: plain JavaScript and CSS, no framework, no build step.
- Fonts from Google Fonts; [pdf-lib](https://pdf-lib.js.org/) from the jsDelivr CDN for PDF export.
- The question bank is embedded in the page: Sets A–C plus the `BANK_DATA` array. Each question has an id, an exam section (`s`, 0–6), the stem, four options, the index of the correct option, an explanation, and an optional source link or "verify" hint.

## Adding questions

Add objects to `BANK_DATA` in `index.html`, following the existing format:

```js
{uid:"N54", s:2, obj:"Objective text", q:"Question stem", o:["A","B","C","D"], a:0,
 e:"Why the answer is right", src:"https://docs.databricks.com/...", topics:["joins"]}
```

Use a new, unique `uid`. Option order is shuffled on display, so `a` refers to the order you write them in. `topics` (optional) adds the question to a deep dive's practice set.

## Content notes

- The five sample questions from Databricks' own exam guide aren't included; read them in the official guide.
- Some explanations are marked "verify" where a fact wasn't confirmed against the docs when the question was written.
- Product names follow the current naming: Lakeflow Jobs, Lakeflow Spark Declarative Pipelines, Git folders, Declarative Automation Bundles, Standard/Dedicated access modes.
