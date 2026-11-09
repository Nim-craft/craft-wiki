---
title: Install and update
description: How to install and update MailCraft on Windows, macOS, Linux, FreeBSD and the web.
---

:::note[Third-Party Application]
MailCraft is independently distributed by UCS Care Group. ArtCraft Launcher does not distribute third-party applications.
:::

Every release is on the [MailCraft Releases page](https://github.com/UCS-Care-Group/mailcraft/releases/latest) with a `SHA256SUMS.txt` file to check your download against.

:::caution
MailCraft releases are not signed yet. Windows and macOS ask before running them.
:::

## Windows

Download the `.msi` installer or the portable `.zip` for your processor: x64, x86 or ARM64.

## macOS

Download the `.dmg` disk image. It is universal and runs on Apple silicon and Intel. Drag **MailCraft** into your Applications folder.

## Linux

Packages are available for x86_64 and aarch64: `.AppImage`, `.deb`, `.rpm`, `.flatpak` and `.tar.gz`. They need glibc 2.35 or later.

### Flatpak

```bash
flatpak install --user mailcraft-*.flatpak
flatpak run io.github.billsecond.mailcraft
```

### AppImage

```bash
chmod +x mailcraft-*-linux-x86_64.AppImage
./mailcraft-*-linux-x86_64.AppImage
```

## FreeBSD

Download the FreeBSD x86_64 tarball.

## Web

`mailcraft-web-*.zip` is a static site you can host yourself. The browser build runs MailCraft through WebAssembly, with three limits:

- It reaches only JMAP mail servers, read only for now. Use the desktop app for IMAP and SMTP.
- Your mailbox lives in the browser's storage.
- Saving downloads a file.

## Updating

MailCraft tells you when a new release is out, in **File › About** and the status bar. Download the new release from the Releases page and install it the same way.

## Building from source

MailCraft needs Rust 1.95 or later.

```bash
git clone https://github.com/UCS-Care-Group/mailcraft
cd mailcraft
cargo run --release -p mailcraft -- --sample
```
