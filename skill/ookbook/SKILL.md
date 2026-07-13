---
name: ookbook
description: Turn a data collection into an Ookbook — a self-reproducing markdown file that carries its own re-run instructions, so the same collection (prices, listings, mentions, job postings, competitor moves) can be repeated next week or next month by handing the file back to any agent. Use this skill whenever the user says "ookbook" in any form ("turn this into an ookbook", "make an ookbook", "update this ookbook", "ookbook this"), asks to package research or scraped/collected data so it can be re-run or refreshed later, wants to track something over time (price tracking, listing monitoring), or attaches a markdown file titled "Ookbook". Trigger even if the collection already happened earlier in the conversation — converting finished work into an ookbook is the primary use case.
license: MIT — https://github.com/associativetrails/ookbook
---

# Ookbook

An Ookbook is a markdown file with both **data** (the collected results) and **behaviour** (precise instructions for reproducing the collection). A human skims to the tables; a fresh agent reads "The task" section and re-runs the whole collection. The quality bar for every mode below: **if a fresh agent with no memory of this conversation could not reproduce the collection from the file alone, the file is not finished.**

The output template is in `references/template.md`. Read it before writing any ookbook file.

## Which mode am I in?

- The user finished (or you just finished) collecting data in this conversation and says "turn this into an ookbook" → **Convert mode**
- The user wants to start a new collection as an ookbook → **Collect mode**
- The user attaches an existing ookbook file and asks to update/refresh/re-run it → **Update mode**

## Convert mode (the main one)

The collection already happened in this conversation. Your job is to reverse-engineer the method into the template — the data is the easy half; the reproducibility is the point.

1. **Audit what was actually done.** Go back through the conversation and list: every URL or search actually used (not the one first suggested — the one that worked), search terms, filters, pagination depth, and how results were extracted. If the working URL differs from what the user originally asked for, record the working one.
2. **Promote implicit decisions to explicit rules.** During ad-hoc collection, exclusions happen silently — a sponsored result skipped, a foreign-language edition ignored, an item with no price dropped. Every one of those judgement calls must become a written exclusion rule in "The task" section, otherwise the next run will apply different judgement and the data will drift between runs.
3. **Fill the template** (`references/template.md`) with the data already in context. Prefer tables over prose. Split into sections by logical grouping rather than one giant table. Include the summary/distribution section if the data has numbers.
4. **Record run metadata**: capture date, total results, page count, and the exact search URL in a code block (code blocks survive copy-paste without corruption).
5. **Only ask the user a question if a re-run-critical detail cannot be recovered from the conversation** (e.g. it's ambiguous whether an exclusion was deliberate). Don't re-interview them — the conversation is the interview.
6. **Name and deliver the file**: `ookbook-[yyyymmdd]-[short-description-of-the-data].md`, and make sure the user has a way to save it locally.

## Collect mode

No data yet. Interview first, collect second. Cover these before starting; skip any the user already answered:

1. **Source** — exact site, URL, search terms, filters
2. **Fields** — what to extract from each result (title, price, date, URL, ...)
3. **Exclusions** — sponsored results, unrelated items, paywalled, foreign-language, no-price items
4. **Structure** — one flat table or sections (by category, price band, series)
5. **Summary** — wanted? What kind (distribution, totals, outliers)?
6. **Scope** — one page, N pages, or paginate until exhausted
7. **Filename** — default to the convention above unless they specify

Then run the collection (browser tools or web search — whatever is available; if the site blocks automated access, fall back to driving a real browser if you can), and write the file per Convert mode steps 2–6.

## Update mode

The attached file's "The task" section is the instruction set — follow it exactly, including its exclusion rules. Then:

- Replace the data sections with fresh results
- Update "Last run", capture date, and result counts
- In "Notes and caveats", briefly note what changed since the previous run (new items, removed items, price movements) — that delta is usually why the user re-ran it
- If the source page has changed so the instructions no longer work, fix the instructions to match what works now and flag the change to the user
- Deliver under the same filename convention with today's date

## Things that make ookbooks fail

- Vague task steps ("search Amazon for the books") instead of exact URLs with parameters
- Exclusion rules left in the agent's head instead of written in the file
- Recording the user's requested source rather than the source that actually worked
- Summary numbers that don't match the tables — recompute them from the final data, don't carry them over from mid-conversation estimates
