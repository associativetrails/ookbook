# Convert prompt

Just finished a data collection in an AI chat and liked the result? Paste the block below into the **same conversation** (along with `template.md`, or point the agent at it) and you'll get the result back as an Ookbook — a file that can re-run itself.

If you're using Claude with the Ookbook skill installed, you don't need this — just say "turn this into an ookbook".

---

> Turn the data collection we just did into a self-reproducing markdown file, following the structure in `template.md`. The data is the easy half — the point of the file is the "The task" section, which must let a fresh agent with no memory of this conversation reproduce the collection exactly. To write it:
>
> 1. Audit this conversation for what you actually did: the exact URLs and search terms that worked (not what was first suggested), filters, pagination depth, and how you extracted each result.
> 2. Promote every silent judgement call into a written rule. If you skipped sponsored results, foreign-language editions, or items without prices, state each exclusion explicitly — otherwise the next run will apply different judgement and the data will drift.
> 3. Fill the template with the data already in this conversation. Prefer tables. Recompute any summary numbers from the final data rather than reusing mid-conversation estimates.
> 4. Put the exact search URL in a code block, and record today's date, total results, and page count.
> 5. Only ask me a question if a re-run-critical detail genuinely can't be recovered from this conversation.
> 6. Name the file `ookbook-[yyyymmdd]-[short description of the data].md` and give me a way to save it locally.

---

## Re-running later

Hand the saved file back to any capable agent with:

```
Follow the instructions in the attached file to update the data
```
