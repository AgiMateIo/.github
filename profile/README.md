# AgiMate

**Your AI assistant — a team, not a lone agent.**

Specialized agents work together instead of one do-everything assistant. They share a common
set of skills, connectors and devices, and they run on your own server, on your own keys.

Open source · self-hosted · no subscription — [agimate.io](https://agimate.io) · [Telegram](https://t.me/agimate)

---

## Open source

| Repo | Stack | What it does |
| --- | --- | --- |
| [**agimate-backend**](https://github.com/AgiMateIo/agimate-backend) | Java · Spring Boot | The platform itself: agents, skills, connectors, channels, triggers and the agent loop |
| [**agimate-frontend**](https://github.com/AgiMateIo/agimate-frontend) | Next.js · TypeScript | Web dashboard: assemble agents, wire them to channels, watch them work |
| [**desktop**](https://github.com/AgiMateIo/desktop) | Python | Cross-platform tray agent: plugin triggers and tools on macOS, Windows and Linux |
| [**android**](https://github.com/AgiMateIo/android) | Kotlin · Compose | Companion agent: trigger monitoring and action execution over WebSocket |
| [**n8n-nodes-agimate**](https://github.com/AgiMateIo/n8n-nodes-agimate) | TypeScript | Community nodes for AgiMate connectors, devices and event triggers |

## How the pieces fit

The **backend** is the platform: it runs the agents and owns everything below. The **frontend**
is where you assemble them and watch them work. **Skills** describe what an agent knows how to
do. **Connectors** give it tools, event triggers and background jobs. **Devices** — the desktop
and Android agents above — carry it beyond the browser. **n8n nodes** wire all of it into
automations you already run.
