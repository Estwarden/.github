<div align="center">

# 🛡 EstWarden

**Open-source Baltic Security Intelligence**

[Live Dashboard](https://estwarden.eu) · [Dataset](https://github.com/Estwarden/dataset) · [Collectors](https://github.com/Estwarden/collectors) · [Research](https://github.com/Estwarden/research) · [Integrations](https://github.com/Estwarden/integrations)

</div>

---

EstWarden is an automated OSINT platform monitoring security threats, disinformation, and influence operations targeting the Baltic states. It collects from 20+ public sources, classifies narratives with LLMs, detects coordinated campaigns, and publishes a real-time threat dashboard.

### Repositories

| Repo | Description |
|------|-------------|
| **[dataset](https://github.com/Estwarden/dataset)** | 27K+ OSINT signals from 20 sources — media, military, economic, maritime. Narrative tags, threat reports, campaigns. ODC-By. |
| **[collectors](https://github.com/Estwarden/collectors)** | Data collection pipelines — 14 collectors, Dagu DAGs, Python/Bash scripts. MIT. |
| **[research](https://github.com/Estwarden/research)** | CTI methodology, threat index math, autoresearch optimizer, Jupyter notebooks. MIT. |
| **[integrations](https://github.com/Estwarden/integrations)** | MCP server, Home Assistant, Grafana, Telegram bot, CLI, n8n workflows. MIT. |

### What we monitor

| Domain | Sources |
|--------|---------|
| **Military** | ADS-B flights, AIS vessels, FIRMS thermal, GPS jamming, satellite imagery, NOTAMs |
| **Disinformation** | 54 RSS feeds, Telegram channels, YouTube, GDELT news |
| **Economic** | Energy prices, sanctions entities, business registry |
| **Environmental** | Weather balloons, space weather, internet outages |

### Composite Threat Index

```
GREEN  (0–24)   Normal baseline
YELLOW (25–49)  Elevated activity
ORANGE (50–74)  Significant concern
RED    (75–100) Critical threat
```

### Narrative taxonomy

| Code | Narrative |
|------|-----------|
| N1 | Russophobia / Persecution |
| N2 | War Escalation Panic |
| N3 | Aid = Theft |
| N4 | Delegitimization |
| N5 | Isolation / Victimhood |

### Public API

No key required. JSON responses. Base: `https://estwarden.eu`

```
/api/threat-index         — CTI score + level
/api/today                — daily report
/api/history?days=30      — threat trend
/api/influence/narratives — narrative activity
/api/influence/campaigns  — detected campaigns
/feed.xml                 — RSS feed
```

### Contribute

- **[Dataset](https://github.com/Estwarden/dataset)** — use for research, model training, threat analysis
- **[Collectors](https://github.com/Estwarden/collectors)** — write a new data collector, submit a PR
- **[Research](https://github.com/Estwarden/research)** — improve CTI weights, add notebooks, run autoresearch
- **[Integrations](https://github.com/Estwarden/integrations)** — connect EstWarden to your tools

---

<div align="center">

**[estwarden.eu](https://estwarden.eu)**

</div>
