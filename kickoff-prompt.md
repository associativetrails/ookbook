# Kickoff prompt

Copy the block below paste it into your AI agent. Paste `template.md` into the same conversation, or point the agent at it. The agent will ask you the questions it needs before it starts.

---

> I want to run a structured data collection using the browser, following the structure in `template.md`. Before you start, ask me the questions you need to fill in the template. Do not begin the collection until I have answered them. When you finish, give me back a completed markdown file whose "The task" section is precise enough that a fresh agent with no memory of this conversation could re-run the collection from the file alone. 

---

## The questions the agent will ask

It may phrase these differently, but it should cover all eight before starting.

**1. What is the source?**
Where should the agent go — a specific URL, a search on a specific site, a sequence of pages? Be precise: include the site, any search terms, and any filters you want applied.

**2. What are you trying to collect?**
Which fields should the agent extract from each result? For example: title, price, author, date, URL, description, rating. List every field you want captured.

**3. What should be excluded?**
Which results should the agent skip? Common exclusions: sponsored results, unrelated authors or brands, paywalled items, foreign-language editions, items with no price, free-tier-only items.

**4. How should the data be structured?**
One flat table, or split into sections (by category, price band, series, etc.)? State a preference, or let the agent make a sensible call.

**5. Is there a summary you want?**
Should the file include a summary section — price distribution, totals by category, notable outliers, patterns? Yes/no, and what kind.

**6. How many pages / results?**
A single page, a fixed number of pages, or paginate until results run out?

**7. Any re-run instructions you want included?**
Should the finished file include a step-by-step guide for re-running the same collection later (e.g. for monthly price tracking)? Recommended: yes. This is what makes the file an Ookbook rather than a one-off scrape.
