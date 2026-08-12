# Proof headline lacks evidence — dev spec
Site: voicenotes.com · Priority 4 · Medium · Effort: Low (0.5-2 days)

## Problem
The social-proof headline promises results but no customer quotes, company names, or outcome data exist to support it.

## Evidence (from the live site)
> Real teams. Real meetings. Real results.

## Current state
h1: AI notetaker that works (magic) in the background; cta: Start for free; notes: Headline present, no supporting testimonials.

## Required change
h1: AI notetaker that works (magic) in the background; cta: Start for free; notes: Add attributed testimonials and specific outcomes below headline.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add attributed testimonials and specific outcomes below headline.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_proof_headline_lacks_evidence` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
