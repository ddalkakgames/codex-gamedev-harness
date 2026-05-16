# New Project Guide

Use this guide when starting a new game project under `projects/<project_id>/`.

## 1. Pick a Project ID

Use a short lowercase identifier:

```text
arcade_runner_001
puzzle_dungeon_001
starball_run_001
```

## 2. Create the Folder Structure

```text
projects/<project_id>/
  README.md
  design/
  systems/
  art/
    README.md
    direction/
    concepts/
    characters/
    gameplay_objects/
    environment/
    animation_vfx/
    production/
    reviews/
    work_items/
  engineering/
  ux/
  qa/
  production/
  slices/
  versions/
  work_items/
  project_memory/
```

## 3. Start With Game Design

Create these documents first:

- `design/game_concept.md`
- `design/game_design_principles.md`
- `design/game_design_document.md`
- `systems/core_loop.system.md`

Do not start from isolated assets. Start from the game promise, player goal, core loop, and version target.

## 4. Add the Art Sub-Harness

The project art folder should explain how art direction, concept references, modeling references, and asset briefs are managed.

Recommended image stages:

| Stage | Purpose |
|---|---|
| `concept_reference` | Visual direction and concept review |
| `modeling_reference` | Orthographic or part-focused references for 3D modeling |
| `production_reference` | Finalized production reference images |
| `legacy` | Old references kept for history only |
| `superseded_reference` | Rejected or replaced references |

## 5. Define the First Vertical Slice

A vertical slice should answer:

- What can the player do?
- What is the goal?
- What makes the interaction interesting?
- What assets are required?
- What can be validated in Unreal?
- What proves this version is complete?

## 6. Connect to GameDevMCP

When the project reaches implementation, document:

- required GameDevMCPPlugin version
- required MCP tool capabilities
- target Unreal project path
- generated or modified Unreal assets
- validation result

## 7. Keep Project Memory Updated

The `project_memory/` folder should summarize decisions so future agents do not need to reconstruct the project from chat history.
