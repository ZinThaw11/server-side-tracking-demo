# Server-Side Tracking Demo — Progress Notes

## Project Goal
Build a fake WordPress e-commerce site to demonstrate server-side tracking skills.
Used as proof of work for a LinkedIn case study post.

---

## User Profile
- Comfortable with HTML/CSS/JS
- Python only for backend
- Has used GTM at work
- Wants to try Stape (free tier)
- Has both Meta Business and Google accounts

---

## Tech Stack Decided
| Layer | Tool |
|---|---|
| CMS | WordPress (via LocalWP) |
| Theme | Astra + Elementor |
| E-commerce | WooCommerce |
| GTM integration | GTM4WP plugin |
| Server-side tracking | Stape (free tier) |
| Analytics | GA4 |
| Ad tracking | Meta CAPI (pending) |

---

## Setup Progress

### LocalWP
- [x] Installed LocalWP on Mac
- [x] Created site: **TrackLab Store**
- [x] Environment: Preferred (Nginx + PHP 8.x)
- [x] Admin credentials saved
- [x] WordPress dashboard accessible

### WordPress Plugins & Theme
- [x] Astra theme installed + activated
- [x] WooCommerce installed + activated
- [x] GTM4WP installed + activated
- [x] Starter Templates plugin installed
- [x] Elementor chosen as page builder (user is familiar with it)
- [x] Site design completed with Elementor

### Products
- [x] First product created: **Premium Marketing Course**
  - Price: $49
  - Type: Simple product

### GTM Setup
- [x] GTM account created: **TrackLab Store**
- [x] Container ID: `GTM-TWW6558P`
- [x] GTM connected to WordPress via GTM4WP
- [x] GA4 Google Tag added in GTM (`GA4 - Google Tag`)
- [x] Container published (v1 - GA4 setup)
- [x] GA4 Realtime verified — showing active user

### GA4 Setup
- [x] GA4 property created: **TrackLab Store**
- [x] Measurement ID obtained (`G-XXXXXXXXXX` — user has this)
- [x] GA4 tag firing on All Pages confirmed in Realtime report

### Meta Pixel
- [ ] Not set up yet — deferred for later

### GTM — Server Container
- [x] Server container created: `GTM-M82NVS2M` (tracklab-store.local sGTM)
- [x] Tagging server URL set to Stape: `https://degquixm.apn.stape.io`
- [x] GA4 server-side tag created: `GA4 - Server-Side` (Measurement ID: `G-6XQR871RH8`)
- [x] Server container published (v1 - GA4 server-side tag)
- [x] Server container preview verified — `GA4 - Server-Side` fired

### GTM — Web Container Update
- [x] `server_container_url` parameter added to GA4 Google Tag → `https://degquixm.apn.stape.io`
- [x] Web container published (v2 - Server-side GA4 via Stape)

### Stape (Server-Side)
- [x] Stape account created (free tier)
- [x] sGTM container created: **TrackLab Store**
- [x] Server location: AP East (Singapore)
- [x] Container identifier: `degquixm`
- [x] Server URL: `https://degquixm.apn.stape.io`
- [x] 2 requests confirmed received (visible in Stape dashboard)

### GA4 Verification
- [x] DebugView confirmed `page_view` events arriving
- [x] Full flow verified: WordPress → GTM web → Stape → GA4

---

## Next Steps (in order)
1. ~~Finish site design with Elementor~~ ✓
2. ~~Create Stape account (free tier)~~ ✓
3. ~~Set up GTM server container in Stape~~ ✓
4. ~~Migrate GA4 tag to server-side~~ ✓
5. ~~Take screenshots for LinkedIn Post 1~~ ✓
6. Write LinkedIn Post 1
7. Set up Meta Pixel + CAPI (Post 2 — future)

---

## LinkedIn Post Plan

### Post 1 — GTM + Stape Setup (current focus)
**Angle:** I learned server-side tracking and built a test site to prove it. Here's the setup.

**Story:**
- What I built: GTM server container via Stape on a WordPress test site
- Proof: screenshots of GTM, Stape, and GA4 all working together
- Tease: "Next up — connecting Meta CAPI and measuring the data gap"

**Screenshots needed:**
1. GTM web container — tags configured
2. Stape dashboard — server container running
3. GTM server container preview — events flowing through
4. GA4 Realtime or DebugView — server-side events confirmed

### Post 2 — Meta CAPI + Data Gap (future)
- Set up Meta Pixel + CAPI
- Show before/after with ad blocker
- Event Match Quality score improvement

---

## Notes
- Site is local only (LocalWP) — no public URL needed, screenshots are sufficient
- LocalWP has a "Live Link" feature if public URL is needed later
- Stape free tier is sufficient for this demo
