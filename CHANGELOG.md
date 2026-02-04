# HavenShield Changelog

All notable changes to the HavenShield SOC project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),  
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [1.0.0] - 2026-02-
### Added
- **Core SOC architecture** with 4-layer defense-in-depth:
  - Detection layer: Wazuh Agent (host) + Suricata (network)
  - Analysis layer: Wazuh Manager with OpenSearch backend
  - Automation layer: Shuffle SOAR with VirusTotal enrichment
  - Investigation layer: TheHive case management with Cortex analyzers
- **Fully automated deployment**:
  - Role-based installation scripts (`siem/`, `soar/`, `case/`, `vuln/`)
  - Single-command deployment per VM with hardware auto-detection
  - Cassandra stability patches for TheHive on resource-constrained systems
- **Secure integration pipeline**:
  - HTTPS-enforced webhooks between Wazuh → Shuffle
  - Python integration script with retry logic and logging
  - Whitelist-aware automation to prevent false positive blocking
- **Documentation suite**:
  - Architecture diagrams with data flow visualization
  - Troubleshooting guide for common home lab issues (Cassandra crashes, Suricata interface config)
  - Hardware requirements matrix with minimum/recommended specs


### Security
- All secrets excluded via `.gitignore` (no hardcoded credentials in repo)
- Webhook integration uses HTTPS by default (self-signed cert acceptable for home lab with documented tradeoffs)
- Default passwords must be changed on first login (enforced by all components)

---

## Why This Changelog Matters

This document demonstrates **engineering maturity** beyond simple tool installation:

✅ **Version discipline** – Shows iterative development process  
✅ **Problem-aware fixes** – Documents *why* changes were made (not just what)  
✅ **Security transparency** – Explicitly calls out tradeoffs and mitigations  
✅ **Roadmap thinking** – Planned releases show understanding of SOC evolution  

> *"A changelog isn't just a history log — it's proof you think like an engineer, not a button-clicker."*