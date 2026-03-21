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
