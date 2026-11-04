# Case study — Rastahunden, Sveriges hundvänliga karta

How [Rastahunden](https://rastahunden.com) — Sweden's most complete dog-friendly map — was built and is operated by [Christoffer](https://github.com/orangeelefant) at [Webraketen](https://webraketen.se).

> **Archived.** This case now lives in [case-studies/rasta-detailed](https://github.com/orangeelefant/case-studies/tree/main/rasta-detailed).

## Live numbers

- **596+ verified locations** across **116 cities**
- Top cities: Stockholm 135 · Malmö 61 · Göteborg 42 · Lund 33 · Uppsala 26 · Mölndal 18 · Gävle 14 · Solna 13 · Helsingborg 12 · Sollentuna 11
- Free for users — no ads, no paywall
- 38% reply rate on outreach to candidate cafés (April 2026 cohort)

## Categories

- 🐕 **Hundrastgårdar** (dog parks)
- 🌳 **Koppelfria zoner** (off-leash zones)
- 🌊 **Hundbad** (dog-friendly bathing spots)
- ☕ **Hundvänliga caféer** (dog-friendly cafés) — every entry owner-confirmed via single-question email outreach

## Stack

- **Next.js 16** App Router
- **Supabase** (Postgres + Auth + Realtime)
- **Mapbox GL JS** interactive map
- **Netlify** functions + scheduled outreach jobs
- **Resend** transactional outreach (HMAC-signed yes/no/unsub one-click links)
- **Claude Code** in the loop for outreach copy + data hygiene

## Schema essentials

- `locations` — name, kind (rastgard|cafe|hundbad|koppelfri), lat/lng, city, municipality
- `municipalities` — Bolagsverket-aligned reference data
- `business_outreach` — outreach state machine
- `businesses` + `business_listings` — partnership tier

## Outreach pipeline

1. Crawl candidate cafés/restaurants from OpenStreetMap + Google Places
2. Send single-question email ("Är hundar välkomna?") via Resend
3. HMAC-signed yes/no/unsubscribe one-click links → `/api/outreach/respond`
4. Resend webhook (signed) logs delivery state to `business_outreach` table

## Live URL

→ [rastahunden.com](https://rastahunden.com)
→ Press: hej@rastahunden.com

## Related

- **Builder:** [github.com/orangeelefant](https://github.com/orangeelefant)
- **Agency:** [webraketen.se](https://webraketen.se) · **Portfolio:** [github.com/orangeelefant/portfolio](https://github.com/orangeelefant/portfolio)
- **Companion case study (gist):** [Building a national directory with Next.js + Supabase](https://gist.github.com/orangeelefant/a37e7614bd3ac559e36c365e1ed72645)

---
**Webraketen on GitHub:** [Portfolio](https://github.com/orangeelefant/portfolio) · [Case studies](https://github.com/orangeelefant/case-studies) · [Blue Pencil](https://github.com/orangeelefant/bluepencil) · [webraketen.se](https://webraketen.se)
