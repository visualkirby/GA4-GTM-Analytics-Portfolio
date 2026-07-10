# ga4-gtm-analytics-portfolio - Session Log

Repo: `D:\Documents\Github\ga4-gtm-analytics-portfolio` (private)
Purpose: portfolio piece documenting the GA4 + GTM analytics build on benchlineanalytics.com, per the master plan's Marketing & Analytics Infrastructure Plan Phase 3

---

## Session: 2026-07-10 (scaffold)

**Scaffolded the repo skeleton only -- no real content yet, per the master plan's own sequencing (don't publish real content until Phase 2 / Looker Studio is done):**
- `README.md`: full structure filled in with real, non-sensitive content (project overview, tag/trigger inventory table with real tag/trigger names, tools used, author block); Key Metrics and screenshots explicitly marked "Coming Soon"
- `LICENSE`: MIT
- `DEEPDIVE_OUTLINE.md`: the 6-section narrative structure agreed with Sawandi (The Ask, The Plan vs. Reality, The Build, The Verification, What Debugging Caught, Takeaway) as headers only, plus the screenshot checklist -- locked in now while fresh, content written later
- `screenshots/`: empty, `.gitkeep` only
- Initial commit, GitHub repo created private under visualkirby, pushed

**The actual GA4/GTM build this repo will document** (full detail in `benchline-analytics-llc`'s context.md): GTM container GTM-MNFBCX5Q, GA4 - Base Configuration tag + 5 GA4 Event tags/triggers, all verified firing via Google Tag Assistant. Two real findings from that debugging process are the intended centerpiece of the Deep Dive: a duplicate-tracking bug (Site Kit's own gtag.js firing alongside GTM) and a trigger-design limitation (a click trigger can't see clicks inside a cross-origin iframe).

### Key Notes
- No real GA4 property ID, auth tokens, or traffic/revenue numbers exist in this repo -- keep it that way until the scrub step is actually done at publish time
- The narrative angle is the debugging/verification methodology, not "here's a GA4 setup tutorial" -- don't let that get diluted when filling in real content later

### What Is Next
- Wait for Looker Studio (Phase 2) and 2-4 weeks of real traffic data before touching this repo again
- When ready: write the Deep Dive content per the outline, take and scrub the planned screenshots (redact `G-3XGQN4JNJ0` -> placeholder, crop any `gtm_auth=`/`cb=` tokens out of Tag Assistant screenshots), fill in the Key Metrics table, add the primary badge link
- Add to GitHub profile README's Featured Projects section once live (see memory `project_portfolio_maintenance.md`)
