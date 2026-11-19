---
title: "Step 2: Cursor"
description: Connect a Craft app to the Cursor code editor.
sidebar:
  order: 6
  label: "2. Cursor"
---

Cursor keeps its MCP servers in a file called `mcp.json`.

## 1. Open the settings file

1. In Cursor, open **Cursor Settings** with the gear icon at the top right.
2. Choose the MCP section, then **Add new MCP server**. Cursor opens `mcp.json`.

You can also open the file yourself. It's in the `.cursor` folder in your home folder: `C:\Users\<you>\.cursor\mcp.json` on Windows, or `~/.cursor/mcp.json` on macOS and Linux. Create it if it isn't there.

## 2. Add your Craft app

If the file already lists other servers, keep them: add yours inside the same `mcpServers` section, with a comma between each. The [Claude desktop app page](/apps/connect-ai/claude-desktop/#if-the-file-already-has-settings) has an example.

If the file is empty, replace everything in it with this, using your own full path from [Step 1](/apps/connect-ai/find-your-app/):

```json
{
  "mcpServers": {
    "wordcraft": {
      "type": "stdio",
      "command": "C:\\Users\\sam\\AppData\\Local\\Programs\\ArtCraft\\WordCraft\\wordcraft-cli.exe",
      "args": ["mcp"]
    }
  }
}
```

On Windows, double every backslash, as above. On macOS and Linux, the path looks like `"/Users/sam/Tools/wordcraft-cli"`.

Save the file.

## 3. Check it's connected

Back in **Cursor Settings**, your app is listed in the MCP section. A green dot means it's running. If the dot is red, see [Troubleshooting](/apps/connect-ai/troubleshooting/).

Cursor uses MCP tools in the chat's **Agent** mode.

Next: [Try it out](/apps/connect-ai/try-it-out/).
