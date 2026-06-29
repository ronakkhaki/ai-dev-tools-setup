# AI Dev Tools Setup

### Ronak's account of setting up a modern AI-assisted development environment

---

## How i wrote this guide:

This guide was written as it happened — including the parts that didn't work, why they didn't, and what that taught me.

## Tools I was asked to install


| Tool        | Status                   |
| ----------- | ------------------------ |
| Cursor IDE  | ✅ Installed              |
| Claude Code | ✅ Installed via CLI      |
| Codex       | ⚠️ Attempted — see below |
| GitHub      | ✅ Account created        |


---

### 1. Cursor IDE

- Downloaded from cursor.com
- Installed on Mac by dragging to Applications folder
- Opened successfully
- **First thing I learned:** I could not find any specific option to add extensions and thats when i discovered Cursor 2.0 has completely redesigned interface — no traditional Extensions panel,replaced by a new plugin system (MCP servers, Skills,
Subagents, Rules, Hooks, Plugins)



### 2. Node.js

- Before installing any AI extensions, I consulted Claude to understand the prerequisites
- Claude explained that Claude Code and Codex are written in JavaScript — a language that normally runs in web 
browsers, not on Mac's operating system directly
- Node.js is the runtime that allows JavaScript to run on a Mac outside of a browser — without it, these tools 
simply won't work
- Ran `node --version` in Terminal — returned "command not found" confirming Node.js wasn't installed
- Installed using Homebrew (Mac's recommended package manager):

```bash
  brew install node
```

- Verified by running `node -v` that returned version number confirming success



### 3. Claude Code

**What I tried first:**

- Searched for Claude Code directly within Cursor's interface — returned no results
- Discovered this is because Cursor's complete 2026 redesign removed the traditional extensions panel entirely
- Created a new chat inside Cursor asking for help installing Claude Code — it pointed me to Anthropic's 
official documentation for adding Claude Code to Cursor

**What happened:**

- Followed the official documentation link
- Hit this error immediately:
`Cannot read properties of undefined (reading 'activeEditor')`
- Researched the error across Cursor community forums 
- Established it's a known compatibility issue between the Claude Code extension and Cursor 2.0's redesigned 
architecture

**Workaround I found:**

- Installed Claude Code via Terminal using:

```bash
npm install -g @anthropic-ai/claude-code
```

- Ran `claude` in Terminal
- Claude Code v2.1.195 launched successfully

**What I'm still curious about:**
Installing Claude Code via Terminal means it runs as a standalone agent on my Mac but I'm not certain this achieves what the assessment originally envisioned, which I believe was Claude Code working visually inside Cursor's interface.

The extension path is broken due to Cursor 2.0. The CLI workaround works but creates a separate environment rather 
than an integrated one.

I'd genuinely like to understand: is there a way to bridge Claude Code running in Terminal with Cursor's visual workspace in the new 2026 interface? And is that what was intended here, or does the CLI installation satisfy the requirement?

### 4. Codex

**What I tried first:**

- Searched for Codex directly inside Cursor's interface as instructed — returned no results
- Used Cursor's chat to ask how to install the Codex extension — it pointed me to OpenAI's official 
extension link

**What happened:**

- Followed the official OpenAI extension link
- Hit the same error as Claude Code:
`Cannot read properties of undefined (reading 'activeEditor')`
- Researched further to understand why

**What I found:**

- The original Codex API was deprecated by OpenAI in 2023
- Codex capabilities now live inside GitHub Copilot and 
OpenAI's newer agent products
- The extension link still exists on OpenAI's site but is not compatible with Cursor 2.0's architecture

**Outcome:**

- No working workaround found for getting Codex inside Cursor's visual interface
**Alternative explored:**
Codex CLI is installable via Terminal using `npm install -g @openai/codex` — however this runs as a standalone agent separate from Cursor, not as an integrated extension, same limitation as Claude Code CLI.

**What I understood Codex to represent:**
Even though I couldn't install it, I now understand what it is — an AI model trained specifically on code that can read, write, and explain programming. That capability exists in the tools I did successfully set up. 

### 5. GitHub

- Created account at github.com
- Created this public repository: `ai-dev-tools-setup`
- Cloned to local machine via Terminal:

```bash
  git clone https://github.com/ronakkhaki/ai-dev-tools-setup
```

- Opened repository folder in Cursor
- Created and edited this README.md inside Cursor

---



## Issues I ran into and how I handled them



### Issue 1 — Extensions panel missing in Cursor

**What happened:** `Cmd+Shift+X` didn't open an extensions
panel and neither could I find it in toolbar. Discovered cursor 2.0 replaced it entirely with a new plugin
architecture.

**What I learned:** Tool documentation goes stale fast in
the AI space. The ability to figure out what actually works
matters more than following instructions literally.

---



### Issue 2 — Claude Code extension error

**What happened:** Official install link threw:
`Cannot read properties of undefined (reading 'activeEditor')`

**What I did:**

1. Searched Cursor community forums
2. Found this is a widespread known issue post-Cursor 2.0
3. Found the CLI workaround in Anthropic's own documentation
4. Installed via `npm install -g @anthropic-ai/claude-code`
5. Confirmed working

**What I learned:** When an official path is broken, go
one level deeper — check the underlying documentation.

---



### Issue 3 — Codex not installable

**What happened:** Same extension error as Claude Code, with no CLI workaround available.

**What I did:** Researched what Codex actually is today vs. what it was when this assessment was likely written.Found that Codex as a standalone product no longer exists in the same form.

**What I learned:** Understanding why a tool exists and
what problem it solves matters more than being able to
install it. Codex's purpose — AI-assisted code generation
— is now fulfilled by the same tools I successfully set up.

---



## What I understood about why these tools matter

This assessment is about whether someone can navigate a fast-moving AI-assisted work environment independently — figure out what's broken, research why, find a path forward, and document it clearly enough that someone else could follow.

---



## A  note of thanks

I want to thank you for designing an assessment like this one.

It felt immediately different and exciting. I had never opened Cursor before this. I didn't know what 
Claude Code was beyond the name. I learned Node.js, Homebrew, and a bit about markdown formatting from scratch today
And I certainly didn't expect to spend time researching why a deprecated OpenAI API still has a live download link.

But that's exactly what made this worthwhile. I walked away understanding not just how to set up these tools, but why they exist and where the industry is heading. This learning will stick with me.

Whether or not we work together — thank you for giving me something I actually get to keep.

— Ronak