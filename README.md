# Ookbook

**Turn a one-off data collection into a file that re-runs itself.** You describe what to collect once. You get back a structured markdown document that carries its own instructions to reproduce the same collection next week, next month, or next quarter.

![[ookbook.png]]

---

## The problem

Plenty of useful data needs watching over time, not capturing once: prices, listings, mentions, job postings, competitor moves. The collection itself is easy. Redoing it by hand every cycle - same site, same filters, same format - is the part nobody has time for, so it stops happening.

Ookbook fixes that. Each finished file contains the exact steps to reproduce it, so the next cycle is a copy and paste, not a project. It's a text file that can be updated at any time, without the need for any fancy software or workflows. 

---

## How to use it

1. Open [`kickoff-prompt.md`](kickoff-prompt.md) and copy the prompt block.
2. Paste it to your browsing agent, along with the [`template.md`](template.md) file.
3. Answer the handful of questions the agent asks (source, fields, exclusions, structure, pagination, filename).
4. Get a completed collection file back.

Claude in Chrome is the reference implementation named throughout, but nothing here assumes it. Any agent that can read web pages and write a file will do.

---

## For example
(Using Claude Desktop on Mac OS)

1. Paste the kickoff prompt and the template file into an AI chat window  ![[scr01.png]]
2. It will ask you questions about the data you want to collect and how you want it processed![[scr02.png]]
3. After processing (Claude desktop may open a browser window to collect the data), it will give you a markdown file you can save to your desktop ![[scr03.png]]
---

## How re-run works

Give the saved file back to your agent with a short instruction: 
```
Follow the instructions in the attached file to update the data
```

![[scr04.png]]

---

## Limitations

- **You need a capable browsing agent.** Ookbook is only as good as the agent you paste it into. Claude, ChatGPT (in Agent mode), anything that can run its own web search should be fine. 
- **Terms of service and robots rules apply.** Some websites restrict automated collection. Sites like LinkedIn and Amazon won't let your agent collect data on its own. If your AI agent can directly control a web browser (e.g. running the Chrome extension for Claude desktop), the agent will fall back to actually opening a browser window and "clicking" through web pages. It's quite fun to watch.
- **Reliability varies with the page.** Layout changes and anti-bot measures can break a collection or make it drift between runs.
- **Data ages.** That is the entire reason for the re-run — but it also means a stale file is a trap if you forget to refresh it.

---

## Why "Ookbook"

The idea came from software development - where an "Object" is a self-contained code block that has both **data** (attributes describing its current state) and **behaviour** (actions it can perform). In the resulting document, humans will naturally skim over the technical instructions and go straight to the data, whereas an AI agent will follow the instructions it finds. It's a short jump from OOP (object-oriented programming) to OOK (object-oriented knowledge). 

As it's like a logbook that updates itself, I thought the "Ookbook" portmanteau was distinct enough for AI to differentiate from other file types ("Turn this into an ookbook") but also recognisable for humans. And it rhymes.

(Also, I like the mental image of the [Librarian of the Unseen University](https://wiki.lspace.org/Librarian) swinging through the library to collect data for me. Oook!)

---

## License

Ookbook is available under the [MIT License](LICENSE).

---

Made by [Associative Trails](https://associativetrails.com).
