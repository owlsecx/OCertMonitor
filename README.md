# 🦉 OCertMonitor

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-OReconnaissance-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-Proprietary-orange?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-3.0-cyan?style=flat-square"/>
</p>

> **OCertMonitor** — Certificate Transparency Monitor

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

This tool is part of the **OwlSec** suite — a collection of 275+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

Proprietary — © 2026 Owlsec LLC. All rights reserved.

*Tools are distributed as pre-built executables. Source code is proprietary.*

---

## 🔍 Verification & Transparency

This tool is closed-source. These files let you see exactly what is inside it,
without the source:

- [`SBOM.cdx.json`](SBOM.cdx.json) — CycloneDX inventory: SHA-256 of this
  binary, bundled CPython version, and every bundled library with its exact
  version and license. Feed it to Grype, Trivy or Dependency-Track to audit
  our dependencies for CVEs yourself.
- [`THIRD-PARTY-NOTICES.md`](THIRD-PARTY-NOTICES.md) — the full license text
  of every third-party component, extracted from this binary.

**No telemetry, no analytics, no licence check-in.** This tool does not phone
home. Verify that claim yourself:

```bash
sudo strace -f -e trace=network ./OCertMonitor --help   # watch every network call
firejail --net=none ./OCertMonitor --help               # deny the network entirely
```

Release signing, GPL compliance and vulnerability reporting:
[**TRUST.md**](https://github.com/owlsecx/owl-os/blob/main/TRUST.md)
