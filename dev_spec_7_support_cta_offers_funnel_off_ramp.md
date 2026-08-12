# Support CTA offers funnel off-ramp — dev spec
Site: voicenotes.com · Priority 7 · Medium · Effort: Medium (2-5 days)

## Problem
Contact support is surfaced as a peer CTA on conversion pages, inviting mid-funnel users to leave the purchase path.

## Evidence (from the live site)
> ctas: Book a demo | Start for free | Get the desktop app | Contact support
> ctas: Book a demo | Start for free | Get Started | Contact Sales | Get the desktop app | Contact support

## Current state
h1: AI notetaker that works (magic) in the background; cta: Contact support alongside conversion CTAs; notes: Support CTA competes with signup.

## Required change
h1: AI notetaker that works (magic) in the background; cta: Start for free (primary); notes: Move Contact support to footer.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Move Contact support to footer.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_support_cta_offers_funnel_off_ramp` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
