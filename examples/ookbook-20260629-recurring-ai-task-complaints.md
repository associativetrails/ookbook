# Recurring AI-Task Complaints — Community Signal Collection

## About this file

A first-pass collection of recurring tasks that people want AI to do but struggle with, gathered from AI and small-business communities and complaint archives. The purpose is to identify which universal jobs to build tools for and blog about next. Findings are clustered into candidate jobs and scored by frequency, friction, and fit with the Associative Trails thesis. This pass was run via web search aggregation, not deep thread-level scraping (see caveats).

---

## The task (for re-running or updating later)

1. Visit the source communities listed below and search each for posts where users describe a task they want AI to do and cannot get done well. Hunt specifically for the phrase pattern "how do I get [AI] to..." and for frustration posts sharing manual workarounds.
2. For each post, note: the task being attempted, the specific failure or frustration, any workaround mentioned, and the rough frequency of the complaint (one-off vs repeated theme).
3. Cluster individual posts into candidate jobs (a job is a repeated task, not a single post).
4. Score each candidate job 1-5 on three axes: Frequency (how often it recurs), Friction (how unsolved it is, judged by hacky workarounds and persistence), Thesis-fit (how well it ladders into the paid tiers and connects to existing essays).
5. Exclude: model-vendor gripes that no third party can solve (pricing, rate limits, outages, over-refusal), one-off posts with no echo, and pure tool-recommendation requests.

**Source list / starting points:**
```
Reddit: r/ChatGPT, r/ClaudeAI, r/artificial, r/productivity, r/Entrepreneur, r/smallbusiness, r/freelance
Beyond Reddit: Indie Hackers, Hacker News "Ask HN" threads, profession subs (r/consulting, r/marketing, r/accounting)
Review mining: 1-2 star reviews of major AI tools on G2, Capterra, Trustpilot
Complaint archives: chatgptdisaster.com complaint library, AI hallucination stat roundups
```

**Re-run method (recommended):** for accurate frequency counts, run this through a Reddit-specific research tool (Reddily, PainOnSocial, or F5Bot for alerts) or a browser pass that reads actual threads. Web search alone surfaces themes but undercounts frequency.

**Last run:** 2026-06-29
**Total candidate jobs identified:** 7

---

## Candidate jobs (ranked by composite score)

Scores are 1-5. Composite is the sum (max 15). Higher is a stronger next focus.

| Candidate job | What people are trying to do | The recurring failure | Freq | Friction | Thesis-fit | Composite |
|---------------|------------------------------|-----------------------|:----:|:--------:|:----------:|:---------:|
| **Verify / fact-check AI output** | Trust what the AI produced before using it | ~20% hallucination rate persists; invented citations; "sounds most confident when wrong" | 5 | 5 | 5 | **15** |
| **Retain context / memory** | Keep the AI aware of prior work across sessions and tools | Cross-chat memory regressions; context rot after 30-50 messages; people manually migrating memory between tools | 5 | 4 | 5 | **14** |
| **Standardise AI use across a team** | Get a whole team using AI to one consistent standard | "Biggest barriers are organizational: unclear ownership, no shared workflows, no accountability" | 4 | 5 | 5 | **14** |
| **Sanitise / redact before prompting** | Make sensitive content safe to paste into AI | Manual redaction is risky; data hides in metadata, revision history, and OCR layers; few usable tools; GDPR makes it a present-tense problem (EU AI Act adds obligations from Dec 2027) | 4 | 4 | 5 | **13** |
| **Keep a consistent voice / house style** | Produce drafts that hold a specific writing voice | Voice degradation; "everything is now a LinkedIn post in a trench coat"; lost a tuned style | 4 | 3 | 4 | **11** |
| **Get genuine pushback (anti-sycophancy)** | Have the AI challenge rather than agree | Models reward guessing over admitting uncertainty; no built-in dissent | 3 | 4 | 5 | **12** |
| **Monitor / collect periodically** | Watch a source over time without redoing it by hand | No native re-run; manual repetition each cycle | 3 | 4 | 4 | **11** |

---

## Mapping to the three tiers

| Candidate job | Small (capability) | Medium (consistency) | Large (governance) |
|---------------|--------------------|----------------------|--------------------|
| Verify / fact-check | Personal verification skill | Verification standard per deliverable type | Auditable assurance layer |
| Retain context | Personal second brain | Team knowledge discipline + house context | Enterprise company brain with controls |
| Standardise team use | (n/a, this *is* medium) | The core medium engagement | Governed AI operating standard |
| Sanitise / redact | Redact-before-paste skill (Presidio) | Team redaction standard | Auditable redaction gate (GDPR now, EU AI Act from 2027) |
| Consistent voice | Style-locked drafting tool | House style standard | Compliance-checked output pipeline |
| Anti-sycophancy | **Roundtable (built)** | Shared critic framework | Output assurance + audit trail |
| Monitor / collect | **Ookbook (in progress)** | Managed intelligence function | Governed market-intel infrastructure |

---

## Summary / notes

The two highest-scoring untouched jobs are **Verify / fact-check** (15) and **Retain context / memory** (14). Both are the strongest candidates for the next small-tier tool and blog series after Roundtable and Ookbook, for three reasons: the failure is real and persistent (hallucination rates have not fallen, memory loss is a live and worsening complaint), the workarounds are visibly hacky (people manually migrating memory between tools, pasting context back every session), and both ladder directly into paid tiers your essays already argue for. Verify connects to *Tacit Debt and the Verification Gap*; Retain context connects to *Agents Cannot Do Osmosis* and the company-brain thread.

"Standardise AI use across a team" also scored 14, but it is a medium-tier job, not a small-tier tool. It does not have a free-tool entry point. Treat it as confirmation of the medium-tier offer rather than the next thing to build, and as a strong blog topic aimed at the buyers who hold medium budgets.

**Long-tail addition (2026-06-29):** "Sanitise / redact before prompting" was added from a second scan aimed at underserved, less-crowded markets. It scored 13. It is defensive and unglamorous, which is why it is uncrowded, and it has a live regulatory forcing function in GDPR, which is already in force (the EU AI Act adds logging and oversight obligations from December 2027, per the high-risk briefing in the Clive folder; the earlier "August 2026" framing was wrong). It ladders into the governance tier more cleanly than any other candidate and connects to Clive's classification machinery and the EU AI Act briefing already in that folder. Treat it as a genuine seventh job. Two related frustrations from the same scan were deliberately not added as separate jobs: "last-mile delivery" (getting AI output into the tool/format you actually use) is a strong but horizontal utility worth holding as a candidate, and "instruction adherence" is better absorbed into Verify as a mode (it checks the output obeys the brief, the same external-checker architecture pointed at instructions instead of facts).

Two notable anomalies. First, the loudest vendor complaints (rate limits, over-refusal, mid-response model swaps) are explicitly excluded because no third party can fix them, but their volume confirms general frustration that a trusted, stable workflow layer is wanted. Second, "Verify" and "anti-sycophancy" are close cousins: both are about not trusting confident AI output at face value. Roundtable already addresses the judgment side; a Verify tool would address the factual side. They may be one product line, not two.

---

## Notes and caveats

- Data captured 2026-06-29 via web search aggregation across community discussions, complaint archives, and 2026 hallucination/usage statistics. This surfaces themes reliably but undercounts exact frequency.
- Excluded: vendor-only issues (pricing, rate limits, outages, over-refusal), one-off posts, and pure tool-recommendation requests.
- Frequency scores are judgement calls from theme prevalence, not counted post volumes. For hard counts, re-run through a Reddit research tool or browser thread pass as noted in the task section.
- Time-sensitive: hallucination rates, memory features, and model behaviour change with each vendor release. Re-run quarterly.

---

*Sources: [ChatGPT Complaint Library 2026](https://chatgptdisaster.com/stories.html), [LLM Hallucination Statistics 2026](https://sqmagazine.co.uk/llm-hallucination-statistics/), [AI Hallucination Statistics (Suprmind)](https://suprmind.ai/hub/insights/ai-hallucination-statistics-research-report-2026/), [Context Rot (Product Talk)](https://www.producttalk.org/context-rot/), [The AI Tools Small Businesses Are Using (SBE Council)](https://sbecouncil.org/2026/04/25/the-ai-tools-small-businesses-are-using/), [Small Businesses Are Using AI (US Chamber)](https://www.uschamber.com/co/run/technology/small-businesses-are-using-ai-heres-whats-actually-working).*
*Captured: 2026-06-29 — first pass, web search aggregation.*
