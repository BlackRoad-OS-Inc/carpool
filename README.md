<!-- BlackRoad SEO Enhanced -->

# carpool

> Part of **[BlackRoad OS](https://blackroad.io)** — Sovereign Computing for Everyone

[![BlackRoad OS](https://img.shields.io/badge/BlackRoad-OS-ff1d6c?style=for-the-badge)](https://blackroad.io)
[![BlackRoad-OS-Inc](https://img.shields.io/badge/Org-BlackRoad-OS-Inc-2979ff?style=for-the-badge)](https://github.com/BlackRoad-OS-Inc)

**carpool** is part of the **BlackRoad OS** ecosystem — a sovereign, distributed operating system built on edge computing, local AI, and mesh networking by **BlackRoad OS, Inc.**

### BlackRoad Ecosystem
| Org | Focus |
|---|---|
| [BlackRoad OS](https://github.com/BlackRoad-OS) | Core platform |
| [BlackRoad OS, Inc.](https://github.com/BlackRoad-OS-Inc) | Corporate |
| [BlackRoad AI](https://github.com/BlackRoad-AI) | AI/ML |
| [BlackRoad Hardware](https://github.com/BlackRoad-Hardware) | Edge hardware |
| [BlackRoad Security](https://github.com/BlackRoad-Security) | Cybersecurity |
| [BlackRoad Quantum](https://github.com/BlackRoad-Quantum) | Quantum computing |
| [BlackRoad Agents](https://github.com/BlackRoad-Agents) | AI agents |
| [BlackRoad Network](https://github.com/BlackRoad-Network) | Mesh networking |

**Website**: [blackroad.io](https://blackroad.io) | **Chat**: [chat.blackroad.io](https://chat.blackroad.io) | **Search**: [search.blackroad.io](https://search.blackroad.io)

---


> CarPool — Sovereign messaging and pub/sub. BlackRoad fork of NATS. Real-time fleet communication.

Part of the [BlackRoad OS](https://blackroad.io) ecosystem — [BlackRoad-OS-Inc](https://github.com/BlackRoad-OS-Inc)

---

# CarPool — BlackRoad Road Fleet

> **Sovereign messaging and pub/sub.** Fork of [NATS](https://github.com/nats-io/nats-server).

---

**CarPool** is BlackRoad's sovereign fork of NATS — real-time messaging, pub/sub events, and inter-node communication across the entire fleet.

## What's Different

- **Fleet mesh** — 4/5 nodes connected via NATS cluster
- **Agent events** — deploy notifications, health alerts, task dispatch
- **BlackRoad topics** — `blackroad.deploy.*`, `blackroad.health.*`, `blackroad.agents.*`
- **RoundTrip integration** — agent chat events flow through NATS

## Deployment

```bash
# On Octavia (NATS hub)
nats-server -c /etc/nats/nats.conf
# Port: 4222 (client), 6222 (cluster), 8222 (monitoring)
```

## Fleet Topology

```
Octavia (:4222) ← hub
  ├── Alice (:4222)
  ├── Cecilia (:4222)
  ├── Lucidia (:4222)
  └── Gematria (:4222)
```

## Topics

| Topic Pattern | Purpose |
|--------------|---------|
| `blackroad.deploy.>` | Deployment events |
| `blackroad.health.>` | Node health checks |
| `blackroad.agents.>` | Agent communication |
| `blackroad.chat.>` | RoundTrip messages |
| `blackroad.memory.>` | Memory system events |

## Upstream

Forked from [nats-io/nats-server](https://github.com/nats-io/nats-server) (Apache 2.0 upstream).
All BlackRoad modifications are proprietary.

---

**BlackRoad OS, Inc.** — Pave Tomorrow.

*Proprietary. All rights reserved.*
