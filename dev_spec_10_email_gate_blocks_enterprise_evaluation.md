# Email gate blocks enterprise evaluation — dev spec
Site: voicenotes.com · Priority 10 · High · Effort: Medium (2-5 days)

## Problem
The enterprise page asks for a business email before showing any value or pricing, creating a high-friction gate that blocks evaluation.

## Evidence (from the live site)
> Voicenotes for Enterprise | What is your business email?
> Bring Voicenotes to your team

## Current state
h1: Voicenotes for Enterprise; cta: What is your business email?; notes: Email field immediately, no features or pricing shown.

## Required change
h1: Voicenotes for Enterprise; cta: Explore features and pricing first, then optional email; notes: Show value and pricing before email capture.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Show value and pricing before email capture.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_email_gate_blocks_enterprise_evaluation` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 315,206 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
