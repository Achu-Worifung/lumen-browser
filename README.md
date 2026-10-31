# Lumen browser

The browser Lumen uses to put live web pages on its screens: Chromium,
through the [Chromium Embedded Framework](https://github.com/chromiumembedded/cef)
(CEF), with Lumen's small helper program that draws pages off-screen and
hands their frames to Lumen.

**You don't need to download anything here.** Lumen fetches the right file
itself: open **Settings → Browser** and press **Download**.

## What's here

Each [release](../../releases) is one browser version, with one zip per kind
of computer:

| Computer | File |
|---|---|
| Windows 10 or later, 64-bit (Intel or AMD) | `<version>-windows-x86_64.zip` |
| macOS, Linux | Not yet. Lumen says "Not available for this computer yet". |

A zip holds the helper (`lumen-web-cef.exe` and `.dll`), CEF's runtime
files, `lumen-web-runtime.json` (the version and the helper's name) and the
licences.

## How Lumen checks the download

Each Lumen release has the address, exact size and SHA-256 of every file
here built in. A download that doesn't match is deleted before anything is
unpacked. The zip is unpacked into a staging folder with every path checked
(no links, no `..`, size limits) and only used once it's complete.

So a file here is **never replaced**: copies of Lumen already out there
check the old one. A changed browser is published under a new version.

## How a release is made

An automated workflow in Lumen's repository makes every release:

1. builds the helper on Windows against CEF,
2. packages it with CEF's runtime,
3. installs the zip the way Lumen does and opens, navigates and resizes a
   real page from it,
4. uploads it here, downloads it back anonymously and checks its size and
   SHA-256,
5. prints the entry that the next Lumen release builds in.

## Licences

- **Chromium and CEF:** BSD-style licences. Each zip includes
  `LICENSE-CEF.txt` and Chromium's `CREDITS.html`, which lists every
  third-party component and its licence.
- **Lumen's helper (`lumen-web-cef`):** MIT or Apache-2.0, at your choice.
