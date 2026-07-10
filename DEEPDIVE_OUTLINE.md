# Deep Dive: GA4 + GTM Analytics Pipeline

Outline only — full write-up pending. Structure locked in now so nothing gets lost before the content is written.

## 1. The Ask

What tracking the site needed and why: conversion-path visibility across product page views, catalog views, and outbound purchase/booking clicks.

## 2. The Plan vs. Reality

The written setup plan assumed GTM's now-retired "GA4 Configuration" tag type. What changed in GTM's UI, how it was discovered mid-build, and how the plan was corrected against the live product rather than trusted documentation.

## 3. The Build

The tag architecture: one Google Tag base configuration, five GA4 Event tags, each with a purpose-built trigger tied to a specific user action.

## 4. The Verification

Why "published" isn't "working." Using Google Tag Assistant against the live production site to confirm every trigger actually fires, rather than trusting the container configuration alone.

## 5. What Debugging Caught

- **Duplicate tracking**: a second, independent tracking snippet was firing alongside GTM, inflating pageview/session counts. How it was found (raw `dataLayer` inspection) before Tag Assistant confirmed it.
- **A trigger that can't see its target**: a click trigger for an embedded third-party widget technically fires but can't detect clicks inside a cross-origin iframe. Documented as a real platform constraint with a stated path forward, not a bug that got hidden.

## 6. Takeaway

Verification methodology as the actual deliverable — the tags themselves are the easy part.

---

**Screenshots needed (scrub before publishing — no real GA4 property ID, no auth tokens):**
- Tag Assistant "Tags Fired / Not Fired" summary for each verified event
- Full tag list and trigger list from GTM
- The `dataLayer` evaluate output that surfaced the duplicate-tag finding
- Before/after of the setup-doc correction
- Before/after of the Cal.com link fix
