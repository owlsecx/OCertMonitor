# 🦉 OCertMonitor

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-OReconnaissance-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-3.0-cyan?style=flat-square"/>
</p>

> **OCertMonitor** — Certificate Transparency Monitor ║

---

> ⚠️ **AUTHORISED USE ONLY** — Use only on systems you own or have explicit written permission to test. Unauthorised use is illegal.

---

## 📌 Overview

OCertMonitor watches Certificate Transparency logs for suspicious SSL/TLS certificates issued for your brands and domains. It queries crt.sh with Cert Spotter and Facebook CT fallbacks, detects typosquatting and IDN/punycode look-alikes, and assigns a 0–100 threat score with risk classification. It can run one-shot scans or continuous monitoring with email/webhook notifications and HTML/CSV/JSON export.

---

## ✨ Features

- CT log monitoring via crt.sh with Cert Spotter and Facebook CT fallbacks
- Typosquatting detection and IDN/punycode look-alike alerts
- Threat scoring (0–100) with risk classification
- One-shot scan and continuous monitor mode with cron-style intervals
- Live TLS endpoint checks (expiry, chain, SANs)
- Email/webhook notifications and HTML/CSV/JSON export

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./OCertMonitor --scan example.com
./OCertMonitor --check example.com:443
./OCertMonitor --monitor --interval 3600 --export json
./OCertMonitor --help
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
