---
title: "Step 1: Find your app's command"
description: Find the Craft app's helper program on Windows, macOS or Linux, and check that it runs.
sidebar:
  order: 2
  label: "1. Find your app's command"
---

Your assistant needs two things from you: the **command**, which is where the app's helper program is, and its **arguments**, the extra words that come after it. For almost every app, the only argument is `mcp`.

## Your app's command

Find your app in this table. Some apps need a folder as well; replace `<folder>` with the full path to a folder you choose, as shown in [Get the full path](#get-the-full-path).

- For MaterialCraft, PdfCraft, PhotoCraft and TextureCraft, the folders are a limit: the assistant can only use files inside them.
- For LightCraft, the folder is just the photos to start with. It doesn't limit where the assistant can save.

| App | Command | Arguments | More detail |
| --- | --- | --- | --- |
| AniCraft | `anicraft-cli` | `mcp` | [AI agents](/apps/anicraft/ai-agents/) |
| CADCraft | `cadcraft-cli` | `mcp` | [Automation](/apps/cadcraft/automation/#let-an-ai-agent-draw) |
| Craft Anything | `craft-anything-cli` | `mcp` | [Workflows](/apps/craft-anything/workflows/#from-an-ai-agent-mcp) |
| DeckCraft | `deckcraft-cli` | `mcp` | [AI agents](/apps/deckcraft/ai-agents/) |
| DesignCraft | `designcraft-cli` | `mcp` | [AI agents](/apps/designcraft/ai-agents/) |
| EffectCraft | `effectcraft-cli` | `mcp` | [AI agents](/apps/effectcraft/ai-agents/) |
| FigCraft | `figcraft-cli` | `mcp` | [AI agents](/apps/figcraft/ai-agents/) |
| FilmCraft | `filmcraft-cli` | `mcp` | [AI agents](/apps/filmcraft/ai-agents/) |
| GridCraft | `gridcraft-cli` | `mcp` | [AI agents](/apps/gridcraft/ai-agents/) |
| LightCraft | `lightcraft-cli` | `mcp` `<folder of photos>` | [AI agents](/apps/lightcraft/ai-agents/) |
| MailCraft | `mailcraft-cli` | `mcp` `--sample` to try it | [Workflows](/apps/mailcraft/workflows/#ai-agents-mcp) |
| MaterialCraft | `materialcraft-cli` | `mcp` `--read-root` `<folder>` `--write-root` `<folder>` | [Workflows](/apps/materialcraft/workflows/#use-it-with-an-ai-assistant) |
| PdfCraft | `pdfcraft-cli` | `mcp` `--root` `<folder>` | [AI agents](/apps/pdfcraft/ai-agents/) |
| PhotoCraft | `photocraft-cli` | `mcp` `--automation-read-root` `<folder>` `--automation-write-root` `<folder>` | [Automation](/apps/photocraft/automation/#connect-an-ai-assistant) |
| SolidCraft | `solidcraft-cli` | `mcp` | [Workflows](/apps/solidcraft/workflows/#automation-and-ai-agents-mcp) |
| SoundCraft | `soundcraft-cli` | `mcp` | [AI agents](/apps/soundcraft/ai-agents/) |
| TextureCraft | `texturecraft-cli` | `mcp` `--read-root` `<folder>` `--write-root` `<folder>` | [AI agents](/apps/texturecraft/ai-agents/) |
| VectorCraft | `vectorcraft-cli` | `mcp` | [AI agents](/apps/vectorcraft/ai-agents/) |
| WordCraft | `wordcraft-cli` | `mcp` | [AI agents](/apps/wordcraft/ai-agents/) |

Each word in the Arguments column is a separate argument. This guide uses WordCraft as its example; swap in your own app's command and arguments as you go.

## Find the helper program

Where it is depends on how you installed the app.

### Windows

The helper is next to the app itself, in its install folder. For the installer, that's usually:

```text
C:\Users\<you>\AppData\Local\Programs\ArtCraft\<App>\<app>-cli.exe
```

For example, `C:\Users\sam\AppData\Local\Programs\ArtCraft\WordCraft\wordcraft-cli.exe`. If you installed the app for everyone, look under `C:\Program Files\ArtCraft\` instead. For the portable zip, it's in the folder you unzipped.

### macOS

Most apps don't include the helper, so download it separately:

1. Open your app's release page on GitHub. Its **AI agents** page links to it.
2. Download the file named `<app>-cli-<version>-macos-universal.zip`. Use the same version as the app.
3. Double-click the zip to unzip it.
4. Move the `<app>-cli` file somewhere it can stay, such as a `Tools` folder in your home folder.

DesignCraft is the exception: its helper is inside the app, at `/Applications/DesignCraft.app/Contents/MacOS/designcraft-cli`.

### Linux

The `.deb` and `.rpm` packages, and most other packages, install the helper alongside the app, usually in `/usr/bin`. The app's **AI agents** page covers Flatpak and AppImage, which work differently.

## Get the full path

Assistant apps often can't find the helper by its name alone, so give them its **full path**: the complete address of the file, starting from the top of the drive.

- **Windows**: in File Explorer, find `<app>-cli.exe`, right-click it and choose **Copy as path**. On Windows 10, hold **Shift** while you right-click. The path is copied with quotes around it; leave the quotes off when you paste it into a settings file.
- **macOS**: in Finder, select the file, hold **Option** and right-click it, then choose **Copy "<app>-cli" as Pathname**.
- **Linux**: open a terminal and run `which wordcraft-cli`, with your app's name. It prints the full path.

Keep this path to hand for Step 2.

## Check that it runs

This step is optional, but it catches most problems early.

1. Open a terminal. On Windows, open the Start menu and type **PowerShell**. On macOS, open **Terminal** from **Applications › Utilities**.
2. Type the full path, a space, and `mcp`, then press **Enter**. On Windows, put `& ` before the path if you pasted it with quotes:

   ```powershell
   & "C:\Users\sam\AppData\Local\Programs\ArtCraft\WordCraft\wordcraft-cli.exe" mcp
   ```

   On macOS or Linux:

   ```bash
   ~/Tools/wordcraft-cli mcp
   ```

3. If nothing seems to happen and the cursor just waits, it's working: the helper is waiting for an assistant to talk to it. Press **Ctrl+C** to stop it.

If you see an error such as "not found", the path is wrong. If macOS says the file can't be opened, see [Troubleshooting](/apps/connect-ai/troubleshooting/#macos-wont-open-the-helper).

Next: add it to your assistant. Start with the [Claude desktop app](/apps/connect-ai/claude-desktop/) if you're not sure which to use.
