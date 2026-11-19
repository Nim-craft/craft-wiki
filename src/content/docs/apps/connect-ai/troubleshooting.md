---
title: Troubleshooting
description: Fix the common problems when connecting an AI assistant to a Craft app.
next: false
---

Work through these in order. Most problems are the path, the settings file, or not restarting the assistant.

## The assistant doesn't list the app

- **Restart the assistant fully.** For the Claude desktop app, quit it from the system tray or with **Cmd+Q**; closing the window isn't enough.
- **Check you edited the right file.** Open it from the assistant's own settings, as Step 2 shows, rather than looking for it yourself.
- **Check the file is valid.** One missing comma or quote stops every server in it from loading. Paste it into a JSON checker such as [jsonlint.com](https://jsonlint.com) to find the mistake.

## "Command not found", "ENOENT" or "spawn ... failed"

The assistant can't find the helper program.

- Use the **full path**, not just `wordcraft-cli`. [Step 1](/apps/connect-ai/find-your-app/#get-the-full-path) shows how to copy it.
- On Windows, the path ends in `.exe`.
- In a JSON file on Windows, double every backslash: `C:\\Users\\sam\\...`.
- Don't put `~` in a JSON file. Write the whole path, such as `/Users/sam/Tools/wordcraft-cli`.
- Run the [check in Step 1](/apps/connect-ai/find-your-app/#check-that-it-runs). If it fails there too, the path is wrong.

## The server starts, then stops straight away

- Check the arguments. Each one goes in its own quotes: `["mcp", "--root", "C:\\Users\\sam\\PDFs"]`, not `["mcp --root C:\\Users\\sam\\PDFs"]`.
- If the app needs a folder, check the folder exists.
- Make sure the helper is from the same version as the app. Update both if they differ.

To see the actual error, look at the assistant's logs. In the Claude desktop app, **Settings › Developer** shows the error, and **Open Logs Folder** has a log for each server.

## macOS won't open the helper

macOS may block a program downloaded from the internet the first time it runs, with a message that it can't be opened or checked.

1. Run the [check in Step 1](/apps/connect-ai/find-your-app/#check-that-it-runs) once, so macOS shows the message.
2. Open **System Settings › Privacy & Security**.
3. Scroll down. Next to the message about the helper, choose **Open Anyway**, and confirm.

Then restart your assistant.

## The assistant can't open or save files

Some apps only let the assistant use the folders you name, such as PdfCraft with `--root`, or PhotoCraft and TextureCraft with read and write folders. Check that:

- the folders in your settings are the ones you mean, written as full paths;
- the file you asked about is inside them.

On Linux, a Flatpak app can only see some of your folders. Its **AI agents** page explains.

## It worked yesterday and stopped

After updating a Craft app, update its helper too. On macOS it's a separate download; replace the old file with the new one in the same place, so the path in your settings still works.

## Still stuck?

Ask in the [ArtCraft Discord](https://discord.gg/artcraft). Say which app, which assistant and which operating system you use, and copy the error message. Remove any personal details from paths or logs first.
