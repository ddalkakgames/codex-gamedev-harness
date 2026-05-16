# Core Loop System

## Purpose

The core loop defines the minimum playable sequence for Starball Run.

## State Flow

| State | Meaning | Next State |
|---|---|---|
| Ready | Waiting at start or after respawn | Playing |
| Playing | Player moves, collects, avoids hazards, and heads to the goal | Clear, Fail, or Retry |
| Clear | Player reaches the goal gate | Result / Retry |
| Fail | Player falls, hits a hazard, or times out | Retry |
| Retry | Stage resets | Ready |

## Required Feedback

- Start point is obvious.
- Collectibles disappear or trigger feedback when collected.
- Hazards communicate danger before contact.
- Goal gate reads as the destination.
- Clear and failure states are visible.

## Validation

The loop is valid when the player can start, collect at least one item, avoid or hit a hazard, reach the goal, and retry.
