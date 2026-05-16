# Starball Run Asset Brief

## Purpose

This document defines the asset set needed for the v0.3 art vertical slice.

## Target Version

v0.3 Art Vertical Slice

## Reference Images

| Image | Purpose | Status |
|---|---|---|
| `../characters/images/concept_reference/character_sheet_v001.png` | Lumi proxy character direction | Generated, pending review |
| `../gameplay_objects/images/concept_reference/core_objects_v002.png` | Core gameplay object direction | Generated, pending review |
| `../environment/images/concept_reference/environment_key_v001.png` | Environment rough kit direction | Generated, pending review |

## Required Asset Groups

| Group | Required Outputs | Notes |
|---|---|---|
| Lumi character proxy | Mesh/proxy, material, basic animation intent | Silhouette first |
| Star shard | Mesh, material, pickup VFX, pickup Blueprint | Route guidance |
| Energy orb | Shell/core meshes, materials, pickup VFX, pickup Blueprint | Bonus reward |
| Hazard device | Mesh, materials, warning VFX, hazard Blueprint | Readable failure |
| Goal gate | Frame/portal meshes, materials, clear VFX, goal Blueprint | Destination clarity |
| Platform kit | Platform meshes, materials, static Blueprint | Traversal readability |
| Moving platform | Platform body, energy rail, movement Blueprint | Timing challenge |
| Platform lift | Split lift meshes, energy material, lift Blueprint | Vertical traversal |
| Environment rough kit | Background/side elements | Must not reduce gameplay readability |

## Completion Criteria

- Each asset has a clear gameplay or readability purpose.
- Each mesh target has a concept and modeling reference when needed.
- Unreal paths and asset names match `gameplay_object_asset_pipeline.md`.
- Assets can be reviewed in engine camera distance.
