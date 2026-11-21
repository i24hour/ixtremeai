# Priyanshu++ — Session Context

> **For any new Claude Code session (laptop or phone):** read this file first. It records what Priyanshu has explained so far about the Priyanshu++ project. Continue from here; don't ask him to explain it again.

Last updated: 2026-11-21

---

## 1. What we are building

**Priyanshu++** (also called "Priyanshu version+"): a complete AI clone of Priyanshu with superhuman capabilities. It's part of **iXtreme AI**, and it's the first project under the iXtreme concept Priyanshu calls "preansionism" (probably "Priyanshu-ism": his way of thinking and working, written down as a system).

- **Goal:** replace himself completely. The clone should handle everything from his basic, everyday work to his extraordinary work.
- **It's not a single bot.** It's a **collection of agents** with one **controlling system** (the brain) on top.
- **Don't rebuild what already exists.** Thousands of AI tools exist already. We don't build a new ChatGPT or new base agents. We build the **control system** that uses the existing tools.

### The core idea, in his words

> "I need to create, first, a controlling system where all of my data will be available, and my computer and my thing can do the work. It can basically understand me, like how I am going to do things — but with a superhuman capability."

The controlling system must be able to:
- Control Claude / Claude Code
- Control Cursor
- Control Codex
- Control OpenCode
- Control Grokbot
- **Create** new bots and agents
- **Delete** bots and agents
- Give commands to any of them
- Create new GitHub repositories and make changes
- Act across all his platforms (below)

---

## 2. How Priyanshu works (his environment)

**AI and dev tools he uses:**
- Grokbot
- Cursor
- Claude Code (on laptop **and on phone**)
- Codex
- OpenCode
- Accounts on OpenAI, Azure, Claude, and others

**Devices:**
- Phone (works heavily from it)
- Laptop

**Communication and social:**
- Telegram
- WhatsApp
- Phone calls
- LinkedIn
- X (Twitter)
- GitHub

### Example workflow: AI credits

Priyanshu holds accounts on OpenAI, Azure, Claude and other providers, and helps people get credits on them. He uses **Grokbot to find people who need credits**, then chats with them. The clone should eventually handle this kind of loop: finding people, reaching out, chatting, following up.

> ⚠️ Open item: many providers' terms (OpenAI, Anthropic, Azure) restrict reselling or sharing account access and credits. Before automating this, confirm exactly how credits are transferred so the clone doesn't put his accounts at risk.

---

## 3. Architecture (agreed direction)

```
                 PRIYANSHU (phone · laptop · Telegram · WhatsApp · voice)
                                   │
                    ┌──────────────▼──────────────┐
                    │      PRIYANSHU++ BRAIN      │
                    │  • Identity: who he is,     │
                    │    how he decides           │
                    │  • Memory: all his data     │
                    │  • Planner: splits tasks    │
                    │  • Rules: what needs his OK │
                    └──────────────┬──────────────┘
                                   │ commands
      ┌──────────┬──────────┬──────┴─────┬──────────┬──────────────┐
  Claude Code  Codex    Cursor /     Grokbot    GitHub     Telegram / WhatsApp /
  (headless)  (exec)    OpenCode    (search)   (repos)     LinkedIn / X (people)
      └──────────┴──────────┴────────────┴──────────┴──────────────┘
          + Agent factory: creates, runs and deletes new bots on demand
```

Layers of the clone:

| Layer | Contents |
|---|---|
| Identity and values | Who he is, priorities, how he decides, red lines |
| Knowledge / memory | Projects, iXtreme AI, clients, skills, history, all his data |
| Voice | How he writes and talks |
| Decision patterns | "In situation X, Priyanshu does Y" |
| Abilities (the "++") | Control of all tools and platforms listed above |
| Autonomy rules | What it does alone, what it drafts for approval, what it never does |
| Feedback loop | Learns from every correction he makes |

What makes it superhuman:
- **Parallel:** many Claude Code, Codex and Cursor jobs running at once
- **Always on:** keeps working while he sleeps, reports on Telegram
- **Total recall:** remembers every conversation, client and repo
- **Self-extending:** builds a new tool or bot when none exists

How the tools can be controlled programmatically: `claude -p` (Claude Code headless), `codex exec`, `opencode run`, Cursor's CLI agent, the GitHub API / `gh`, and the Telegram Bot API.

---

## 4. Principles and cautions

- **Orchestrate, don't rebuild.** Reuse existing AI tools.
- **Be open with people.** When the clone talks to others, it should present as "Priyanshu's AI" or send drafts he approves, not secretly pass as him. That protects him with clients and partners.
- **Platform bans.** Unofficial automation on WhatsApp, LinkedIn and X can get accounts banned. Prefer official APIs, and keep anything sent to real people behind his approval at first.
- **Grow autonomy step by step.** Start with drafts and approvals, then hand over more control as trust builds.

---

## 5. Next steps (not started yet)

Priyanshu said the **purpose must be clear before building**. Pending:

1. **Vision and operating doc:** purpose, full tool inventory, work inventory (basic → extraordinary), autonomy rules, build roadmap.
2. **His typical day:** ask him to walk through it, wake-up to sleep, to build the work inventory.
3. **Identity and decision profile:** a 15–20 minute interview to capture how he thinks and decides.
4. **Phase 1 build (proposed):** Telegram as the interface, plus a memory store, plus control of Claude Code and Codex on his laptop.

Open questions for him:
- What should the clone take over **first**?
- What raw data can he provide (emails, WhatsApp/Telegram exports, docs, posts, voice recordings)?
- On day one, should it only draft for his approval, or act on its own in some areas?
- Where should the brain run: laptop, a server, or the cloud?
