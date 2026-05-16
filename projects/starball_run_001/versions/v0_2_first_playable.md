# v0.2 First Playable

## Purpose

Build the first playable Starball Run prototype using existing Unreal template assets where necessary.

## Required Systems

| System | Minimum Scope | Status |
|---|---|---|
| Character move/jump | Player can move and jump | Prototype duplicated |
| Collectibles | Star shard and energy orb candidates | Prototype placement started |
| Hazard | Failure or respawn condition | Pending dedicated logic |
| Goal gate | Clear trigger | Pending dedicated logic |
| Retry | Restart the same stage | Pending |

## Current Evidence

- Native MCP connection was verified.
- Six duplicated Blueprints compiled successfully.
- `world.validation.map_check` returned error count 0 in the temporary validation world.
- Final placement still needs to be locked in `/Game/StarballRun/Maps/Lvl_Starball_FirstPlayable`.

## Completion Criteria

1. The final StarballRun map opens in Unreal.
2. The player can start, collect, avoid/fail, reach the goal, and retry.
3. Map check and Blueprint compile pass without critical errors.
4. A manual play validation report is recorded.
