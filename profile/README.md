<div align="center">

# 🛡 EstWarden

**Open-source Baltic Security Intelligence Platform**

[Dashboard](https://estwarden.eu) · [Collectors](https://github.com/Estwarden/collectors) · [Research](https://github.com/Estwarden/research)

</div>

---

EstWarden is an automated OSINT platform that monitors security threats, disinformation campaigns, and influence operations targeting the Baltic states. It collects data from 20+ public sources, classifies narratives using LLM models, detects coordinated campaigns, and presents everything on a real-time dashboard.

### 🔍 What we monitor

| Domain | Sources | What |
|--------|---------|------|
| **Military posture** | ADS-B, AIS, FIRMS, satellite | Aircraft, vessels, thermal anomalies at military bases |
| **Disinformation** | RSS (54 feeds), Telegram, YouTube | Russian-language media, state outlets, pro-Kremlin channels |
| **Electronic warfare** | GPSJam, NOTAM | GPS interference zones, airspace restrictions |
| **Geopolitical** | ACLED, GDELT, embassy advisories | Conflict events, military news, travel advisories |
| **Economic** | Elering, statistics offices | Energy prices, economic indicators |
| **Cyber** | IODA, CERT feeds | Internet outages, cyber incidents |

### 📊 Threat Assessment

Signals are fused into a **Composite Threat Index** (0-100) using weighted anomaly detection across all sources. The narrative classifier detects five categories of Baltic-targeted information operations:

| Code | Narrative |
|------|-----------|
| N1 | Russophobia / Persecution |
| N2 | War Escalation Panic |
| N3 | Aid = Theft |
| N4 | Delegitimization |
| N5 | Isolation / Victimhood |

### 🤝 Contribute

We welcome contributions to our open-source components:

- **[Estwarden/collectors](https://github.com/Estwarden/collectors)** — Data collection pipelines. Write a new collector script, submit a PR. No special access needed — collectors talk to the Data API, never to the database directly.

- **[Estwarden/research](https://github.com/Estwarden/research)** — CTI methodology, threat index mathematics, Jupyter notebooks. Help improve the analytical models.

**Good first contributions:**
- Add a new RSS feed to `config/feeds.yaml`
- Write a collector for a public data source we don't cover yet
- Improve the narrative classifier prompt
- Add country-specific configurations (Latvia, Lithuania, Finland)
- Write Jupyter notebooks for threat index calibration

### 🏗 Architecture

```
Public sources → Collector scripts → Data API → PostgreSQL → Dashboard
                    (Dagu DAGs)       (private)              (estwarden.eu)
```

Collectors are scheduled by [Dagu](https://github.com/dagu-org/dagu) (Go workflow engine). They fetch data from public APIs and submit signals through an authenticated Data API. The dashboard reads from the database and presents intelligence.

### 📄 License

All open-source components are MIT licensed.

---

<div align="center">

**[estwarden.eu](https://estwarden.eu)** — Real-time Baltic security intelligence

</div>
