# Validation Strategy

## Purpose

Validation proves that each Starball Run version is playable, readable, and aligned with the design goals.

## v0.2 Checks

| Check | Purpose | Method |
|---|---|---|
| MCP smoke test | Confirm Unreal automation access | `tools/list` and basic tool call |
| Blueprint compile | Catch broken Blueprint assets | GameDevMCP or Unreal Editor |
| Map check | Catch level errors | `world.validation.map_check` |
| Manual play test | Validate the full loop | Human play or guided test |
| Design questions | Validate intended experience | Checklist review |

## Manual Play Questions

- Can the player identify the route quickly?
- Can the player collect at least one star shard?
- Is the energy orb clearly optional and more valuable?
- Is hazard failure readable?
- Does the goal gate read as the endpoint?
- Does retry work without resetting the editor manually?

## Art Validation Questions

- Are collectible, hazard, goal, and platform silhouettes distinct?
- Does VFX reinforce state without hiding collision?
- Does environment detail stay behind gameplay readability?
- Are generated assets safe from obvious IP copying?
