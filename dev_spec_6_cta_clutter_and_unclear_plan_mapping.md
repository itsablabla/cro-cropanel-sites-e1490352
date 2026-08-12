# CTA clutter and unclear plan mapping — dev spec
Site: voicenotes.com · Priority 6 · Medium · Effort: Medium (2-5 days)

## Problem
The pricing page presents multiple similar CTAs without clear association to tiers, confusing the next step after plan selection.

## Evidence (from the live site)
> prices: $0 $9 /user $24 /user
> ctas: Book a demo | Start for free | Get Started | Contact Sales | Get the desktop app | Contact support

## Current state
h1: Every meeting, remembered.; cta: Book a demo | Start for free | Get Started | Contact Sales | Get the desktop app | Contact support; notes: Multiple CTAs, no billing context, no guarantee.

## Required change
h1: Plans & Pricing; cta: Start for free (for $0), Start trial (for $9), Contact Sales (for $24); notes: Single CTA per tier, add billing toggle, add guarantee, remove generic Get Started.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Single CTA per tier, add billing toggle, add guarantee, remove generic Get Started.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_cta_clutter_and_unclear_plan_mapping` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
