# Art Production Strategy

## Purpose

Starball Run is a practical test of the full AI-assisted asset pipeline: concept references, modeling references, generated 3D assets, Unreal import, and playable validation.

## Strategy

1. Use template assets only for v0.2 playability validation.
2. Define Starball Run-specific visual direction in documents.
3. Generate concept images for review.
4. Split gameplay objects into real static mesh targets.
5. Generate orthographic modeling references for each mesh.
6. Produce or generate 3D models from approved references.
7. Import models into Unreal through GameDevMCP.
8. Validate readability, collision expectations, and gameplay integration.

## Production Priorities

| Priority | Asset Group | Reason |
|---|---|---|
| 1 | Star shard, energy orb, hazard, goal gate | Core loop readability |
| 2 | Platform kit, moving platform, lift system | Traversal readability |
| 3 | Lumi proxy character | Player identity |
| 4 | Environment rough kit | Visual identity without hurting gameplay readability |
| 5 | VFX and UI polish | Feedback and replay motivation |

## Review Rule

An asset is not accepted just because a generated image looks good. It must also work in gameplay camera, collision, scale, material, and Blueprint context.
