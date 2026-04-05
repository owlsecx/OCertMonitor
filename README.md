# 🔍 OCertMonitor

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux%20%2F%20Windows-informational?style=flat-square&logo=linux&logoColor=white&color=0a0c10"/>
  <img src="https://img.shields.io/badge/Category-ORec%20%2F%20Brand%20Protection-cyan?style=flat-square"/>
  <img src="https://img.shields.io/badge/Dependencies-requests-yellow?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-Proprietary-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-v2.0-cyan?style=flat-square"/>
</p>

> **OCertMonitor** is a powerful Certificate Transparency (CT) log monitor that watches for new SSL/TLS certificates issued for your domains. It detects typosquatting, IDN homograph attacks, suspicious subdomains, and brand abuse, with alerts logged to both human-readable and JSONL formats.

**Ideal for brand protection, blue team monitoring, and detection of rogue certificates.**

---

## 📌 Overview

OCertMonitor continuously queries public CT logs (primarily crt.sh with Cert Spotter fallback) for new certificates matching your watched domains. It classifies each certificate as:

- **Legitimate** — Exact match or allowlisted
- **Subdomain** — Valid subdomain (review recommended)
- **Typosquatting** — Edit-distance similarity
- **IDN/Punycode** — Homograph risk
- **Unrelated/Spoof** — Potential brand abuse

It maintains a seen-cert database to avoid duplicate alerts and supports continuous live monitoring mode.

---

## 🖥️ Modules

| # | Module                | Description |
|---|-----------------------|-------------|
| **[1]** | **Single Scan**       | One-shot query for all watched domains |
| **[2]** | **Live Monitor**      | Continuous polling at configurable interval |
| **[3]** | **Manage Domains**    | Add / remove / clear watched domains |
| **[4]** | **DB Inspector**      | View seen-cert database statistics |
| **[5]** | **View Alerts**       | Show recent alerts from log |
| **[6]** | **Settings**          | Wildcard, fallback, similarity, allowlist, retention, etc. |

---

## 📊 Key Features

- **Dual CT Sources** — crt.sh (primary) + Cert Spotter (fallback)
- **Suspicion Classification** — Typosquatting, IDN/Punycode, Subdomain, Allowlist
- **Damerau-Levenshtein Similarity** — Smart typo detection
- **Allowlist Regex Support** — Whitelist known good patterns
- **Persistent Database** — `ocert_seen.json` with pruning
- **Dual Logging**:
  - Human-readable `ocert_alerts.log`
  - Structured `ocert_alerts.jsonl`
- **Live Monitor Mode** — Background polling with graceful Ctrl+C handling
- **Clean Terminal UI** — Colored output with spinner and clear sections

---

## ⚙️ Requirements

- **requests**:
  ```bash
  pip install requests
  chmod +x OCertMonitor

  📁 Output

Live Terminal — Real-time colored alerts with classification
Alert Log — ocert_alerts.log (human-readable)
Structured Log — ocert_alerts.jsonl (machine-readable)
Seen Database — ocert_seen.json (deduplication + pruning)

Each alert includes:

Domain & base domain
Suspicion label
Issuer, NotBefore, entry URL
Timestamp


📦 Part of OwlSec Toolkit
This tool is part of the OwlSec suite — a collection of 300+ security and privacy tools.
🔗 owlsec.org

©️ License
Proprietary — © Khaled S. Haddad
Tools are distributed as pre-built executables. Source code is proprietary.
AUTHORISED BRAND PROTECTION & CERTIFICATE TRANSPARENCY MONITORING USE ONLY
