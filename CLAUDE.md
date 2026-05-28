# CRA Risk Assessment Drafting Tool

## What This Is
An AI-powered web tool that helps cybersecurity consultants draft risk assessments for EU manufacturers complying with the **Cyber Resilience Act (Regulation EU 2024/2847)**.

## Who It's For
Cybersecurity consultants filling in assessments on behalf of manufacturer clients.

## Branding
**Jyohan Joglekar, Safety Consultant** — jyohannj@gmail.com

---

## Tech Stack
- `index.html` — single file, no framework, no build step
- `api/generate.js` — Vercel serverless function (hides Claude API key)
- Hosted on **Vercel**, connected to **GitHub** (auto-deploys on push)
- PDF export via browser print dialog

---

## What the Tool Does
1. Consultant fills in **40 questions across 10 sections** (grounded in Article 13(3) and Annex I)
2. Claude generates a structured 3-part risk assessment report
3. Report is exported via print-to-PDF

## Report Structure
- **Part 1** — Management Summary (plain English, traffic light dashboard, urgent actions)
- **Part 2** — Technical Assessment (asset register, STRIDE methodology, ISO 27005 scoring, information gaps)
- **Part 3** — Standard closing (supply chain note, disclaimer, consultant credentials)

---

## Demo Product
**SecureLock One** — a smart door lock with all 40 questions pre-filled, loads automatically on page load.

---

## Key Constraints to Remember
- Part 1 must be in **plain English** — no jargon (no OTA, RBAC, firmware, etc.)
- Residual risk is always a **sentence**, never a second number
- Dashboard traffic lights are generated **after** the full assessment, not before
- `max_tokens` is set to **8000** to avoid report cutoff

---

## Current Status
Core tool is built and deployed. Focus is on:
1. Reviewing and improving the tool
2. Validating with real cybersecurity consultants
3. Outreach to consultants and potential partners (e.g. CRACI)
