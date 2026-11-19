---
title: "Step 2: VS Code with GitHub Copilot"
description: Connect a Craft app to GitHub Copilot in Visual Studio Code.
sidebar:
  order: 7
  label: "2. VS Code with Copilot"
---

VS Code can add an MCP server for you through a short series of questions.

## 1. Set up Copilot

Install [VS Code](https://code.visualstudio.com), then sign in to GitHub Copilot from the Copilot icon in the status bar.

## 2. Add your Craft app

1. Open the Command Palette: **Ctrl+Shift+P** on Windows and Linux, **Cmd+Shift+P** on macOS.
2. Type **MCP: Add Server** and press **Enter**.
3. Choose **Command (stdio)**.
4. Enter the full path from [Step 1](/apps/connect-ai/find-your-app/), a space, and the arguments, for example:

   ```text
   "C:\Users\sam\AppData\Local\Programs\ArtCraft\WordCraft\wordcraft-cli.exe" mcp
   ```

5. For the name, enter your app's name in lower case, such as `wordcraft`.
6. Choose **Global** to use it in every window, or **Workspace** for this folder only.

VS Code saves it to a file called `mcp.json` and opens it, so you can check it.

## 3. Start it and check

1. The first time it starts, VS Code asks whether you trust the server. Choose **Trust**.
2. Open the Command Palette again and run **MCP: List Servers**. Your app should be listed as running.
3. In the Copilot Chat view, switch to **Agent** mode, then open the tools button in the message box. Your app's tools are listed there.

Next: [Try it out](/apps/connect-ai/try-it-out/).
