# Pricing lacks billing context — dev spec
Site: voicenotes.com · Priority 9 · Medium · Effort: Medium (2-5 days)

## Problem
Per-user prices are shown without billing period or commitment details, so visitors cannot tell if the price is monthly or annual.

## Evidence (from the live site)
> $0 $9 /user $24 /user
> Get Started
> Every meeting, remembered.

## Current state
h1: Every meeting, remembered.; cta: Get Started; notes: Prices lack billing term.

## Required change
h1: Plans & Pricing; cta: Start for free / Start trial / Contact Sales; notes: Add billing toggle and plan names.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add billing toggle and plan names.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_pricing_lacks_billing_context` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
