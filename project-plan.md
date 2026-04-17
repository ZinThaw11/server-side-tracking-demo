# Server-Side Tracking Demo — Project Plan

## Goal
Build a WordPress e-commerce test site to demonstrate server-side tracking skills.

---

## Site Structure

- Home page — simple landing with hero and product highlight
- Shop page — single fake product (e.g. a digital course or a T-shirt)
- Checkout page — WooCommerce fake checkout
- Order confirmation page — fires Purchase event

---

## WordPress Setup

### Hosting
- ~~Option A: InfinityFree~~
- ~~Option B: 000webhost~~
- ✅ Option C: Local install via LocalWP

### Theme
- ✅ Astra (free) — fast, lightweight, WooCommerce-ready

### Plugins Installed
| Plugin | Purpose | Status |
|---|---|---|
| WooCommerce | Fake e-commerce store | ✅ Done |
| GTM4WP | Inject GTM container into site | ✅ Done |
| Elementor | Page builder | ✅ Done |
| Astra Starter Templates | Quick page designs | ✅ Done |
| Pixel Your Site (free tier) | Meta Pixel + CAPI integration | ⏳ Phase 3 |

---

## Tracking Setup Checklist

### Phase 1 — Browser-Side (Standard)
- [x] Create GTM account + web container (`GTM-TWW6558P`)
- [x] Install GTM on WordPress via GTM4WP plugin
- [x] Add GA4 via GTM (`GA4 - Google Tag`, Measurement ID: `G-6XQR871RH8`)
- [x] Verify events firing in GTM Preview mode
- [x] Verify events in GA4 DebugView
- [ ] Add Meta Pixel via GTM — deferred to Phase 3
- [ ] Verify events in Meta Events Manager — deferred to Phase 3

### Phase 2 — Server-Side (Stape)
- [x] Create Stape account (free tier)
- [x] Set up GTM server container in Stape (`GTM-M82NVS2M`)
- [x] Connect web container to server container via `server_container_url`
- [x] Migrate GA4 tag to server-side (`GA4 - Server-Side`)
- [x] Verify server-side events in GTM server container preview
- [x] Verify events in GA4 DebugView
- [ ] Migrate Meta Pixel tag to server-side — Phase 3
- [ ] Configure Meta CAPI with event_id for deduplication — Phase 3
- [ ] Verify events in Meta Events Manager (server source) — Phase 3
- [ ] Check Event Match Quality score in Meta — Phase 3

### Phase 3 — Meta Pixel + CAPI
- [x] Set up Meta Pixel via GTM (`Meta Pixel - PageView`, Pixel ID: `967118215859697`)
- [x] Set up Meta CAPI via GTM server container (`Meta CAPI - PageView`)
- [x] Verified browser events in Meta Events Manager Test Events
- [x] Verified server events in Meta Events Manager Test Events
- [x] Confirmed both Browser and Server sources showing in Meta Events Manager
- [ ] Configure event deduplication (event_id) — coming next
- [ ] Block browser-side pixel with ad blocker — confirm server-side still fires
- [ ] Compare browser-only vs server-side event counts
- [ ] Check Event Match Quality score improvement in Meta

---

## Resources

- Stape free tier: https://stape.io
- GTM server-side docs: https://developers.google.com/tag-platform/tag-manager/server-side
- Meta CAPI docs: https://developers.facebook.com/docs/marketing-api/conversions-api
- LocalWP (local WordPress): https://localwp.com
- GTM4WP plugin: https://wordpress.org/plugins/duracelltomi-google-tag-manager
- Pixel Your Site plugin: https://wordpress.org/plugins/pixelyoursite
