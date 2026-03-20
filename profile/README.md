<div align="center">

# 🛡 EstWarden

**Open-source Baltic Security Intelligence**

[Live Dashboard](https://estwarden.eu) · [Collectors](https://github.com/Estwarden/collectors) · [Research](https://github.com/Estwarden/research) · [Integrations](https://github.com/Estwarden/integrations)

</div>

---

EstWarden is an automated OSINT platform monitoring security threats, disinformation campaigns, and influence operations targeting the Baltic states. It collects data from 20+ public sources, classifies narratives with LLMs, detects coordinated campaigns, and publishes a real-time threat dashboard.

### What we monitor

| Domain | Sources |
|--------|---------|
| **Military** | ADS-B flights, AIS vessels, NATO NOTAMs, satellite thermal anomalies |
| **Disinformation** | 54 RSS feeds (Baltic, Russian state, independent media), Telegram, YouTube |
| **Electronic warfare** | GPS jamming zones, airspace restrictions |
| **Geopolitical** | ACLED conflict events, GDELT military news, embassy advisories |
| **Economic** | Electricity prices, economic indicators |
| **Cyber** | Internet outage monitoring, CERT feeds |

### Composite Threat Index

All signals are fused into a daily **CTI score** (0–100):

```
GREEN  (0–24)   Normal baseline
YELLOW (25–49)  Elevated activity
ORANGE (50–74)  Significant concern
RED    (75–100) Critical threat
```

### Narrative taxonomy

Information operations are classified into five Baltic-targeted categories:

| Code | Narrative |
|------|-----------|
| N1 | Russophobia / Persecution |
| N2 | War Escalation Panic |
| N3 | Aid = Theft |
| N4 | Delegitimization |
| N5 | Isolation / Victimhood |

### Repositories

| Repo | Description |
|------|-------------|
| **[collectors](https://github.com/Estwarden/collectors)** | Data collection pipelines — 14 collectors, enrichment DAGs, Dagu workflows. MIT. |
| **[research](https://github.com/Estwarden/research)** | CTI methodology, threat index math, architecture docs. MIT. |
| **[integrations](https://github.com/Estwarden/integrations)** | MCP server, Home Assistant, Grafana dashboards, Telegram bot, CLI. MIT. |

### Public API

No key required. JSON responses.

```
GET /api/threat-index        — CTI score + level
GET /api/today               — daily report
GET /api/history?days=30     — threat trend
GET /api/influence/narratives — narrative activity
GET /api/influence/campaigns  — detected campaigns
GET /feed.xml                — RSS feed
```

Base URL: `https://estwarden.eu`

### Contribute

- **New collector** — write a Python/bash script that fetches from a public source, submit to [collectors](https://github.com/Estwarden/collectors)
- **Integration** — connect EstWarden to your tool, submit to [integrations](https://github.com/Estwarden/integrations)
- **Research** — improve CTI weighting, add notebooks, submit to [research](https://github.com/Estwarden/research)

Good first issues: add an RSS feed, write a collector for a source we don't cover, improve the narrative classifier, add country configs for Latvia/Lithuania.

---

<div align="center">

**[estwarden.eu](https://estwarden.eu)**

</div>
