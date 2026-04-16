# Server-Side Tracking Demo — TrackLab Store

A portfolio project demonstrating server-side tracking implementation using Google Tag Manager, Stape, and GA4 on a WordPress/WooCommerce test site.

## What This Project Covers

- Setting up a GTM web container and server container
- Routing GA4 events through a Stape-hosted sGTM server
- Verifying the full data flow: browser → GTM → Stape → GA4

## Architecture

```
┌─────────────────────────────────────────────────────────┐
│                        Browser                          │
│   User visits TrackLab Store (WordPress/WooCommerce)    │
└───────────────────────┬─────────────────────────────────┘
                        │
                        ▼
┌─────────────────────────────────────────────────────────┐
│              GTM Web Container (GTM-TWW6558P)           │
│   GA4 Google Tag — sends to server_container_url        │
└───────────────────────┬─────────────────────────────────┘
                        │
                        ▼
┌─────────────────────────────────────────────────────────┐
│         Stape Server (degquixm.apn.stape.io)            │
│       GTM Server Container (GTM-M82NVS2M)               │
│   Receives request → fires GA4 server-side tag          │
└───────────────────────┬─────────────────────────────────┘
                        │
                        ▼
┌─────────────────────────────────────────────────────────┐
│                  Google Analytics 4                     │
│          Event received from server (POST 204)          │
└─────────────────────────────────────────────────────────┘
```

**Why this matters:** Ad blockers and iOS privacy restrictions can silently block browser-side pixels. Server-side tracking routes data through a server first — the request comes from your server, not the user's browser, so client-side blocking has no effect.

## Tech Stack

| Layer | Tool |
|---|---|
| CMS | WordPress (LocalWP) |
| Theme | Astra + Elementor |
| E-commerce | WooCommerce |
| Tag Management | Google Tag Manager |
| Server-Side Hosting | Stape (free tier) |
| Analytics | Google Analytics 4 |

## Repo Structure

```
├── gtm-exports/
│   ├── GTM-TWW6558P_v3.json   # Web container export
│   └── GTM-M82NVS2M_v2.json   # Server container export
├── screenshots/                # Proof screenshots
├── project-plan.md             # Project plan and checklist
├── server-side-tracking-briefing.html  # Visual setup guide
└── README.md
```

## GTM Container Exports

The `gtm-exports/` folder contains the exported configurations for both containers:

- **GTM-TWW6558P** (Web) — fires on all pages, routes GA4 data to the Stape server URL
- **GTM-M82NVS2M** (Server) — receives requests from the web container, forwards to GA4

## Project Status

- [x] Phase 1 — Browser-side GTM + GA4 setup
- [x] Phase 2 — Server-side via Stape (GTM server container + GA4)
- [ ] Phase 3 — Meta Pixel + CAPI (coming soon)
