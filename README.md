# Phishing Analysis — Task Summary

**Task:** Analyze a suspicious email (CoinDesk / Ripple allocation mock) and determine whether it is phishing.

## Quick visual checks (do first — no clicking)
- Check **From** display vs actual domain (e.g. `CoinDesk <coindesk@mg.areafellowship.com>` — mismatch = suspicious).  
- Look for **too-good-to-be-true** offers, urgency, or generic greetings.  
- **Hover** links (do not click) — verify the shown URL/domain; demo links replaced with safe placeholders.

## Header checks (confirm with tools)
- Inspect `Received` chain and origin IP (trace hops).  
- Verify authentication: **SPF / DKIM / DMARC** status. Passing auth ≠ safe (ESP may be used).  
- Check **SCL / spam score** and `Message-ID` / `Return-Path` for odd hostnames.

## Verdict (example)
- If visible red flags + suspicious header signals (high SCL, unrelated sending domain) → **Likely phishing**.

## Safe handling
- Do **not** click links or open attachments.  
- Report to provider and analyze offline (MXToolbox, VirusTotal, urlscan) or in an isolated VM.
