# Collectibles, Hazards, and Goal System

## Purpose

This system connects route guidance, optional reward, failure pressure, and stage completion.

## Collectibles

| Item | Purpose | Feedback |
|---|---|---|
| Star shard | Main route guidance and base score | Gold sparkle / pickup feedback |
| Energy orb | Optional risk reward | Stronger cyan pulse / bonus feedback |

## Hazards

Hazards must show their danger area clearly. The visible form and collision volume should feel consistent.

| Hazard | Purpose | Feedback |
|---|---|---|
| Hazard device | Timing and positioning challenge | Orange warning ring and hot core |
| Pit / fall area | Jump accuracy challenge | Clear drop or out-of-bounds reset |

## Goal

The goal gate marks the stage endpoint. It must read as a destination from a distance and trigger a clear result when entered.

## Validation

- The star shard trail leads toward the goal.
- Energy orbs are visibly more valuable than star shards.
- Hazards are readable before failure.
- Goal collision matches the visible gate area.
