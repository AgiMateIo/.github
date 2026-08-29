# AgiMate

**Agents you can trust with real credentials.**

Each agent reaches only the connectors and tools you granted it. Credentials stay in the platform and
never reach the model. Every rule is checked before the call leaves, and every call is written to a
log — allowed and denied alike.

Open source · self-hosted · your own server, your own keys — [agimate.io](https://agimate.io) · [Telegram](https://t.me/agimate)

---

## Least privilege, concretely

| | |
| --- | --- |
| **Credentials never reach the model** | Connector credentials are stored envelope-encrypted and decrypted only in the backend, at the moment of the call. Tools are executed by the platform, not by the agent loop — the process that talks to the model sends a tool name and its arguments, and gets a result back |
| **A matrix of agent × connector × tool** | An agent reaches a connector instance only through an explicit binding; inside a binding, per-tool and per-trigger rules deny what it should not have, down to a filter over the call's arguments |
| **Checked before the call, logged after** | The rule is evaluated in the backend before anything leaves for the external service, and the decision — with the agent, the tool and its arguments — is on the record either way |

The security model, down to the classes that implement it:
[agimate-backend/SECURITY.md](https://github.com/AgiMateIo/agimate-backend/blob/master/SECURITY.md).

## Repositories

| Repo | Stack | What it does |
| --- | --- | --- |
| [**agimate-backend**](https://github.com/AgiMateIo/agimate-backend) | Java 21 · Spring Boot | The core: agents, connectors, the access policy, credential storage, triggers and the agent loop |
| [**agimate-frontend**](https://github.com/AgiMateIo/agimate-frontend) | Next.js · TypeScript | Web dashboard: assemble agents, set their permissions, watch the logs |
| [**agimate-chat-android**](https://github.com/AgiMateIo/agimate-chat-android) | Kotlin · Compose | Chat client: your agents as a contact list, live conversations and push |
| [**connector-desktop**](https://github.com/AgiMateIo/connector-desktop) | Python | Companion connector for macOS, Windows and Linux: a fixed set of tools and triggers, in the system tray |
| [**connector-android**](https://github.com/AgiMateIo/connector-android) | Kotlin · Compose | Android companion connector: trigger monitoring and action execution over WebSocket |
| [**n8n-nodes-agimate**](https://github.com/AgiMateIo/n8n-nodes-agimate) | TypeScript | n8n community nodes for AgiMate connectors, devices and event triggers |

## How the pieces fit

The **backend** is the platform: it runs the agents, holds the credentials and owns the access policy.
The **frontend** is where you assemble agents and decide what each one may touch, and the **chat
client** is where you talk to them. **Skills** describe what an agent knows how to do. **Connectors**
give it tools, event triggers and background jobs — over MCP, over messengers, or through a
**companion connector** on a machine you control, which is the only way an agent touches that machine
at all. **n8n nodes** wire the whole thing into automations you already run.
