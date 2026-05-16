# Starball Run

`starball_run_001` is the first live production test project for Codex GameDev Harness.

## One-Line Pitch

A short 2.5D platform game where the player collects star shards and energy orbs, avoids moving hazards, and reaches a goal gate.

## Production Goals

- Validate the full flow from game design to systems, art, engineering, UX, QA, and version decisions.
- Grow through small validated vertical slices rather than trying to build the full game at once.
- Use GameDevMCP to inspect assets, place actors, create/modify Blueprints, update settings, and record Unreal validation results.

## Current Version Targets

| Version | Status | Completion Target |
|---|---|---|
| v0.1 | Documented | Concept, design principles, core loop, and first stage requirements are defined |
| v0.2 | Prototype planned | First playable stage with start, collectibles, hazards, and goal |
| v0.3 | Art vertical slice planned | Score, timer, failure/success UI, retry flow, and project-specific art proxies |

## Document Map

- `design/`: concept, design principles, and game design document
- `systems/`: core loop and collection/hazard/goal systems
- `art/`: Starball Run art sub-harness
- `engineering/`: Unreal implementation design and backlog
- `ux/`: HUD, feedback, and input flow
- `qa/`: validation strategy
- `production/`: roadmap, pipeline, and traceability
- `slices/`: vertical slice definitions
- `versions/`: milestone completion criteria
- `project_memory/`: durable project decisions, asset manifests, and feature status
- `implementation/`: GameDevMCP and Unreal application logs

## IP Rule

This project does not copy existing commercial games, characters, maps, or presentation. It references only broad platformer structures such as movement, collection, hazard avoidance, and reaching a goal.

## Practical Production Rule

v0.2 may use Unreal template assets to validate playability. v0.3 starts replacing those proxies with Starball Run-specific character, collectible, hazard, platform, goal, and environment assets.
