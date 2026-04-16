# Server-Side Tracking Demo — TrackLab Store

A portfolio project demonstrating server-side tracking implementation using Google Tag Manager, Stape, and GA4.

## What This Project Covers

- Setting up a GTM web container and server container
- Routing GA4 events through a Stape-hosted sGTM server
- Verifying the full data flow: browser → GTM → Stape → GA4

## Tech Stack

| Layer | Tool |
|---|---|
| CMS | WordPress (LocalWP) |
| Theme | Astra + Elementor |
| E-commerce | WooCommerce |
| Tag Management | Google Tag Manager |
| Server-Side Hosting | Stape (free tier) |
| Analytics | Google Analytics 4 |

## Architecture

```
User visits site
  → Browser fires GTM web container (GTM-TWW6558P)
  → Web container sends data to Stape server (degquixm.apn.stape.io)
  → Stape server container (GTM-M82NVS2M) processes the request
  → Server forwards event to GA4
```

## Why Server-Side Tracking?

Browser-side pixels are vulnerable to ad blockers, iOS privacy restrictions, and cookie limitations. Server-side tracking routes data through a server first — making it resistant to client-side blocking and improving data accuracy.

## Project Files

- `project-plan.md` — Full project plan, plugin list, and tracking checklist
- `server-side-tracking-briefing.html` — Plain-English visual guide to the setup

## Status

- [x] Phase 1 — Browser-side GTM + GA4 setup
- [x] Phase 2 — Server-side via Stape
- [ ] Phase 3 — Meta Pixel + CAPI (coming soon)
