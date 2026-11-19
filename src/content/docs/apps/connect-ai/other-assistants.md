---
title: "Step 2: Other assistants"
description: Connect a Craft app to any assistant that supports MCP.
sidebar:
  order: 8
  label: "2. Other assistants"
---

Any assistant that supports **local** MCP servers, ones that run on your computer, can use a Craft app. Some assistants only connect to servers on the internet, such as ChatGPT on the web; they can't use a Craft app.

Look in its settings for **MCP**, **MCP servers**, **tools** or **connectors**, and add a server with these details:

| Setting | What to enter |
| --- | --- |
| Type or transport | **Local**, **stdio** or **command**. Not a URL, HTTP or SSE server |
| Name | Your app's name in lower case, such as `wordcraft` |
| Command | The full path from [Step 1](/apps/connect-ai/find-your-app/) |
| Arguments | The arguments from Step 1, such as `mcp`, one per line or field |

Many assistants use the same settings file layout as the Claude desktop app:

```json
{
  "mcpServers": {
    "wordcraft": {
      "command": "/Users/sam/Tools/wordcraft-cli",
      "args": ["mcp"]
    }
  }
}
```

The [Claude desktop app page](/apps/connect-ai/claude-desktop/#3-add-your-craft-app) explains each part.

## Models that run on your computer

Apps that run a model on your own computer, such as LM Studio, can also use MCP servers. Choose a model that supports **tool use** (sometimes called function calling); a model without it can't use the Craft app at all. Smaller models may struggle with long tasks.

Next: [Try it out](/apps/connect-ai/try-it-out/).
