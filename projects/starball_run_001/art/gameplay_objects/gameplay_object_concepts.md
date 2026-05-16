# Gameplay Object Concepts

## Purpose

This document defines the concept direction for Starball Run gameplay objects: collectibles, hazards, goal gate, platform kit, moving platform, and platform lift system.

## Reference Image

| Image | Purpose | Status |
|---|---|---|
| `images/concept_reference/core_objects_v002.png` | Review star shard, energy orb, hazard, goal gate, and platform kit | Generated, pending final review |

## Object Concepts

### Star Shard

- Basic collectible and route guide.
- Gold faceted crystal fragments.
- Should read clearly at small size.
- Avoid making it look like a flat UI icon only.

### Energy Orb

- Bonus collectible placed near risk.
- Cyan glass shell with a glowing star-like core.
- Must differ from star shards by shape and color.

### Hazard Device

- Contact hazard that causes failure or respawn.
- Dark metal body with orange hot core and warning ring.
- Visible danger range should match gameplay collision.

### Goal Gate

- Stage clear destination.
- Tall arch frame with portal disc and gold trim.
- Must read as the endpoint from a distance.

### Platform Kit

- Core playable surfaces.
- Pale stone top, deep blue frame, gold corner accents.
- Top surfaces must remain flat and easy to read.

### Moving Platform

- Platform with mechanical/energy rail language.
- Cyan rail or underside energy component should communicate movement.
- Movement path should be predictable.

### Platform Lift System

The lift system controls vertical platform movement and should be built from multiple parts rather than a single unclear mesh.

Required parts:

- fixed base
- variable column
- guide rail
- gear
- height/energy gauge
- top mount
- platform mesh

The old single-device reference and semi-transparent guide reference are superseded. Current modeling should follow the split static-mesh references listed in `gameplay_object_asset_pipeline.md`.

## Tripo3D Modeling Rule

For 3D generation, each static mesh should have its own concept image and orthographic modeling reference. Do not use old combined reference sheets as production modeling targets.
