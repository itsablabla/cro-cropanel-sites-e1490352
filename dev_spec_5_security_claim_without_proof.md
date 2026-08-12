# Security claim without proof — dev spec
Site: voicenotes.com · Priority 5 · High · Effort: Medium (2-5 days)

## Problem
The enterprise-grade security claim is repeated without any supporting evidence, undermining trust at the pricing decision point.

## Evidence (from the live site)
> Enterprise-grade security. No compromise.

## Current state
h1: Every meeting, remembered.; cta: Get Started; notes: Security claim present but no certifications or links.

## Required change
h1: Every meeting, remembered.; cta: Get Started; notes: Add security certifications, compliance status, or link to security docs.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add security certifications, compliance status, or link to security docs.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_security_claim_without_proof` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 315,206 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
