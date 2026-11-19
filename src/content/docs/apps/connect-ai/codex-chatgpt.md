---
title: "Step 2: Codex and the ChatGPT desktop app"
description: Connect a Craft app to OpenAI's Codex and the ChatGPT desktop app.
sidebar:
  order: 5
  label: "2. Codex and ChatGPT"
---

The Codex command-line tool, the Codex extension for code editors and the ChatGPT desktop app share one list of MCP servers. Add a Craft app once and they can all use it.

## 1. Install Codex

Install Codex by following [OpenAI's Codex guide](https://developers.openai.com/codex), and sign in with your ChatGPT account.

## 2. Add your Craft app

Open a terminal and run this, with your own full path from [Step 1](/apps/connect-ai/find-your-app/).

On Windows, in PowerShell:

```powershell
codex mcp add wordcraft -- "C:\Users\sam\AppData\Local\Programs\ArtCraft\WordCraft\wordcraft-cli.exe" mcp
```

On macOS or Linux:

```bash
codex mcp add wordcraft -- /Users/sam/Tools/wordcraft-cli mcp
```

`wordcraft` is a label; use your app's name in lower case. Everything after `--` is the command and its arguments from Step 1. For an app that needs a folder, add it at the end.

## 3. Check it's connected

```bash
codex mcp list
```

Your app should be in the list. Restart the ChatGPT desktop app or your code editor if it was open, so it picks up the change.

Next: [Try it out](/apps/connect-ai/try-it-out/).

## Or edit the settings file

Codex keeps the list in a file called `config.toml`, in the `.codex` folder in your home folder. You can add an app there instead:

```toml
[mcp_servers.wordcraft]
command = 'C:\Users\sam\AppData\Local\Programs\ArtCraft\WordCraft\wordcraft-cli.exe'
args = ["mcp"]
```

Put a Windows path in single quotes, as above, so the backslashes don't need doubling.
