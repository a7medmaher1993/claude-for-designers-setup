# Setting up Claude for design, Mac & Windows

A step-by-step setup for non-developers. By the end you will have Claude Code
running and ready for the design workflow from Session 1. Follow the track for
your computer.

التعليمات بالإنجليزي عشان الأوامر، بس كل خطوة مشروحة. لو علقت في أي خطوة، اسأل في
`#ask-the-mentors`.

---

## Part 1: Install Claude Code

### Mac

1. Open **Terminal** (press `Cmd + Space`, type `Terminal`, hit Enter).
2. Copy and paste this line, then press Enter:
   ```bash
   curl -fsSL https://claude.ai/install.sh | bash
   ```
3. Wait for it to finish (a minute or two).
4. Close and reopen Terminal, then type `claude` and press Enter.

Prefer no terminal? Download the **desktop app** instead from
[claude.ai/download](https://claude.ai/download), or use the web at
[claude.ai/code](https://claude.ai/code), nothing to install.

### Windows

1. Open **PowerShell** (press the Start key, type `PowerShell`, hit Enter).
2. Copy and paste this line, then press Enter:
   ```powershell
   irm https://claude.ai/install.ps1 | iex
   ```
3. Wait for it to finish.
4. Close and reopen PowerShell, then type `claude` and press Enter.

Alternatives: `winget install Anthropic.ClaudeCode` in PowerShell, or the
**desktop app** from [claude.ai/download](https://claude.ai/download), or the web
at [claude.ai/code](https://claude.ai/code).

---

## Part 2: Sign in and pick a plan

1. The first time you run `claude` (or open the app), it asks you to sign in with
   your Claude account. Sign in or create one.
2. You need a paid plan for real use. **Pro (~$20/month) is enough to start.**
   Check current prices at [claude.com/pricing](https://claude.com/pricing).
3. To confirm it works, open any folder and ask Claude something simple like
   "list the files here." If it answers, you are set.

| Plan | Price | For |
|---|---|---|
| Free | $0 | Chat only, no Claude Code |
| **Pro** | ~$20/month | Start here. Most designers. |
| Max 5x | ~$100/month | Heavy daily use |

---

## Part 3: Connect your design tools (MCP)

MCP connects Claude to real tools so it reads live data instead of pasted
screenshots. The three from the session are **Mobbin**, **Figma**, and the
**annotation** tool.

**The general way to add one:**
- In the **desktop or web app**: open **Settings → Connectors / MCP**, find the
  tool, and follow its connect button. This is the easiest path.
- In the **terminal**: `claude mcp add <name>` (for example `claude mcp add figma`).

Each tool has its own connect step (signing into Figma, Mobbin, etc.). Maher will
walk through connecting these live in the session, so do not worry if a tool asks
for its own login.

---

## Part 4: Get the skills

Skills are the design workflows you invoke with a slash command like
`/impeccable` or `/frontend-design`.

- Most skills come bundled in a **plugin** you install once. In the app, browse
  the plugin marketplace and install the design plugin; or in the terminal use
  the `/plugin` command.
- You can also add a personal skill by dropping a `SKILL.md` file in a
  `.claude/skills/<name>/` folder inside your project.

Maher will share the exact plugin/skill list used in the session so you can
install the same set. Once installed, type `/` to see them.

---

## Quick check before the session

- [ ] `claude` runs (terminal) or the app opens, and you are signed in.
- [ ] You are on a paid plan (Pro is fine).
- [ ] You know where Settings → Connectors / MCP is.
- [ ] You can type `/` and see at least one skill.

That is enough to follow along. The rest we connect together live.
