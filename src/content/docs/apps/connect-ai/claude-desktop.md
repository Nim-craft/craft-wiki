---
title: "Step 2: Claude desktop app"
description: Connect a Craft app to the Claude desktop app on Windows or macOS, step by step.
sidebar:
  order: 3
  label: "2. Claude desktop app"
---

The Claude desktop app runs on Windows and macOS. You add a Craft app by editing a small settings file. You'll need the full path from [Step 1](/apps/connect-ai/find-your-app/).

## 1. Install Claude and sign in

Download the desktop app from [claude.ai/download](https://claude.ai/download), install it, and sign in.

## 2. Open the settings file

1. In Claude, open **Settings**. On Windows it's in the menu at the top left; on macOS, choose **Claude › Settings** in the menu bar.
2. Choose **Developer**, then **Edit Config**.
3. A folder opens with a file called `claude_desktop_config.json` selected. Open it in a plain text editor: **Notepad** on Windows, or **TextEdit** on macOS.

If the file is empty or has only `{}` in it, go on to the next step. If it already has text in it, see [If the file already has settings](#if-the-file-already-has-settings) first.

## 3. Add your Craft app

Replace everything in the file with this, using your own full path from Step 1.

On Windows:

```json
{
  "mcpServers": {
    "wordcraft": {
      "command": "C:\\Users\\sam\\AppData\\Local\\Programs\\ArtCraft\\WordCraft\\wordcraft-cli.exe",
      "args": ["mcp"]
    }
  }
}
```

On macOS:

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

Check three things:

- **The name**, `"wordcraft"`, is just a label. Use your app's name in lower case.
- **On Windows, every backslash is doubled**: `C:\\Users\\...`, not `C:\Users\...`. A single backslash breaks the file.
- **Each argument is in its own quotes**, separated by commas. For an app that needs a folder, such as PdfCraft, it looks like this: `"args": ["mcp", "--root", "C:\\Users\\sam\\Documents\\PDFs"]`.

Save the file.

## 4. Restart Claude

Closing the window isn't enough, because Claude keeps running in the background.

- **Windows**: right-click the Claude icon in the system tray, by the clock, and choose **Quit**. You may need to click the **^** arrow to see it.
- **macOS**: choose **Claude › Quit Claude**, or press **Cmd+Q**.

Then open Claude again.

## 5. Check it's connected

Open **Settings › Developer** again. Your app should be listed with the status **running**. If it shows an error instead, see [Troubleshooting](/apps/connect-ai/troubleshooting/).

In a new chat, open the tools menu below the message box. Your app should be listed there and switched on.

Next: [Try it out](/apps/connect-ai/try-it-out/).

## If the file already has settings

The file must contain one `mcpServers` section, with each app inside it, separated by commas. For two Craft apps, it looks like this:

```json
{
  "mcpServers": {
    "wordcraft": {
      "command": "C:\\Users\\sam\\AppData\\Local\\Programs\\ArtCraft\\WordCraft\\wordcraft-cli.exe",
      "args": ["mcp"]
    },
    "gridcraft": {
      "command": "C:\\Users\\sam\\AppData\\Local\\Programs\\ArtCraft\\GridCraft\\gridcraft-cli.exe",
      "args": ["mcp"]
    }
  }
}
```

Note the comma after the closing `}` of the first app, and no comma after the last one. If the file has other settings outside `mcpServers`, keep them, and put a comma between each section.

If you're not sure the file is right, paste it into a JSON checker such as [jsonlint.com](https://jsonlint.com) before saving. Leave out anything private first.
