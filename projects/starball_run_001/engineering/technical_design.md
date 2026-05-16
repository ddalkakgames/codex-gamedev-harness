# Technical Design

## Purpose

Build the first playable Starball Run slice by iterating on Unreal level placement, Blueprint creation/modification, settings changes, and validation through GameDevMCP.

## Target Runtime

| Topic | Decision |
|---|---|
| Engine | Unreal Engine 5.7 target |
| Prototype base | Side-scrolling template assets for v0.2 |
| Implementation layer | Blueprint-first prototype, C++ only when needed |
| Automation layer | GameDevMCP native MCP endpoint |
| Target project | TestMcp / StarballRun content path during prototype |

## Main Systems

| System | Implementation Direction |
|---|---|
| Character movement | Start from side-scrolling character template |
| Collectibles | Prototype generic collectible, then split star shard and energy orb |
| Hazards | Prototype overlap/failure actor, then replace with hazard device |
| Goal gate | Clear trigger volume and goal Blueprint |
| Course manager | Timer, respawn, score, retry, and result flow |
| Platforms | Static, moving, and lift platform Blueprints |

## GameDevMCP Validation Points

- MCP endpoint connection succeeds.
- Required tools are listed.
- Blueprints compile.
- Level map check passes without critical errors.
- Actor placement matches the intended first playable layout.
- Validation results are recorded in `implementation/` or `qa/`.
