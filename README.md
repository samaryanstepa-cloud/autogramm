# AUTOGRAMM
### If it's not logged — it didn't happen.

Motorsport verification platform. AI-powered Digital Twin for every machine. Verified lap times, authenticated builds, public leaderboard.

---

## What it is

Autogramm links hardware to track time. Every lap is verified by AI, every build is public. Pilots claim a handle, build their Digital Twin through a conversation with Otto (AI crew chief), upload telemetry — and their machine earns its rank.

No self-reported times. No unverified builds. The machine runs the leaderboard.

---

## Current State — MVP UI

`index.html` — single responsive file, mobile-first + desktop

### Screens
- **Landing** — emotional first touch, live leaderboard preview, single CTA
- **Otto Onboarding** — AI-powered Digital Audit (4 acts: Identity → Twin → Telemetry → Verified)
- **Dashboard** — pilot profile, lap analysis, garage, leaderboard, Otto agent

### Features
- **Otto** — Anthropic Claude-powered onboarding. Builds your Digital Twin through natural conversation. Detects language, assigns class, launches dashboard on completion.
- **Multi-car Garage** — horizontal swipe carousel. 4 car types: Track / Street / Heritage / Project. Each with type-specific detail sheet.
- **Heritage Passport** — authenticity tracking. Original vs replaced vs unknown parts. Per-component breakdown.
- **Share Card** — canvas-generated verified lap card. 3 formats: Story 9:16 / Square 1:1 / Card 4:5. Native Web Share API + download fallback.
- **Digital Twin** — real-time build via Otto chat. Chips appear as data is confirmed.
- **Leaderboard** — class-filtered, verified times only.

### Stack
- Vanilla HTML/CSS/JS — zero dependencies, zero build step
- Anthropic Claude API (`claude-sonnet-4-20250514`) for Otto
- Canvas 2D API for share card generation
- Web Share API for native mobile sharing
- CSS scroll-snap for garage carousel
- Responsive: mobile-first → desktop layout at 768px+

---

## Garage — Car Types

| Type | Logic | Key metric |
|------|-------|------------|
| **Track** | Telemetry + verified lap time + class ranking | Best lap |
| **Street** | Build documented, telemetry optional | Est. lap / mods |
| **Heritage** | No track. Authenticity passport, parts provenance | % original |
| **Project** | Under build / restoration. Stage tracker | Build % |

---

## Roadmap

### Phase 1 — MVP (now)
- [x] Mobile-first UI
- [x] Otto onboarding (Claude API)
- [x] Digital Twin builder
- [x] Multi-car garage with carousel
- [x] Heritage authenticity passport
- [x] Share card generation
- [ ] Real telemetry upload (RaceChrono .CSV / VBOX .VBO)
- [ ] Otto live in dashboard (API connected)
- [ ] Backend + auth

### Phase 2 — Platform
- [ ] Real telemetry parsing and lap verification
- [ ] Multi-track leaderboards
- [ ] Heritage ownership chain (centralized DB)
- [ ] Monetization: verification packages
- [ ] iOS/Android PWA

### Phase 3 — Protocol
- [ ] Blockchain Heritage passports (Polygon / Base)
- [ ] On-chain ownership transfer
- [ ] NFT authenticity certificates
- [ ] Third-party verifier API

---

## Otto — AI Crew Chief

Otto is the AI concierge and crew chief. Powered by Anthropic Claude.

**Onboarding:** 4-act Digital Audit — claims handle, collects machine DNA, assigns class (Stock / Club-Sport / GT / Pro), launches dashboard.

**In dashboard:** setup advice, tire strategy, sector analysis, telemetry interpretation.

System prompt: `otto_system_prompt_v1.txt`

---

## Files

```
index.html                     — Single responsive file (mobile + desktop, Otto + Garage + Share Card)
otto_system_prompt_v1.txt      — Otto AI system prompt
README.md                      — This file
```

---

## Car Classes

| Class | Definition |
|-------|-----------|
| Stock | OEM spec. No ECU tune, stock suspension |
| Club-Sport | Mild mods. Aftermarket suspension, minor tune |
| GT | Full track prep. Coilovers, brake upgrade, ECU |
| Pro | Race-spec. Cage, slicks, standalone ECU |
| Heritage | Pre-1995 collector cars. Authenticity-rated |

---

*Autogramm — Leave Your Trace*
