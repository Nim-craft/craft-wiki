---
title: Connect an AI assistant
description: A step-by-step, beginner-friendly guide to connecting Claude, ChatGPT, Cursor or Copilot to a Craft app over MCP.
prev: false
sidebar:
  order: 1
---

Most Craft apps can be used by an AI assistant as well as by you. Once they're connected, you can ask the assistant in plain words, for example *"make a one-page flyer for the school fair"*, and it uses the app to do the work.

This guide connects the two, one step at a time. You don't need to be a programmer. Allow about ten minutes.

## How it works, in plain words

The assistant and the Craft app talk to each other through **MCP**, the [Model Context Protocol](https://modelcontextprotocol.io). Think of it as a plug: the Craft app offers a list of things it can do, and the assistant can use them.

Each Craft app comes with a small helper program whose name ends in `-cli`, such as `wordcraft-cli`. You tell your assistant where that helper is, and the assistant starts it whenever it needs the app. You don't have to start anything yourself.

## What you need

- **A Craft app**, installed on your computer. See its **Install and update** page.
- **An AI assistant that runs on your computer**, such as the Claude desktop app, Claude Code, Codex or the ChatGPT desktop app, Cursor, or VS Code with GitHub Copilot.

:::note
Assistants in a web browser, such as claude.ai or chatgpt.com, can't reach programs on your computer. Use the desktop app or one of the other assistants instead.
:::

## The three steps

1. [Find your app's command](/apps/connect-ai/find-your-app/): where the helper program is, and what to type.
2. Add it to your assistant. Pick yours:
   - [Claude desktop app](/apps/connect-ai/claude-desktop/): the easiest place to start if you're new to this.
   - [Claude Code](/apps/connect-ai/claude-code/)
   - [Codex and the ChatGPT desktop app](/apps/connect-ai/codex-chatgpt/)
   - [Cursor](/apps/connect-ai/cursor/)
   - [VS Code with GitHub Copilot](/apps/connect-ai/vs-code/)
   - [Other assistants](/apps/connect-ai/other-assistants/)
3. [Try it out](/apps/connect-ai/try-it-out/): check it's connected and give it a first task.

If something doesn't work, see [Troubleshooting](/apps/connect-ai/troubleshooting/).

## Before you start: stay safe

An assistant connected to a Craft app can open, change and save files, much as you can. A few habits keep that safe:

- Give it a folder of its own to work in, and keep copies of files you care about.
- Read what it's about to do when it asks for permission, before you say yes.
- Treat what's inside files, emails and web pages as information, not orders. A document can contain text written to trick an assistant.

Several apps can be limited to certain folders. Each app's **AI agents** page says how.
