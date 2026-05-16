# Framework

The `framework/` directory contains reusable rules, templates, schemas, and guides shared by every game project managed by Codex GameDev Harness.

## Role

- Define the baseline project folder structure.
- Provide Markdown templates for human-reviewed game production documents.
- Provide image-generation workflow guidance for concept review.
- Provide JSON schemas only where automation needs structured validation.
- Explain the recommended order for building a project from concept to playable slice.

## Directory Layout

```text
framework/
  schemas/    # JSON schemas for automation and validation
  templates/  # human-readable Markdown templates
  guides/     # workflow guides
```

## Main Templates

| Template | Purpose |
|---|---|
| `game_concept.template.md` | Define the game concept |
| `game_design_principles.template.md` | Define game design principles |
| `game_design_document.template.md` | Draft the game design document |
| `system_spec.template.md` | Describe one gameplay/system feature |
| `art_harness_readme.template.md` | Create the art sub-harness entry point |
| `art_direction.template.md` | Define art direction |
| `concept_brief.template.md` | Review concept images and art intent |
| `art_asset_brief.template.md` | Describe an asset production request |
| `traceability_matrix.template.md` | Track design-to-implementation coverage |
| `version.template.md` | Define version completion criteria |

## Image Generation Principles

`imagegen` is used to help people review art direction quickly. Generated images are references, not final production assets.

- Store generated images next to the category that uses them.
- Do not collect every image under a single central `art/images/` folder.
- Example paths: `art/gameplay_objects/images/modeling_reference/`, `art/characters/images/concept_reference/`.
- Do not expose raw image-generation prompts in user-facing review documents.
- Record the image, purpose, decision, and revision notes instead.

## Principles

1. Keep shared framework docs free of game-specific lore.
2. Store project-specific concepts, systems, art direction, versions, and validation under `projects/<project_id>/`.
3. Treat Markdown as the primary human review format.
4. Use JSON as an automation support layer, not as the main design source.
