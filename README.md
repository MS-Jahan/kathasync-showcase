# KathaSync — Showcase

> 🔒 **Source is private** (live commercial SaaS). Happy to walk through the architecture in an interview.

Bangla / English / Banglish **voice-to-text SaaS**: record or upload audio → LLM-assisted transcription plus smart notes, summaries, meeting minutes, action items, and translation. Credit billing with **bKash SMS verification**, phone OTP, admin console, and large-file **Meeting Mode** via R2/GCS + Cloud Run async jobs.

## Links

- **Live:** https://kathasync.com
- **This repo:** portfolio write-up only — no production source

## Role

**Founder / full-stack** — product, billing, async pipeline, and web client for the Bangladesh market.

## What it does

- Multilingual ASR-oriented workflow (Bangla, English, Banglish)
- LLM-assisted notes, summaries, meeting minutes, action items, translation
- Credit-based billing with bKash SMS verification + phone OTP
- Admin console for operations
- Meeting Mode for large files: object storage + Cloud Run async processing

## Tech stack

| Layer | Stack |
| :--- | :--- |
| Frontend | React 18, TypeScript, Vite, Tailwind |
| Backend / data | Supabase, Deno Edge Functions |
| Async / media | Cloudflare R2, GCS, Cloud Run |
| Payments | bKash SMS verification |

## Architecture (high level)

```mermaid
flowchart TB
  U[Web / mobile clients] --> API[Supabase + Edge Functions]
  API --> ASR[Transcription + LLM notes]
  API --> BILL[Credits + bKash / OTP]
  U -->|large Meeting Mode files| R2[R2 / GCS]
  R2 --> CR[Cloud Run async jobs]
  CR --> ASR
```

## Screenshots

<!-- Add product screenshots under docs/screenshots/ when available -->

## Source

Production source stays private (billing, abuse controls, and commercial IP). This showcase is the public story for recruiters.
