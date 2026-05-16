# Unreal MCP Application Plan

## Goal

Apply the documented v0.2 first playable requirements to the TestMcp project as a small prototype.

## First Application Method

Use existing `Variant_SideScrolling` template assets first.

1. Verify native MCP HTTP connection.
2. Inspect the current editor world.
3. Verify candidate collectible/platform asset paths.
4. Create StarballRun prototype assets under `/Game/StarballRun`.
5. Place test actors.
6. Run map check.
7. Record results here.

## Note

The editor may have a different map open. In that case, the first placement is treated as a loop-placement test, not the final first playable map.

## Application Log

### 2026-05-07 First Application

MCP native HTTP endpoint connection was verified.

- URL: `http://172.17.32.1:19091/mcp`
- UE version: `5.7.4-51494982+++UE5+Release-5.7`
- Registered tool count: 514

StarballRun prototype assets were created in the local TestMcp project.

| Task | Result |
|---|---|
| Duplicate `/Game/Variant_SideScrolling/Lvl_SideScrolling` | Created `/Game/StarballRun/Maps/Lvl_Starball_FirstPlayable` |
| Duplicate character/game mode/controller | Created `BP_StarballCharacter`, `BP_StarballGameMode`, `BP_StarballPlayerController` |
| Duplicate collectible/platform assets | Created `BP_StarballCollectible`, `BP_StarballMovingPlatform`, `BP_StarballSoftPlatform` |
| Compile Blueprints | 6 Blueprints compiled successfully |

The currently opened world was `/Game/ThirdPerson/Lvl_ThirdPerson`. Nineteen `SBR_*` validation actors were placed there.

| Category | Count |
|---|---:|
| PlayerStart | 1 |
| Star shard candidates | 10 |
| Energy orb candidates | 3 |
| Moving platform | 1 |
| Soft platform | 1 |
| Lava hazard candidates | 2 |
| Goal trigger candidate | 1 |

`world.validation.map_check` result:

- actor count: 134
- error count: 0
- warning count: 18

The warnings came from the existing ThirdPerson world and were not critical errors caused by the StarballRun placement.

## Current Constraint

The current MCP tool set does not include a dedicated tool for opening a specific editor map. The first placement therefore happened in the currently open ThirdPerson world. The next step is to open `/Game/StarballRun/Maps/Lvl_Starball_FirstPlayable` and lock the same course placement there.

## Next Work

1. Open `/Game/StarballRun/Maps/Lvl_Starball_FirstPlayable` in the editor.
2. Re-place the `SBR_*` course actors in that map.
3. Implement `BP_StarballGoalGate` and `BP_StarballHazard` logic.
4. Run manual play validation for start, collection, avoidance, clear, and retry.
