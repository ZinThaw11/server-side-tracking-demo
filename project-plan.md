# Server-Side Tracking Demo — Project Plan

## Goal
Build a fake WordPress e-commerce site to demonstrate server-side tracking skills.
Used as proof of work for a LinkedIn case study post.

---

## Site Structure

- Home page — simple landing with hero and product highlight
- Shop page — single fake product (e.g. a digital course or a T-shirt)
- Checkout page — WooCommerce fake checkout
- Order confirmation page — fires Purchase event

---

## WordPress Setup

### Hosting
- Option A: InfinityFree (free, no credit card)
- Option B: 000webhost (free)
- Option C: Local install via LocalWP (best for testing, no hosting needed)

### Theme
- Astra (free) — fast, lightweight, WooCommerce-ready

### Plugins to Install
| Plugin | Purpose |
|---|---|
| WooCommerce | Fake e-commerce store |
| GTM4WP | Inject GTM container into site |
| Pixel Your Site (free tier) | Meta Pixel + CAPI integration |
| Astra Starter Templates | Quick page designs |

---

## Tracking Setup Checklist

### Phase 1 — Browser-Side (Standard)
- [ ] Create GTM account + web container
- [ ] Install GTM on WordPress via GTM4WP plugin
- [ ] Add Meta Pixel via GTM (PageView, AddToCart, Purchase triggers)
- [ ] Add GA4 via GTM (same events)
- [ ] Verify events firing in GTM Preview mode
- [ ] Verify events in Meta Events Manager
- [ ] Verify events in GA4 DebugView

### Phase 2 — Server-Side (Stape)
- [ ] Create Stape account (free tier)
- [ ] Set up GTM server container in Stape
- [ ] Connect web container to server container
- [ ] Migrate Meta Pixel tag to server-side
- [ ] Configure Meta CAPI with event_id for deduplication
- [ ] Migrate GA4 tag to server-side
- [ ] Verify server-side events in Stape logs
- [ ] Verify events in Meta Events Manager (server source)
- [ ] Check Event Match Quality score in Meta

### Phase 3 — Compare & Document
- [ ] Block browser-side pixel with an ad blocker
- [ ] Confirm server-side still fires
- [ ] Screenshot browser-only vs server-side event counts
- [ ] Screenshot Meta Event Match Quality score
- [ ] Screenshot GA4 real-time server events

---

## Screenshot Checklist (for LinkedIn post)

1. Meta Events Manager — showing both browser and server event sources
2. Event Match Quality score (before and after if possible)
3. GTM server container preview — showing events hitting the server
4. Stape dashboard — showing requests received
5. GA4 DebugView — showing server-side events

---

## LinkedIn Post Angle

**Hook:** Implemented server-side tracking on a test site. Here's what changed.

**Story:**
- Problem: browser-side pixels miss data (ad blockers, iOS, cookie limits)
- Action: set up GTM server container via Stape + Meta CAPI
- Result: events still fire even with ad blocker on, event match quality improved

---

## Resources

- Stape free tier: https://stape.io
- GTM server-side docs: https://developers.google.com/tag-platform/tag-manager/server-side
- Meta CAPI docs: https://developers.facebook.com/docs/marketing-api/conversions-api
- LocalWP (local WordPress): https://localwp.com
- GTM4WP plugin: https://wordpress.org/plugins/duracelltomi-google-tag-manager
- Pixel Your Site plugin: https://wordpress.org/plugins/pixelyoursite
