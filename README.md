# SkyDrop (Desktop Releases)

SkyDrop is a high-speed, local peer-to-peer file drop and device sync application for Linux and Windows. It helps you discover nearby devices on the same local network and send or receive files quickly, with a background daemon handling transfers and updates.

## About this repository

This repository hosts **compiled desktop releases of SkyDrop only**. It contains no source code; the source code is maintained in a private repository. Releases are published here so the desktop app’s built-in updater can check for, verify, and download updates.

## Download

Get the latest desktop packages from the [Releases](../../releases) page of this repository and choose the asset for your system:

- **`.exe` (Windows)** — 64-bit NSIS installer for Windows 10/11.
- **`.deb` (Linux)** — Debian/Ubuntu package for systems that use `dpkg`/APT.
- **`.AppImage` (Linux)** — portable standalone binary that runs on most Linux distributions.

Every release includes `SHA256SUMS.txt` containing SHA-256 hashes to verify package authenticity (see [Verifying downloads](#verifying-downloads)).

## Installation

### Windows (`.exe`)

1. Download the `SkyDrop Setup *.exe` file from the Releases page.
2. Run the installer and follow the setup wizard.
3. Launch **SkyDrop** from your Start Menu or Desktop shortcut.

### Debian / Ubuntu (`.deb`)

1. Download the `skydrop-desktop_*_amd64.deb` file from the Releases page.
2. Install it using APT:

   ```bash
   sudo apt install ./skydrop-desktop_*_amd64.deb
   ```

   Alternatively:

   ```bash
   sudo dpkg -i skydrop-desktop_*_amd64.deb
   sudo apt-get install -f
   ```

3. Launch **SkyDrop** from your applications menu.

### Linux Standalone (`.AppImage`)

1. Download the `SkyDrop-*.AppImage` file from the Releases page.
2. Make it executable and run it:

   ```bash
   chmod +x SkyDrop-*.AppImage
   ./SkyDrop-*.AppImage
   ```

   You can also mark it executable from your file manager’s properties/permissions and launch it by double-clicking.

## Features

- **Nearby device discovery** with a customizable device name.
- **Send and receive files** over the local network.
- **Optional auto-accept** with one-time PIN pairing.
- **Thumbnail caching** for received media.
- **Themes:** light, dark, or follow system.
- **Start on login** option.
- **Automatic updates** delivered from this repository’s GitHub Releases.
- Runs as a desktop app with a **background daemon** (default receive destination: `~/Downloads/SkyDrop` on Linux).

## Updates

SkyDrop can check this repository’s latest release, compare versions, and download/install updates from **Settings** inside the app.

To update manually, download the latest release asset for your system from the [Releases](../../releases) page and install it using the steps above.

## Start on Login

To launch SkyDrop automatically when you sign in, open **Settings** in the app and enable **Start on Login**.

## Verifying downloads

Every release includes `SHA256SUMS.txt`. You can verify your downloaded binary against the published checksum:

```bash
# Verify all downloaded files in current directory
sha256sum -c SHA256SUMS.txt

# Or check individually:
sha256sum SkyDrop-*.AppImage
sha256sum skydrop-desktop_*_amd64.deb
```

## Troubleshooting

- **App does not start**
  - On Linux: Try launching from a terminal to see any error output (`./SkyDrop-*.AppImage`). Ensure the file is marked executable (`chmod +x`).
  - On Windows: Ensure the app is not blocked by Windows Defender SmartScreen (click "More info" -> "Run anyway" if untrusted certificate prompt appears).
  - Re-download the asset and verify against `SHA256SUMS.txt` to rule out incomplete downloads.

- **Devices do not appear on the network**
  - Confirm both devices are connected to the **same local network / subnet**.
  - Check firewall settings: ensure local mDNS (port 5353/UDP) and SkyDrop transfer ports are permitted.
  - Ensure the background daemon is running.

- **Updater fails**
  - Check your internet connection and ability to reach GitHub API.
  - Try updating manually by downloading the latest release from the Releases page.
  - If the issue persists, note the app version shown in **Settings** and any error message, then retry after a newer release is published.

## Versioning

Releases use version tags in the form `v1.0.0` that match the version shown in the app’s **Settings**.
