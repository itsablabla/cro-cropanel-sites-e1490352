# Hero lacks concrete outcome — dev spec
Site: voicenotes.com · Priority 3 · Medium · Effort: Low (0.5-2 days)

## Problem
The homepage headline names the product but uses vague parenthetical language, failing to explain the concrete benefit.

## Evidence (from the live site)
> AI notetaker that works (magic) in the background

## Current state
h1: AI notetaker that works (magic) in the background; cta: Book a demo | Start for free | Get the desktop app | Contact support; notes: Vague parenthetical.

## Required change
h1: AI notetaker that automatically records, transcribes, and summarizes meetings; cta: Start for free; notes: Plain-language outcome.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Plain-language outcome.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_hero_lacks_concrete_outcome` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
