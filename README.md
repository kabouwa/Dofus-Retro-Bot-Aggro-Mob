# 🐉 Dofus Retro Bot — Aggro Mob

**A desktop app that automatically detects monster groups in Dofus Retro and engages them in combat, with a modern React control panel.**

Aggro Mob watches a Dofus Retro client's network traffic in real time, detects monster groups matching configurable rules (minimum count per monster type), and automatically moves the character to engage them. It supports multiple player instances simultaneously, each connecting either through a dedicated network interface or a proxy.

🔗 Repo: [github.com/kabouwa/Dofus-Retro-Bot-Aggro-Mob](https://github.com/kabouwa/Dofus-Retro-Bot-Aggro-Mob)

---

## ✨ Features

- **Multi-account** — manage several players at once, each with its own network interface or proxy
- **Real-time detection** — sniffs the game's network packets to spot monster groups as soon as they appear
- **Configurable aggro rules** — set a minimum count per monster type (Blue Jelly, Abraknyde, etc.) before the bot engages
- **Randomized attack delay** — adjustable interval (e.g. 0.30s–0.44s) to space out actions and avoid a mechanical pattern
- **Live logs** — real-time event stream (startup, per-player status, errors) shown directly in the interface
- **Light / dark theme**
- **Standalone desktop app** — no browser to open, everything is packaged into a native window

## 🛠️ Tech Stack

| Component | Role |
|---|---|
| **FastAPI** | Backend REST API — players, rules, delay, and bot control routes |
| **Scapy** | Packet sniffing — reads live game network traffic to detect mobs |
| **pywin32** | Simulates in-game clicks to attack detected groups |
| **Server-Sent Events (SSE)** | Live log stream from backend to the frontend |
| **React** | Control panel interface |
| **Tailwind CSS v4** | Styling, light/dark theming |
| **pywebview** | Wraps the whole app into a native desktop window |

## 📸 Screenshots

### Players — Retro accounts
Overview of managed accounts: name, network interface, host, status (active/inactive), and actions (edit, delete).

![Players](assets/screenshots/players-table.png)

### Add Player — Adding an account
Form to add a player: name, connection type (dedicated network interface or proxy with host/port), and active toggle.

![Add Player](assets/screenshots/add-player.png)

### Monster Rules — Aggro rules
Configure the minimum count required per monster type before the bot triggers an attack.

![Monster Rules](assets/screenshots/attack-mob-reqs.png)

### Attack Delay — Attack timing
Set the randomized interval between attacks using a dual slider.

![Attack Delay](assets/screenshots/attack-delay.png)

### Bot Control — Start / stop
Main control panel with bot status and a live log stream.

![Bot Control](assets/screenshots/bot-control.png)

### About — Project info
Overview page describing the tool, the tech stack used, and developer info.

![About](assets/screenshots/about.png)

## 📂 Project Structure

```
Dofus-Retro-Bot-Aggro-Mob/
├── backend/                 # FastAPI API (players, rules, delay, bot control)
├── frontend/                # React + Tailwind CSS v4 interface
├── assets/
│   └── screenshots/          # Screenshots used in this README
└── ...
```

## ⚠️ Disclaimer

This project automates in-game actions. Using automation tools may violate the game's terms of service and could result in account sanctions (including bans). This project is provided for educational purposes (networking, protocol reverse engineering, desktop automation) — use it at your own risk and with full awareness of the consequences.

## 👤 Developer

Built by **Kabouwa** — a self-directed developer studying software engineering, databases, and system design. Most of the real skill-building happens outside class — building bots, desktop automation tools, and full-stack projects independently across Python, PHP/Laravel, and JavaScript/React.
