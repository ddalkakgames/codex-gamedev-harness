# Game Design Document

## Overview

Starball Run is a short-course platform game about improving collection score and clear time across repeated attempts.

## Controls

| Input | Action |
|---|---|
| Move left/right | Move the character |
| Jump | Traverse platforms and avoid hazards |
| Retry | Restart after failure or clear |

## Core Loop

1. Start the stage.
2. Read the route.
3. Collect star shards and energy orbs.
4. Avoid hazards.
5. Reach the goal gate.
6. Review the result.
7. Retry for a better score or time.

## Collectibles

| Name | Role | Placement Rule |
|---|---|---|
| Star shard | Basic score and route guidance | Placed along the main route with rhythmic spacing |
| Energy orb | Bonus score | Placed near risky jumps or hazards |

## Hazards

| Name | Role | v0.2 Implementation |
|---|---|---|
| Rotating hazard | Timing avoidance | Fixed-position rotating danger volume |
| Pit / fall zone | Jump accuracy test | Gap or out-of-bounds failure area |
| Moving platform | Timing traversal | Platform moving along a defined route |

## Clear Condition

The stage clears when the player reaches the goal gate. v0.2 does not require all collectibles. v0.3 can add optional completion goals.

## Failure Conditions

- Falling into a fail area
- Colliding with a hazard
- Running out of time

v0.2 may reset the player to the start after a fall or collision. v0.3 adds failure UI and retry flow.

## First Stage Structure

1. Safe start area
2. Basic jump and star shard collection area
3. Moving platform area
4. Optional energy orb near a hazard
5. Short combined challenge before the goal gate

## Fun Validation Questions

- Does the player understand the goal within the first 10 seconds?
- Does following star shards naturally lead to the goal?
- Is there a reason to risk grabbing an energy orb?
- Is failure readable without explanation?
- Does the player want to retry after three attempts?
