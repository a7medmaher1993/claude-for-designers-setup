# Setting up Claude for design, Mac & Windows

A step-by-step setup for non-developers. By the end you will have Claude Code
running, your design tools connected, and the design skills installed. Follow the
track for your computer.

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

Prefer no terminal? Download the **desktop app** from
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

1. The first time you run `claude` (or open the app), sign in with your Claude
   account.
2. You need a paid plan for real use. **Pro (~$20/month) is enough to start.**
   Check current prices at [claude.com/pricing](https://claude.com/pricing).
3. To confirm it works, open any folder and ask Claude "list the files here." If
   it answers, you are set.

| Plan | Price | For |
|---|---|---|
| Free | $0 | Chat only, no Claude Code |
| **Pro** | ~$20/month | Start here. Most designers. |
| Max 5x | ~$100/month | Heavy daily use |

---

## Part 3: Connect your design tools (MCP)

MCP connects Claude to real tools so it reads live data instead of pasted
screenshots. Add each one with the terminal command below, or in the desktop/web
app under **Settings → Connectors → Add custom connector** (easier, no terminal).
After adding, run `/mcp` inside Claude to sign in and check status.

**Figma** (read designs, generate code, push back to Figma):
```bash
claude mcp add --transport http figma https://mcp.figma.com/mcp
```
Docs: https://help.figma.com/hc/en-us/articles/39888612464151-Claude-Code-and-Figma-Set-up-the-MCP-server

**Mobbin** (real app screens as references). Needs a Mobbin account:
```bash
claude mcp add mobbin -- npx -y mobbin-mcp
```
Docs: https://docs.mobbin.com/mcp/clients/claude-code

**Agentation** (annotate a page, Claude acts on your notes):
Go to https://www.agentation.com/mcp and run their installer. It detects Claude
Code and sets the MCP up for you, no manual command needed.

Handy: `claude mcp list` shows what is connected. `/mcp` inside Claude manages,
authenticates, and reconnects them.

---

## Part 4: Install the skills

Skills are the design workflows you invoke with a slash command like
`/impeccable`. They come from plugins. Install the ones from the session:

```bash
/plugin install frontend-design@claude-plugins-official
/plugin install impeccable@claude-plugins-community
/plugin install ui-ux-pro-max@claude-plugins-community
/plugin install emil-design-eng@claude-plugins-community
```

If a command does not resolve, the reliable way is to run `/plugin`, open the
**Discover** tab, search the name (for example "impeccable"), and click install.
To add the community marketplace first if needed:
```bash
/plugin marketplace add anthropics/claude-plugins-community
```

Useful plugin commands:
```bash
/plugin            # open the plugin manager (Discover / Installed / Marketplaces)
/plugin list       # list installed plugins
```

After installing, type `/` to see your skills. You can also add a personal skill
by dropping a `SKILL.md` file in `.claude/skills/<name>/` inside a project.

---

## Quick check before the session

- [ ] `claude` runs (terminal) or the app opens, and you are signed in.
- [ ] You are on a paid plan (Pro is fine).
- [ ] Figma / Mobbin / Agentation added (run `claude mcp list` to confirm).
- [ ] You can type `/` and see the skills (impeccable, frontend-design, etc.).

That is enough to follow along. The rest we connect together live.

---

## Reference links

- Claude Code overview: https://code.claude.com/docs/en/overview
- Pricing: https://claude.com/pricing
- MCP setup: https://code.claude.com/docs/en/mcp
- Plugins: https://code.claude.com/docs/en/discover-plugins
- Figma MCP: https://help.figma.com/hc/en-us/articles/32132100833559-Guide-to-the-Figma-MCP-server
- Mobbin MCP: https://mobbin.com/mcp
- Agentation MCP: https://www.agentation.com/mcp
