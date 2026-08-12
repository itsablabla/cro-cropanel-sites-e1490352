# No guarantee at pricing — dev spec
Site: voicenotes.com · Priority 8 · Medium · Effort: Medium (2-5 days)

## Problem
The pricing page shows paid tiers without any explicit guarantee or trial terms, increasing perceived risk at the moment of commitment.

## Evidence (from the live site)
> prices: $0 $9 /user $24 /user
> Get Started

## Current state
h1: Every meeting, remembered.; cta: Get Started; notes: No guarantee or trial terms visible.

## Required change
h1: Every meeting, remembered.; cta: Get Started; notes: Add risk-reversal statement (free trial or money-back guarantee).

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add risk-reversal statement (free trial or money-back guarantee).
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_no_guarantee_at_pricing` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
