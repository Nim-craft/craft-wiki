---
title: "Step 2: Claude Code"
description: Connect a Craft app to Claude Code with one command.
sidebar:
  order: 4
  label: "2. Claude Code"
---

Claude Code is Claude in a terminal. You add a Craft app with one command.

## 1. Install Claude Code

Follow [Anthropic's setup guide](https://code.claude.com/docs/en/setup), then sign in by running `claude` once and following the prompts.

## 2. Add your Craft app

Open a terminal and run this, with your own full path from [Step 1](/apps/connect-ai/find-your-app/).

On Windows, in PowerShell:

```powershell
claude mcp add --scope user wordcraft -- "C:\Users\sam\AppData\Local\Programs\ArtCraft\WordCraft\wordcraft-cli.exe" mcp
```

On macOS or Linux:

```bash
claude mcp add --scope user wordcraft -- /Users/sam/Tools/wordcraft-cli mcp
```

What each part means:

- `wordcraft` is a label. Use your app's name in lower case.
- `--scope user` makes the app available in every folder. Without it, Claude Code only uses the app in the folder you're in now.
- Everything after `--` is the command and its arguments, exactly as in Step 1. Here the backslashes are single, not doubled.

For an app that needs a folder, add it at the end, for example `... pdfcraft-cli.exe" mcp --root "C:\Users\sam\Documents\PDFs"`.

## 3. Check it's connected

```bash
claude mcp list
```

Your app should be listed as **Connected**. Inside Claude Code, typing `/mcp` shows the same list.

To remove it later: `claude mcp remove --scope user wordcraft`.

Next: [Try it out](/apps/connect-ai/try-it-out/).
