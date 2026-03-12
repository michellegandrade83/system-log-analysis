# Log Analysis Methodology | Metodologia di Analisi dei Log

## EN: Step-by-Step Approach | IT: Approccio Passo per Passo

---

## STEP 1 — Collect | Raccogliere

**EN:** Gather logs from all relevant sources before starting analysis. Never analyze logs in isolation.

**IT:** Raccogliere i log da tutte le fonti rilevanti prima di iniziare l'analisi. Non analizzare mai i log isolatamente.

| Log Source | Location (Linux) | Command |
|---|---|---|
| System logs | `/var/log/syslog` | `cat /var/log/syslog` |
| Authentication logs | `/var/log/auth.log` | `cat /var/log/auth.log` |
| Kernel logs | `/var/log/kern.log` | `cat /var/log/kern.log` |
| Application logs | `/var/log/[appname]/` | `journalctl -u servicename` |
| All systemd logs | systemd journal | `journalctl -xe` |

---

## STEP 2 — Filter | Filtrare

**EN:** Filter logs by severity level to focus on what matters most.

**IT:** Filtrare i log per livello di gravità per concentrarsi su ciò che è più importante.

```bash
# Show only ERROR and CRITICAL entries
grep -E "ERROR|CRITICAL" /var/log/syslog

# Show last 100 lines
tail -100 /var/log/syslog

# Show logs from a specific time window
journalctl --since "2024-11-01 00:00:00" --until "2024-11-01 23:59:59"

# Count errors by type
grep "ERROR" /var/log/syslog | awk '{print $5}' | sort | uniq -c | sort -rn
```

---

## STEP 3 — Classify | Classificare

**EN:** Group errors into categories to identify patterns.

**IT:** Raggruppare gli errori in categorie per identificare i pattern.

| Severity | Label | Action Required |
|---|---|---|
| 🔴 CRITICAL | System may be down | Immediate response |
| 🔴 ERROR | Function failed | Investigate within 1 hour |
| 🟠 WARNING | Something may go wrong | Investigate within 24 hours |
| 🟡 INFO | Normal operations | Log for audit trail |
| ⚪ DEBUG | Development details | No action needed |

---

## STEP 4 — Correlate | Correlare

**EN:** Look for relationships between events. A single error may be harmless; repeated errors in sequence tell a story.

**IT:** Cercare relazioni tra gli eventi. Un singolo errore può essere innocuo; errori ripetuti in sequenza raccontano una storia.

**Key correlation patterns to look for:**
- Same error repeating in short time window → systemic failure
- Authentication failures + service crash → possible attack followed by exploitation
- Disk errors + backup failures → data loss risk
- Permission errors on sensitive files → insider threat or compromised account

---

## STEP 5 — Report | Riportare

**EN:** Document findings clearly for both technical and non-technical stakeholders.

**IT:** Documentare i risultati in modo chiaro per le parti interessate tecniche e non tecniche.

A good findings report includes:
1. **Executive Summary** — what happened in plain language
2. **Timeline** — chronological sequence of events
3. **Root Cause** — what caused the issue
4. **Impact** — what was affected
5. **Recommendations** — what to fix and how

---

## STEP 6 — Retain | Conservare

**EN:** Define log retention policies aligned with compliance requirements.

**IT:** Definire le politiche di conservazione dei log allineate ai requisiti di conformità.

| Framework | Minimum Retention |
|---|---|
| ISO 27001 | Defined by organization's risk assessment |
| NIST AI RMF | Commensurate with risk level |
| EU AI Act (High Risk) | Minimum 6 months post-deployment |
| GDPR | Only as long as necessary |

**Recommended minimum: 90 days for security logs, 1 year for audit logs.**
