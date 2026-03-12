# 🔍 System Log Analysis for Anomaly Detection
### *Analisi dei Log di Sistema per il Rilevamento delle Anomalie*

> **A structured methodology for analyzing system logs to identify errors, failures, and suspicious patterns**
> *Una metodologia strutturata per analizzare i log di sistema e identificare errori, guasti e pattern sospetti*

*By Michelle Andrade | Cybersecurity Analyst & Content Creator*

---

## 📌 About This Project | Informazioni sul Progetto

**EN:** This project demonstrates a structured approach to system log analysis for anomaly detection. It includes sample logs, analysis methodology, classification of common error patterns, and recommendations aligned with security best practices.

**IT:** Questo progetto dimostra un approccio strutturato all'analisi dei log di sistema per il rilevamento delle anomalie. Include log di esempio, metodologia di analisi, classificazione dei pattern di errore comuni e raccomandazioni allineate alle best practice di sicurezza.

---

## 🎯 Why Log Analysis Matters | Perché l'Analisi dei Log è Importante

**EN:**
System logs are the primary source of evidence in any security investigation. Without proper log analysis, organizations cannot detect failures early, investigate incidents, or demonstrate compliance with security frameworks.

**IT:**
I log di sistema sono la principale fonte di prove in qualsiasi indagine di sicurezza. Senza un'analisi adeguata dei log, le organizzazioni non possono rilevare i guasti in anticipo, investigare gli incidenti o dimostrare la conformità ai framework di sicurezza.

---

## 📁 Project Structure | Struttura del Progetto

```
system-log-analysis/
│
├── README.md                        ← You are here / Sei qui
├── sample-logs/
│   ├── system_errors.log            ← Sample system error logs
│   ├── auth_failures.log            ← Sample authentication failure logs
│   └── service_crashes.log          ← Sample service crash logs
├── analysis/
│   ├── methodology.md               ← Step-by-step analysis methodology
│   ├── error-classification.md      ← Classification of error types
│   └── findings-report.md           ← Sample findings report
└── references.md                    ← All sources
```

---

## 📊 Error Categories Analyzed | Categorie di Errori Analizzati

| Category | EN Description | IT Description | Severity |
|---|---|---|---|
| Authentication Failures | Repeated failed login attempts | Tentativi di accesso falliti ripetuti | 🔴 High |
| Service Crashes | Unexpected process terminations | Terminazioni impreviste dei processi | 🟠 Medium |
| Disk/Memory Errors | Hardware resource failures | Guasti alle risorse hardware | 🟠 Medium |
| Permission Errors | Unauthorized access attempts | Tentativi di accesso non autorizzati | 🔴 High |
| Network Timeouts | Connection failures and drops | Errori e interruzioni di connessione | 🟡 Low |
| Configuration Errors | Misconfigurations causing failures | Configurazioni errate che causano guasti | 🟠 Medium |

---

## 🔍 Key Findings | Risultati Principali

**EN:**
- Authentication failure spikes often precede unauthorized access — they should trigger immediate alerts
- Service crashes grouped within short time windows indicate systemic failures, not isolated events
- Permission errors on sensitive directories are the clearest signal of insider threat or compromised credentials
- Proper log retention (minimum 90 days) is required by ISO 27001 and NIST frameworks

**IT:**
- I picchi di errori di autenticazione spesso precedono accessi non autorizzati — dovrebbero attivare alert immediati
- I crash dei servizi raggruppati in brevi finestre temporali indicano guasti sistemici, non eventi isolati
- Gli errori di autorizzazione su directory sensibili sono il segnale più chiaro di minaccia interna o credenziali compromesse
- La conservazione adeguata dei log (minimo 90 giorni) è richiesta dai framework ISO 27001 e NIST

---

## 🛠️ Tools Referenced | Strumenti Utilizzati

| Tool | Purpose | Type |
|---|---|---|
| Linux `journalctl` | System log collection | Free / Open Source |
| `grep` / `awk` | Log filtering and parsing | Free / Open Source |
| Splunk Free | Log aggregation and search | Free tier available |
| Elastic Stack (ELK) | Log visualization | Free / Open Source |
| Wazuh | Security log monitoring | Free / Open Source |

---

## 📖 Related Projects | Progetti Correlati

- 🔐 [Project 1 — AI Security Tools Analysis](https://github.com/michellegandrade83/ai-security-tools-analysis)
- ✅ [Project 2 — AI Compliance Checklist](https://github.com/michellegandrade83/ai-compliance-checklist)
- 📝 [Medium — @michelle.g.andrade83](https://medium.com/@michelle.g.andrade83)

---

## 👩‍💻 About Me | Chi Sono

**EN:** Cybersecurity content creator and analyst with a background in data analysis, financial services, and account management. Open to opportunities in cybersecurity analysis and governance/compliance roles internationally.

**IT:** Content creator e analista di cybersecurity con esperienza in analisi dei dati, servizi finanziari e account management. Aperta a opportunità internazionali nei ruoli di analisi della sicurezza e governance/compliance.

- 📝 [Medium](https://medium.com/@michelle.g.andrade83)
- 💼 [LinkedIn](https://www.linkedin.com/in/michelle-andrade)
