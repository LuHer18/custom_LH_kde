# KDE Plasma and OBS settings backup

This is a curated snapshot from Fedora KDE (Plasma 6.8.3), with Krohnkite 0.9.11.0 and OBS Studio installed as a Flatpak. It is a reference for recreating the setup, not a full home-directory backup or an automated restore.

| File | What it preserves |
| --- | --- |
| [`kde/kwinrc`](kde/kwinrc) | Virtual desktop count and rows, window decoration, and Krohnkite enablement, gaps and borders. KWin had no window rules to export. |
| [`kde/shortcuts.tsv`](kde/shortcuts.tsv) | Krohnkite bindings and selected custom KWin and Plasma shortcuts. `none` means disabled; ` \| ` separates alternative bindings. |
| [`kde/kdeglobals`](kde/kdeglobals) | Plasma look and feel, icon theme, color scheme and palette. |
| [`kde/panels/`](kde/panels/) | The two panels' placement, widget IDs and order, and selected panel and widget options. |
| [`assets/wallpaper.jpg`](assets/wallpaper.jpg) | The desktop wallpaper, with embedded metadata removed. |
| [`obs/recording/basic.ini`](obs/recording/basic.ini) | Selected recording profile options, including output mode, format, encoders, audio tracks, video size and frame rate. |

## Recreate the setup

1. Back up the destination's existing settings. Install the matching themes, widgets and Krohnkite separately; their packages are not included here.
2. Use **System Settings** to apply the KWin, appearance and shortcut values. Recreate the panels in **Plasma Edit Mode** on the desired screens and select `assets/wallpaper.jpg` in the desktop wallpaper settings. The numeric IDs in `kde/panels/` describe the source layout; do not overwrite live Plasma files with these excerpts.
3. In OBS, make a new profile, use `obs/recording/basic.ini` as a reference for **Settings → Output**, **Video** and **Audio**, and choose your own recording directory. Select an encoder available on the destination machine, then make a short test recording.

OBS scenes, streaming and service settings, plugin state, device identifiers, recording paths, and logs are not included. The KDE backup excludes monitor mappings, desktop and activity identifiers, original wallpaper paths, private launcher references, and arbitrary widget content. Reconfigure any omitted widget options manually.

## Use on Ubuntu

Use Kubuntu or an Ubuntu installation with **KDE Plasma 6**. The standard Ubuntu GNOME session does not use Plasma panels, KWin shortcuts, or Krohnkite. Install a Krohnkite release that supports your Plasma version, along with the themes and widgets in the snapshot. Recreate the panels and shortcuts manually; older Plasma releases or missing widgets may not reproduce them exactly.

The wallpaper and OBS recording settings can also be used on Ubuntu with GNOME. For OBS, use the profile values as a reference and select an encoder available on that computer.
