# Competing CTAs dilute primary action — dev spec
Site: voicenotes.com · Priority 1 · Urgent · Effort: Medium (2-5 days)

## Problem
Multiple competing CTAs on the homepage dilute the primary signup action, creating ambiguity in the first step of the funnel.

## Evidence (from the live site)
> ctas: Book a demo | Start for free | Get the desktop app | Contact support
> h1: AI notetaker that works (magic) in the background

## Current state
h1: AI notetaker that works (magic) in the background; cta: Book a demo | Start for free | Get the desktop app | Contact support; notes: Four competing CTAs, no pricing link in nav or footer.

## Required change
h1: AI notetaker that automatically records, transcribes, and summarizes meetings; cta: Start for free (primary), secondary links in nav/footer; notes: Single dominant CTA; move demo, app, support to nav/footer; add Pricing link.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Single dominant CTA; move demo, app, support to nav/footer; add Pricing link.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_competing_ctas_dilute_primary_action` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 124,891 visitors per variant to detect a 8.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
