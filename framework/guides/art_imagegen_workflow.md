# Art Image Generation Workflow

This guide explains how Codex GameDev Harness uses generated images inside art documents.

## Purpose

Generated images help users and agents align on visual direction before production assets are made. They are not final game assets by default.

## Folder Convention

Use category-local image folders:

```text
art/
  concepts/images/concept_reference/
  direction/images/concept_reference/
  characters/images/concept_reference/
  gameplay_objects/images/concept_reference/
  gameplay_objects/images/modeling_reference/
  environment/images/concept_reference/
```

## Recommended Flow

1. Write the design or art document first.
2. Identify where a visual reference would make review easier.
3. Generate the image with the internal image-generation workflow.
4. Save the result under the relevant category and stage folder.
5. Link the image from the Markdown document.
6. Record the image purpose, review status, and revision notes.

## Review Table

| Field | Meaning |
|---|---|
| Image | Relative path to the generated image |
| Purpose | What decision this image supports |
| Status | Accepted, needs revision, or rejected |
| Notes | What to keep, change, or avoid |

## Usage Rules

- Do not publish raw prompts unless they are intentionally part of a reproducibility document.
- Keep visual references close to the feature or asset they support.
- Move obsolete images to `legacy/` or `superseded_reference/` when they are no longer production references.
- If an image is used for 3D modeling, make the target mesh, scale, silhouette, and separated parts explicit in the related asset brief.
