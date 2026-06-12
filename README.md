# Marine HS Tariff Lookup — CBSA Customs Classification Engine

**AI-assisted HS code classification for marine and industrial spare parts.**

Single-file 846KB HTML application with 2,949 CBSA tariff entries, client-side TF-IDF keyword search, and DeepSeek API-powered classification reasoning. Built for professional customs brokers processing vessel spare parts through Canadian Customs.

## Live Demo

🔗 **Local:** http://localhost:8888/marine-hs-lookup.html

🔗 **[Launch HS Tariff Lookup](https://holy-salmon-ka4w.here.now/)**

## What It Does

A customs broker types "turbocharger for marine diesel engine" → the app:
1. Searches 2,949 CBSA tariff entries across 7 chapters (40, 73, 84, 85, 87, 89, 90)
2. Returns top 80 keyword matches scored by relevance
3. Sends top 30 matches + broker's question to DeepSeek API
4. AI returns recommended HS code(s) with classification reasoning
5. HS codes are clickable, linked to official CBSA chapter pages

Broker saves 10-15 minutes per classification. API cost: **$0.0006/lookup**.

## Features

- **Keyword search** — real-time client-side search across 2,949 descriptions
- **AI classification** — DeepSeek v4-flash for routine, v4-pro for complex queries
- **Expandable result cards** — HS code, MFN tariff rate, UOM, chapter, full description
- **Frequently Used Codes** — saved to localStorage, always ranked first
- **Duty Estimator** — enter value + origin country, calculates duty + GST + landed cost
- **Search history** — persistent with individual delete
- **Keyboard shortcuts** — `/` to focus search, `Esc` to close
- **Dark theme** — professional Bloomberg Terminal-inspired design
- **Zero server** — runs entirely in the browser, no backend needed

## Tech Stack

- Vanilla HTML/CSS/JS — single file, no framework, no build step
- CBSA T2026 tariff data — parsed from 7 official HTML chapter pages
- Client-side TF-IDF keyword scoring with code prefix boosting
- DeepSeek API (OpenAI-compatible REST endpoint)
- localStorage for API keys, search history, frequent codes
- Duty calculator: 6 Canadian trade agreements (MFN, US/CUSMA, UK, CPTPP, GPT, LDCT)

## Data

2,949 tariff entries extracted from CBSA Customs Tariff T2026 chapters:
- Chapter 40 — Rubber and articles thereof
- Chapter 73 — Articles of iron or steel
- Chapter 84 — Machinery and mechanical appliances
- Chapter 85 — Electrical machinery and equipment
- Chapter 87 — Vehicles other than railway
- Chapter 89 — Ships, boats and floating structures
- Chapter 90 — Optical, photographic, medical instruments

Each entry includes: HS code, statistical suffix, full description, unit of measure, MFN tariff rate.

## Benchmark

| Metric | Value |
|---|---|
| API cost per classification | $0.0006 (DeepSeek v4-flash) |
| Time saved per lookup | 10-15 minutes |
| Annual savings (100 lookups/month) | $10,000+ |
| Annual API cost (100 lookups/month) | $0.72 |

## Why This Exists

Customs brokers manually searched CBSA's paginated HTML tariff tables across multiple chapters. A single marine part could fall under Chapter 84 (machinery), Chapter 89 (vessel parts), or Chapter 73 (steel articles). The CBSA website has no semantic search. Wrong classifications cause rejected entries and Customs audits.

This tool gives brokers instant semantic search + AI reasoning over the complete tariff dataset.

## Author

**Rubin Varghese** — Senior Purchasing Manager, McKeil Marine Limited  
Founder, Artisa AI  
rubinagentagi@gmail.com

## License

MIT
