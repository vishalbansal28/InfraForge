# 🏦 InfraForge — Real-Time Governance Dashboard
### SBIePay · Innovation Hackathon 2026

<p align="center">
  <img src="https://epay.sbi.bank.in/secure/images/logo.png" alt="SBIePay Logo" height="60"/>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Status-Live%20Prototype-brightgreen?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Node-Mumbai%20Production-blue?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Hackathon-2026-gold?style=for-the-badge&color=C8A951"/>
  <img src="https://img.shields.io/badge/Built%20with-HTML%20%7C%20JS%20%7C%20Chart.js-orange?style=for-the-badge"/>
</p>

---

## 📌 Problem Statement

SBIePay's Core Banking infrastructure relies on three separate systems — **Archer**, **PAM (Privileged Access Management)**, and **ITSAM** — for governance and compliance tracking. Currently, reconciliation between these systems is done **manually**, resulting in:

| Issue | Impact |
|-------|--------|
| ⏰ 14-day reporting latency | Delayed risk visibility |
| 👷 140+ man-hours/week | High operational overhead |
| 📋 Manual evidence tracking | Error-prone & audit-risky |
| 🔴 Siloed data across tools | No single source of truth |

---

## 💡 Solution — InfraForge

**InfraForge** is an automated governance engine that bridges the gap between Archer, PAM, and ITSAM by:

- 📥 **Auto-ingesting** daily Archer CSV dumps via IMAP scanning
- 🔁 **Reconciling** 4,201+ asset records against ITSAM and PAM in real time
- 🟢 **Resolving** evidence gaps and SIEM faults automatically
- 📊 **Presenting** a live Health Center dashboard for Mumbai's Core Banking node

> **Result:** Latency drops from `T + 14 days` → `T + 0 days`. Effort cut from `140 hrs/week` → `15 hrs/week`.

---

## 🖥️ Live Demo

The prototype is a fully interactive, single-file HTML dashboard. Open `infraforge_sbi.html` in any browser.

### How to Run the Simulation

```
1. Click "Step 1: Start Log Ingestion"
   → Scans Archer IMAP, finds Archer_Dump_SBIePay_2026_02_17.csv
   → Ingests 4,201 asset records

2. Click "Step 2: Reconcile with Archer"
   → Matches Archer assets to ITSAM database
   → Cross-references PAM privilege status with SIEM logs
   → Resolves all gaps — dashboard updates live
```

**Before reconciliation:**
- Status Score: `65%`
- Missing Evidence: `2`
- SIEM Faults: `12`
- Sync Latency: `T + 14d`

**After reconciliation:**
- Status Score: `100%` ✅
- Missing Evidence: `0` ✅
- SIEM Faults: `0` ✅
- Sync Latency: `T + 0d` ✅

---

## 📁 Repository Structure

```
InfraForge/
│
├── infraforge_sbi.html     # Main SBIePay-themed governance dashboard (standalone)
├── README.md               # This file
```

> The entire prototype runs as a **single HTML file** — no build step, no dependencies, no server required.

---

## 🛠️ Tech Stack

| Technology | Usage |
|------------|-------|
| HTML5 / CSS3 | UI structure & SBI-branded styling |
| Vanilla JavaScript | Simulation engine & state management |
| Chart.js | Impact metrics visualisation |
| Google Fonts (Noto Serif + Source Sans 3) | SBI-style typography |
| SBIePay Design System | Navy `#003366`, Gold `#C8A951`, institutional layout |

---

## 📊 Impact Metrics

```
Weekly Effort Reduction
  Before (Manual):   ████████████████████  140 hrs/week
  After (InfraForge): █                     15 hrs/week
                                            89% reduction ✅

Reporting Latency
  Week 1:  ████████████████  14 days (baseline)
  Week 2:  █                  1 day
  Week 3:  ▌                  0.5 days
  Week 4:  ▎                  0.2 days  → Near real-time ✅
```

---

## 🏗️ Architecture Overview

```
┌─────────────────────────────────────────────────────┐
│                  InfraForge Engine                   │
│                                                     │
│  ┌──────────┐    ┌───────────┐    ┌──────────────┐  │
│  │  Archer  │───▶│ Ingestion │───▶│ Reconciler   │  │
│  │  (IMAP)  │    │  Engine   │    │  (PAM+ITSAM) │  │
│  └──────────┘    └───────────┘    └──────┬───────┘  │
│                                          │           │
│                                          ▼           │
│                              ┌───────────────────┐   │
│                              │  Health Center    │   │
│                              │  Dashboard (Live) │   │
│                              └───────────────────┘   │
└─────────────────────────────────────────────────────┘

Assets Monitored:  CBS-PRIMARY-DB · MB-GATEWAY-01 · PAY-SWITCH-MUM-03
Node:              Mumbai Production (SBIePay Core Banking)
Systems Bridged:   Archer v6.11 · PAM · ITSAM
```

---

## 🔒 SBIePay Context

[SBIePay](https://www.sbiepay.sbi) is the Payment Aggregation platform of **State Bank of India** — India's largest bank. It is the only bank-owned payment aggregator in India, providing direct integration with 45+ banks, UPI, card networks (Visa, Mastercard, RuPay), and offline channels.

InfraForge targets the **internal governance and compliance** layer of SBIePay's infrastructure operations, specifically the Mumbai Production node managing core banking transactions.

---

## 🚀 Getting Started

```bash
# Clone the repository
git clone https://github.com/vishalbansal28/InfraForge.git

# Open in browser — no server needed!
cd InfraForge
open infraforge_sbi.html    # macOS
# or
start infraforge_sbi.html   # Windows
# or
xdg-open infraforge_sbi.html  # Linux
```

---

## 👨‍💻 Author

**Vishal Bansal**
Innovation Hackathon 2026 — SBIePay Infrastructure Governance Track

---

## 📄 Disclaimer

> This is a **prototype demonstration** built for the Innovation Hackathon 2026. It is not an official State Bank of India or SBIePay product. All data shown is simulated for demonstration purposes.

---

<p align="center">
  <strong>InfraForge · Bridging the Governance Gap · SBIePay · Mumbai Node</strong>
</p>
