# SkyDrop (Desktop)

SkyDrop is a high-speed, local peer-to-peer file drop app for the Linux desktop. It helps you discover nearby devices on the same network and send or receive files quickly, with a background daemon handling transfers and updates.

## About this repository

This repository hosts **compiled desktop releases of SkyDrop only**. It contains no source code; the source code is not public. Releases are published here so the desktop app’s built-in updater can check for and download updates.

## Download

Get the latest desktop packages from the [Releases](../../releases) page of this repository and choose the asset for your system:

- **`.AppImage`** — portable package that runs on most Linux distributions.
- **`.deb`** — Debian/Ubuntu package for systems that use `dpkg`/APT.

Download the file that matches the format you prefer. If checksum files are attached to the release, download them as well to verify your download (see [Verifying downloads](#verifying-downloads)).

## Installation

### AppImage

1. Download the `SkyDrop-*.AppImage` file from the Releases page.
2. Make it executable and run it:

   ```bash
   chmod +x SkyDrop-*.AppImage
   ./SkyDrop-*.AppImage
   ```

   You can also mark it executable from your file manager’s properties/permissions and launch it by double-clicking.

### Debian/Ubuntu (`.deb`)

1. Download the `skydrop-desktop_*_amd64.deb` (or similarly named `.deb`) file from the Releases page.
2. Install it with:

   ```bash
   sudo apt install ./skydrop-desktop_*_amd64.deb
   ```

   Alternatively:

   ```bash
   sudo dpkg -i skydrop-desktop_*_amd64.deb
   sudo apt-get install -f
   ```

3. Launch **SkyDrop** from your applications menu.

> If the exact asset filename differs for a release, use the filename shown on the Releases page.

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

If a checksum file is published alongside a release asset, you can verify the integrity of your download. Download the checksum file from the same release and compare it with the asset, for example:

```bash
# Example (adjust filenames and algorithm to match the published checksum file)
sha256sum -c <TODO: confirm checksum filename>
# or compare manually:
sha256sum SkyDrop-*.AppImage
```

If no checksum file is attached to a release, treat verification as `<TODO: confirm whether checksums are published for releases>`.

## Troubleshooting

- **App does not start**
  - Try launching from a terminal to see any error output (for AppImage: `./SkyDrop-*.AppImage`).
  - Ensure the AppImage is marked executable (`chmod +x ...`).
  - Re-download the asset in case the download was incomplete or corrupted.

- **Devices do not appear on the network**
  - Confirm both devices are on the **same local network**.
  - Check firewall rules and allow SkyDrop/local network discovery and transfer traffic as required by your system. `<TODO: confirm specific ports/protocols if needed>`
  - Ensure the background service/daemon is running and discovery is enabled on both devices.

- **Updater fails**
  - Check your internet connection and ability to reach GitHub.
  - Try updating manually by downloading the latest release from the Releases page.
  - If the issue persists, note the app version shown in **Settings** and any error message, then retry after a newer release is published.

## Versioning

Releases use version tags in the form `v1.0.0` that match the version shown in the app’s **Settings**.
