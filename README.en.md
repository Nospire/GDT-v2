# Geekcom Deck Tools

[Русская версия](README.md)

![GDT Preview](docs/preview.png)

Roskomnadzor has blocked Valve's servers — Steam Deck cannot update
SteamOS or download apps from Flatpak. GDT solves this automatically
through a temporary VPN tunnel.

[![Telegram News](https://img.shields.io/badge/Telegram-News-2CA5E0?style=flat&logo=telegram&logoColor=white)](https://t.me/geekcomdeck_news)
[![Telegram Games](https://img.shields.io/badge/Telegram-Games-2CA5E0?style=flat&logo=telegram&logoColor=white)](https://t.me/geekcom_deck_games)
[![Telegram Chat](https://img.shields.io/badge/Telegram-Chat-2CA5E0?style=flat&logo=telegram&logoColor=white)](https://t.me/Geekcom_hub)
[![Boosty](https://img.shields.io/badge/Boosty-Support-FF6A00?style=flat&logoColor=white)](https://boosty.to/steamdecks)

## Features

- 🔄 **SteamOS Update** — through a temporary VPN tunnel, automatically
- 📦 **Flatpak Update** — all apps at once, including system ones
- 🎬 **Fix OpenH264** — fixes the 403 error when installing the codec via Flatpak
- 🔒 **Proxy** — persistent proxy through Geekcom servers for Boosty subscribers
- 📊 **System Monitor** — SteamOS version, update branch, OpenH264 status, pending Flatpak updates
- 🌙 **Two themes** — dark and light
- 🏠 **Geekcom Inn** — SSH tavern to chat with other users

> All network operations are performed through a temporary encrypted tunnel.
> After completion the tunnel closes automatically.

## Installation

> [!IMPORTANT]
> GDT only works in **Desktop Mode** on Steam Deck.
> To update SteamOS from TTY use [NGDT](https://github.com/Nospire/NGDT).

### Requirements

- Steam Deck with SteamOS 3.x
- Desktop Mode
- Password for user `deck`

> [!NOTE]
> GDT uses the sudo password for system operations: installing updates,
> modifying system files, and managing Flatpak. The password is stored only
> in application memory and is never written to disk.
>
> If no password is set — the install script will offer to create one.
> You can also set it manually:
> ```bash
> passwd
> ```

### Install

Open Konsole and run:

```bash
curl -fsSL https://gdt.geekcom.org/gdt | bash
```

The script will automatically:
- check and install required dependencies
- download GDT and all modules
- create a desktop shortcut
- launch the application

### Update

To update to a new version run the same command — or click the version
number in the GDT interface when an update notification appears.

### Uninstall

```bash
rm -rf ~/.scripts/geekcom-deck-tools
rm -f ~/.local/share/applications/gdt.desktop
rm -f ~/Desktop/gdt.desktop
rm -rf ~/.config/gdt
```

## How it works

```
You press a button in GDT
        ↓
GDT requests a temporary tunnel from the Geekcom server
        ↓
An encrypted VLESS tunnel is established
        ↓
System proxy is set automatically
        ↓
The required action is performed (update, Flatpak, etc.)
        ↓
The tunnel closes automatically
```

All operations requiring network access (SteamOS update, Flatpak, Fix OpenH264)
are routed through the tunnel — Roskomnadzor is not a problem.

Proxy mode works differently: the tunnel stays active while GDT is open,
allowing you to use blocked services in the browser and other apps.
Available to [Boosty](https://boosty.to/steamdecks) subscribers.

## Community

Have questions, found a bug, or just want to chat with other Steam Deck owners?
You are welcome:

| | |
|---|---|
| 📢 News | [@geekcomdeck_news](https://t.me/geekcomdeck_news) |
| 🎮 Games | [@geekcom_deck_games](https://t.me/geekcom_deck_games) |
| 💬 Chat | [@Geekcom_hub](https://t.me/Geekcom_hub) |

## Support the project

GDT is a free tool. Servers, domains and development time are paid out
of the author's own pocket. If GDT helped you — consider supporting the
project on Boosty:

[Boosty → boosty.to/steamdecks](https://boosty.to/steamdecks)

Boosty subscribers get access to **Proxy** — a permanent encrypted
tunnel through Geekcom servers.
