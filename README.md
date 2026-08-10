# GA4 + GTM Analytics Pipeline

**Google Tag Manager | Google Analytics 4 | Analytics Engineering**

[![Deep Dive (Coming Soon)](https://img.shields.io/badge/📓_Deep_Dive-Coming_Soon-D9D9D9)](./DEEPDIVE_OUTLINE.md)

A GA4 + Google Tag Manager conversion-tracking build for a WordPress product site, covering the tag architecture, a live platform migration it had to account for mid-build, and the debugging process used to verify every event against real production behavior before publishing.

---

# Project Overview

The site needed conversion-path tracking across three actions that actually matter for a self-serve product business: someone viewing a product, someone viewing the products catalog, and someone clicking through to buy or book. The plan going in assumed Google Tag Manager's older "GA4 Configuration" tag type. Partway through the build, that assumption turned out to be wrong — Google had quietly retired it in favor of a unified "Google Tag" type, with GA4 Event tags now taking a direct Measurement ID field instead of referencing a separate configuration tag. The build (and the written setup plan it followed) had to be corrected against the real, current UI rather than trusted documentation.

The second half of the project was verification: rather than assume "published" meant "working," every tag was tested against the live site using Google Tag Assistant. That process caught two real problems before they could corrupt data — see [Known Limitations](#3️⃣-known-limitations) below.

---

# What's Inside

### 1️⃣ Tag Architecture
One base "Google Tag" configuration plus five GA4 Event tags, each mapped to a specific trigger and a specific user action. See the inventory table below.

### 2️⃣ Debugging Process
*(Coming soon — full write-up in the Deep Dive)* How Google Tag Assistant was used to verify each trigger against live production behavior, including the raw `dataLayer` inspection that first surfaced a duplicate-tracking bug.

### 3️⃣ Known Limitations
*(Coming soon — full write-up in the Deep Dive)* A documented case where a click trigger technically fires but can't see its actual target, because the target lives inside a cross-origin iframe — and why that's a real constraint, not a bug to hide.

---

# Tag / Trigger Inventory

| Tag | Type | Trigger | Fires On |
|---|---|---|---|
| GA4 - Base Configuration | Google Tag | Initialization - All Pages | Every page load |
| GA4 Event - Products Hub View | GA4 Event | Page View - Products Hub | `/products/` page view |
| GA4 Event - Product Page View | GA4 Event | Page View - Product Pages | Individual product page view |
| GA4 Event - Gumroad Click | GA4 Event | Click - Gumroad Links | Outbound click to Gumroad |
| GA4 Event - Cal.com Click | GA4 Event | Click - Cal.com Links | Outbound click to Cal.com |
| GA4 Event - Contact Form Submit | GA4 Event | Form Submit - Contact Page | Contact form submission |

# Key Metrics

*(Full metrics table coming once Looker Studio dashboard is built on 2-4 weeks of real traffic data.)*

# Weekly Tracking

Lightweight weekly GA4 snapshots (7-day view), started ahead of the full Looker Studio dashboard. Property ID and any auth tokens are never shown in these screenshots.

| Date | Active Users | New Users | Sessions | Top Traffic Source | Screenshot |
|---|---|---|---|---|---|
| 2026-08-10 | 6 | 1 | 30 | Referral -- indiehackers.com (21 sessions) | [GA4 Home](screenshots/ga4-home-2026-08-10.png) |

---

# How It Was Built

- Google Tag Manager (container-based tag/trigger/variable management)
- Google Analytics 4 (Measurement Protocol via GTM's Google Tag)
- Google Tag Assistant (live production debugging and verification)
- Looker Studio (dashboard — pending, Phase 2)

# Tools Used

- Google Tag Manager
- Google Analytics 4
- Google Tag Assistant
- Looker Studio (planned)

# Author

**Sawandi Kirby**

Data Analytics & Business Intelligence
Benchline Analytics - Data intelligence for organizations that mean business.

- GitHub: https://github.com/visualkirby
- LinkedIn: https://linkedin.com/in/sawandi-kirby
- Kaggle: https://kaggle.com/sawandikirby
