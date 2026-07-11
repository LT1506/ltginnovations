# LTG Innovations — "Selected Work" Showcase

**Date:** 2026-07-11
**Site:** `C:\Users\graysolt\ltg-innovations-site\` (vanilla HTML/CSS/JS, no build)
**Status:** Approved design, ready for implementation plan

## Purpose

Add a portfolio of LTG's client/business builds to the marketing site. Frames LTG
as "a software company that ships real products for real businesses," which also
strengthens the site's role as LTG's Stripe Connect business web presence.

Scope decisions already made with the user:
- **Which projects:** client/business work only — Chairtime, George + Gray, Tornatta
  Tire. No personal apps (RangeHUD, TrailCompass, AR Trainer), no internship/study work.
- **Placement:** "Both" — a compact highlights strip on the landing page plus a fuller
  dedicated `work.html` page.
- **Card style:** "Cards + live capture" — real screenshots where a site is live, a
  branded mock tile where it is not, so all three read as one consistent set.

## Surfaces

### 1. Landing page (`index.html`)
- New **"Selected work"** section inserted **after Features (`#features`) and before
  Pricing (`#pricing`)**.
- A 3-card strip (compact variant): thumbnail, project name, one-line role, 2–3 tech
  tags, and a link. Below the strip, a "See all work →" button linking to `work.html`.
- Add **"Work"** to the primary nav (header `.nav-menu`) and the footer nav.

### 2. Full page (`work.html`)
- Reuses the existing `<header>`, `<footer>`, `css/style.css`, `js/main.js`.
- Nav links point back to landing anchors (e.g. `index.html#product`); "Work" is the
  current page.
- Navy hero ("Work we've shipped" + one-line lead).
- 3 larger detail cards (bigger screenshot, longer blurb, full tag list, live-site link).
- Closes with a "Get a quote" CTA reusing the existing `.section-navy` contact pattern
  (or a link back to `index.html#contact`).

## The three projects

| Project | Role / framing | Tags | Link target |
|---|---|---|---|
| **Chairtime** | Flagship — all-in-one booking + in-person card payments for independent stylists and small salons | FastAPI · PostgreSQL · Stripe Terminal · Twilio · PWA | `index.html#product` (branded mock tile; frontend not yet deployed) |
| **George + Gray Co.** | Evansville clothing boutique — full e-commerce: Stripe Checkout + Connect payouts, inventory, admin panel, order-confirmation emails | FastAPI · PostgreSQL · Stripe · Railway | Live storefront `https://trustworthy-optimism-production-b60f.up.railway.app` (verify reachable before linking/capturing) |
| **Tornatta Tire** | Evansville family tire shop (since 1983) — "Heritage Garage" marketing site, all quotes via tap-to-call | Next.js · Tailwind · SEO · Railway | `https://www.tornattatires.com` |

Copy is written by LTG about client work ("We built…"), not first-person personal.

## Assets

- New folder `assets/img/`.
- **Tornatta:** headless-Chrome screenshot of `https://www.tornattatires.com`.
- **George + Gray:** headless-Chrome screenshot of the live Railway URL, **if reachable**;
  if it is down, fall back to a branded mock tile matching the Chairtime one.
- **Chairtime:** hand-built navy/gold SVG (or CSS) mock tile — no live frontend to capture.
- All captures at a consistent viewport and cropped/displayed at a consistent aspect
  ratio (target 16:10) so the three tiles look like one set.
- Images sized/compressed reasonably for web; include descriptive `alt` text.

## Styling

- Add `.work-*` classes to `css/style.css`, matching the existing card system:
  navy/gold palette, `--radius` (16px), hover lift + shadow, `.reveal` animation.
- Grid: 3 columns desktop → 1 column at the existing 860px breakpoint.
- Thumbnail sits in a fixed-aspect frame with `object-fit: cover`.
- Tag chips: small pill/underline treatment in gold on mist, reusing existing tokens.

## Constraints / non-goals

- No new dependencies, no build step — same vanilla stack.
- No per-project detail sub-pages, no CMS, no filtering.
- Portfolio grows by adding one card object; keep the markup simple and repeatable.
- Do not alter the existing Chairtime-centric hero or messaging.

## Verification

- Both pages render correctly desktop + mobile (headless-Chrome screenshots, matching
  the process already used for this site).
- Nav "Work" link works from both pages; footer "Work" link works.
- Every external link resolves (or is intentionally an internal anchor for Chairtime).
- Images load with correct aspect ratio and alt text; layout collapses cleanly to 1
  column on mobile.
