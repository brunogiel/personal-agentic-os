# SecondBrain

**Claude starts every session guessing who you are.** This stops the guessing: a few plain-text files it reads on startup turn it into _your_ assistant, not a generic one. It's not a second brain for you to read — it's a second brain for your assistant to operate from.

A simple, installable method to organize how you work with **Claude Code** (or **Cowork**) and grow it over time. You install one thing, a coach, and it builds and grows the rest with you, one rung at a time.

Built for anyone: total beginner or power user. You don't need to code. If you do, the code/context split is already baked in.

> 🇦🇷 Method content is in Spanish (rioplatense). This README is in English for reach. Spanish version: [README.es.md](README.es.md).

---

## Why this works

Claude is a brain that generates text. The harness (Claude Code, Cowork) gives it hands and memory. **Your folders are what turn it into _your_ assistant.** A few plain text files, read at the start of every session, stop it from guessing who you are and how you work. That is the whole trick. The rest is staying organized.

Most people never write those files. This gives you the seed and a coach that walks you through growing it. You'll feel it by the **second session**: it comes back already knowing what you told it in the first.

## Install

Two paths. Pick the one that's you.

### 🖥️ Cowork (no terminal) — the easy one

Install it as a plugin, straight from Cowork's UI:

1. Open the **plugins** panel and add this marketplace: `brunogiel/secondbrain-claude`
   (or type `/plugin marketplace add brunogiel/secondbrain-claude`).
2. Install the **secondbrain** plugin
   (or type `/plugin install secondbrain@secondbrain-claude`).
3. Open (or make) a folder where you want your brain to live, somewhere that syncs (Drive, iCloud, Dropbox), and open it in Cowork.
4. Say **"set up my system"** (or `/second-brain-coach`).

No terminal, no zip, no git. The coach builds your brain folder *with* you, one step at a time, and **always asks before it creates anything** (it won't make a folder behind your back). And the plugin **updates itself**.

### ⌨️ Claude Code (terminal)

```bash
curl -fsSL https://raw.githubusercontent.com/brunogiel/secondbrain-claude/main/install.sh | bash
```

Then open the folder and type **`/second-brain-coach`**.

---

Either way, the split is the same. **The method installs as an app, outside your folder**: as a plugin in Cowork, or globally in `~/.claude/skills/` in Claude Code. It carries the coach (with its doctrine, templates, and examples) plus the **kit** it installs into your brain (`kit/brain/` the base files, `kit/skills/` the use-skill catalog), plus the `actualizar` updater in Claude Code. **Your folder only ever holds your own stuff**: your `0. Inbox/` + PARA folders and the essentials (`CLAUDE.md` router, `ESTADO.md`, `ESCALERA.md`, `AGENTS.md`, your identity under `2. Áreas/yo/`). The **skills you actually use** (redactar, anti-slop, triage, auditar, crear-skill, evaluar-skill, ppt-builder, panel) are NOT dumped on you: the coach adds each one to a plain, visible `skills/` folder as you climb, so you see it, open it, and learn how it's built. They fire through the **"Mis skills" table in your `CLAUDE.md`** (a phrase → a skill) — which is why they work the same in **Claude Code, Cowork, and Codex** (all three read your `CLAUDE.md`; Codex via `AGENTS.md`), no Claude-only folder needed.

## Already have a system?

You don't have to migrate. Install it and use it however you want. If you already have a folder that works, the coach **reads your structure and keeps it**: it won't rename your folders or force PARA on you. It maps what you have into your router (the `CLAUDE.md` the assistant reads at startup) so it stops guessing where things live, then proposes a couple of improvements *in your own structure*, one at a time. Take the ideas you like, leave the rest. PARA is just the default packaging for someone starting from zero, not a requirement. The one non-negotiable is the router knowing your structure; everything else is opt-in.

It's non-destructive and reversible (see *What it touches* below), so there's no big decision to make: install it, try it, keep what helps.

## What it touches (and how to undo it)

No black box. The exact split:

- **Your folder** gets only your own content (your `CLAUDE.md`, identity, projects, inbox, the use-skills you adopt), and **the coach builds it with you, asking** — it never creates or overwrites anything without your OK (it skips anything that exists), so it can't clobber a system you already built. The **curl installer doesn't touch your folder at all**; it only installs the method globally.
- **The method** installs as an app, outside your folder: a **plugin** in Cowork, or globally in `~/.claude/skills/` in Claude Code (the coach, plus the `actualizar` updater in Claude Code). None of it lives in your folder.
- **Updates** only refresh that engine. In Cowork the plugin updates itself; in Claude Code, `actualizar` does it. Either way they never touch your folder, so your edits are safe.
- **Uninstall** removes only the engine; your folder stays untouched. In Cowork, remove the plugin from the UI (or `/plugin uninstall secondbrain`). In Claude Code:
  ```bash
  curl -fsSL https://raw.githubusercontent.com/brunogiel/secondbrain-claude/main/uninstall.sh | SB_YES=1 bash
  ```

## The ladder (grow one rung at a time)

You don't build the whole system on day one. You climb. The coach teaches you the idea behind each rung, not just what to do.

| Level | What you learn + add | What you get |
|---|---|---|
| **0** | The 3 layers (model / harness / your folders) + capture: it knows you (`sobre-mi` + `como-trabajo`) and nothing slips (`0. Inbox/`) | It stops guessing who you are |
| **1** | Your first project (its own brain + decision log) | You never re-explain a project twice |
| **2** | Shortcuts (route the assistant instantly) | Say "my expenses" and it knows where to look |
| **3** | Your first skill (read the shipped one, then build your own), and what a script is | A phrase triggers a whole recipe |
| **4** | The system works *for* you: a routine that runs on its own + connect a tool via MCP so it has eyes (mail, calendar) | It works while you sleep, on your real data |
| **5** | You orchestrate: several skills working together on one task (use the example orchestrator, then build yours) | Big jobs, split and recombined |
| **6** | You maintain it: a health check (`auditar-sistema`) + tune a skill (`evaluar-skill`) | The system doesn't rot silently |
| *(if you code)* | An optional branch (not a level): code/context split + subagents in your own code | Code in its repo, context here |

Beginner or advanced? The coach adapts: one rung at a time with full teaching for newcomers, or a fast multi-rung setup plus an advanced track for power users. Ask **`/second-brain-coach`** anytime: it tells you where you are and proposes the next step. It proposes, you decide.

## Works in Cowork, Code, or anything else

Your **brain** is just plain text in one synced folder, so it's the same wherever you open it. Start in **Cowork** (no terminal needed); grow into **Claude Code** by opening the same folder, no migration. And the text itself isn't tied to Claude: your folders, identity, and projects work with **Codex, Cursor, or whatever comes next** (a shipped `AGENTS.md` points non-Claude agents to your `CLAUDE.md`).

To be honest about the line: your **brain** (your text) *and* your **use-skills** are portable — the skills live in a plain `skills/` folder and fire through your `CLAUDE.md` table, which Code, Cowork and Codex all read (Codex via `AGENTS.md`). The only Claude-specific bit is the **engine** (the `/second-brain-coach` command and the few maintenance skills); in another harness you just drive those by asking in words. The harness is the hands; the brain is yours.

> **And if you build software in earnest** (epics, PRDs, a team) — that's a different sport. Pair SecondBrain with a dev method like [BMAD-METHOD](https://github.com/bmad-code-org/BMAD-METHOD): SecondBrain keeps your context and decisions, the dev method runs the build. They sit side by side at the code/context split (Level 5).

## What's inside

- **`CLAUDE.md`** — your root file, a thin router read at the start of every session.
- **`ESTADO.md`** — your dashboard: where you are, what's active (the thin one the assistant reads every session).
- **`ESCALERA.md`** — your gamified growth tracker: levels 0→6, a checklist per level, what you've done and what's next. It ends with **"📦 Todo lo que trae el kit"** — a catalog of what you see and manage (base files + use-skills) with a checkbox each, so you can see in one place what you have and what's missing. The coach keeps it updated; ask it "how am I doing?" or "what skills do I have?" anytime.
- **`AGENTS.md`** — a 6-line pointer so non-Claude agents (Codex, etc.) find your `CLAUDE.md`.
- **`0. Inbox/`** — capture without deciding: toss the murky stuff here, "cook" it later (`INBOX.md` holds the protocol).
- **`sobre-mi.md` / `como-trabajo.md` / `mi-estilo.md`** — who you are, how you like to work, and a sample of your writing voice (fill-in templates, under `2. Áreas/yo/`).
- **`soul.md` / `dev-prefs.md`** — what you're really about (fills in over time, in conversation) and, if you code, how you like to work the code (`dev-prefs.md` ships with a block of universal engineering rules already baked in, so it's not an empty template). The coach adds these as you climb; they don't ship on install.
- **`3. Recursos/arquitectura-skills.md`** — your reference for building good skills (rule of 3, DET/LAT, anatomy, common mistakes).
- **`3. Recursos/anti-slop-writing.md`** — the full anti-slop doctrine (the 5 rules, with blacklists and before/after examples) that the `anti-slop` skill draws on.
- **The method** installs as an app outside your folder (a plugin in Cowork, or globally in `~/.claude/skills/` in Claude Code), not in your brain: the coach carries its doctrine (`reference.md`), templates, and examples, plus the **kit** it installs into your brain (`kit/brain/` base files, `kit/skills/` use-skill catalog). Nothing of the method clutters your brain — you only see your own content.
- **The engine** (🔒 outside your folder, invisible, called by name, never clutters your brain):
  - **`second-brain-coach`** — the one command you use; it walks you up the levels and teaches as you go (`/second-brain-coach`), and **brings your closed Claude Projects into the system** when you ask (built into the coach, not a separate skill).
  - **`actualizar`** (Claude Code only) — checks if the kit has a new version and installs it with your OK. In Cowork the plugin updates itself, so it isn't needed or shown.
- **The skills you use** (👁 visible in `skills/`, added by the coach as you climb — dormant until a phrase triggers them):
  - **`redactar`** — writes in your voice (learns it from your own sample texts).
  - **`anti-slop`** — strips the "AI smell" out of any text.
  - **`crear-skill`** — helps you build a new skill the right way.
  - **`evaluar-skill`** — checks a skill against its own SKILL.md and proposes fixes (for when you have several to keep sharp).
  - **`auditar-sistema`** — a health check of your system (great as a routine).
  - **`triage`** — your morning brief and action items, pulled across your sources: mail, calendar (a meetings report) and your work chat/tasks (Slack, Jira, Linear, Trello, Notion comments, whatever you use). Each source needs its MCP; mail alone is enough to start.
  - **`ppt-builder`** — builds a deck (or post, video, carousel, landing) in 5 stages; the **stateful orchestrator example** (it coordinates `redactar` + `anti-slop` + your pptx skill). Shows up at Level 5.
  - **`panel`** — brings 2-5 reviewers with different lenses to look at a piece you're making (a doc, email, proposal, copy) from several angles before you ship it, then hands the ball back to you (it shows angles, it doesn't decide); the **multi-agent orchestrator example**. Shows up at Level 5.

## Philosophy

- **Propose, you decide.** Nothing gets created without your OK.
- **One rung at a time.** No overwhelming to-do lists.
- **Teach as you climb.** You learn the idea, not just the task.
- **Light to run.** Reads only what it needs, so it stays cheap even on the $20 plan.
- **Everything ships dormant.** A skill does nothing until a phrase wakes it up.

## Credit

Made by [Bruno Gielczynsky](https://www.linkedin.com/in/brunogiel/). Part of a family of installable AI methods alongside [Empat.ia](https://github.com/brunogiel/Empat.ia).

## License

MIT. Use it, fork it, make it yours.
