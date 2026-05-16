# Gameplay Object Asset Pipeline

Status: first production scope locked.

## Purpose

This document defines the gameplay objects required for the Starball Run v0.3 art vertical slice at Unreal asset granularity.

It converts concept direction into production targets for modeling, materials, VFX, and Blueprint assembly.

## Sources

- Object concepts: `gameplay_object_concepts.md`
- Art direction: `../direction/art_direction.md`
- Asset brief: `../production/asset_brief.md`
- Reference board: `images/concept_reference/core_objects_v002.png`

## First Production Scope

| ID | Object | Gameplay Role | 3D Modeling Target | v0.3 |
|---|---|---|---|---|
| GPO-COL-001 | Star shard | Basic collectible and route guide | Yes | Required |
| GPO-COL-002 | Energy orb | Risk/reward bonus collectible | Yes | Required |
| GPO-HAZ-001 | Hazard device | Contact failure / respawn obstacle | Yes | Required |
| GPO-GOAL-001 | Goal gate | Stage clear destination | Yes | Required |
| GPO-PLAT-001 | Basic platform kit | Traversal surface | Yes | Required |
| GPO-PLAT-002 | Moving platform device | Moving traversal surface | Yes | Required |
| GPO-PLAT-003 | Platform lift device | Vertical platform movement / height readability | Yes | Required |

## Unreal Asset List

| Object | Mesh | Material / Material Instance | VFX | Blueprint |
|---|---|---|---|---|
| Star shard | `SM_SR_StarShard_A` | `MI_SR_StarShard_Gold` | `NS_SR_Collect_StarShard` | `BP_SR_StarShardPickup` |
| Energy orb | `SM_SR_EnergyOrb_Shell_A`, `SM_SR_EnergyOrb_Core_A` | `MI_SR_EnergyOrb_Glass`, `MI_SR_EnergyOrb_Core` | `NS_SR_Collect_EnergyOrb` | `BP_SR_EnergyOrbPickup` |
| Hazard device | `SM_SR_HazardDevice_A` | `MI_SR_HazardDevice_Body`, `MI_SR_HazardDevice_HotCore` | `NS_SR_HazardWarningRing`, `NS_SR_HazardHeat` | `BP_SR_HazardDevice` |
| Goal gate | `SM_SR_GoalGate_A`, `SM_SR_GoalGate_PortalDisc_A` | `MI_SR_GoalGate_Stone`, `MI_SR_GoalGate_Gold`, `MI_SR_GoalGate_Portal` | `NS_SR_GoalGate_Idle`, `NS_SR_GoalGate_Clear` | `BP_SR_GoalGate` |
| Basic platform kit | `SM_SR_Platform_1x1_A`, `SM_SR_Platform_1x2_A`, `SM_SR_Platform_Edge_A`, `SM_SR_Platform_Corner_A` | `MI_SR_Platform_StoneMetal`, `MI_SR_Platform_GoldTrim` | Optional `NS_SR_Platform_EdgeGlow` | `BP_SR_PlatformStatic` |
| Moving platform | `SM_SR_MovingPlatform_A`, `SM_SR_MovingPlatform_EnergyRail_A` | `MI_SR_MovingPlatform_Body`, `MI_SR_MovingPlatform_Energy` | `NS_SR_MovingPlatform_Trail` | `BP_SR_MovingPlatform` |
| Platform lift | `SM_SR_PlatformLiftBase_A`, `SM_SR_PlatformLiftColumn_A`, `SM_SR_PlatformLiftGuideRail_A`, `SM_SR_PlatformLiftGear_A`, `SM_SR_PlatformLiftGauge_A`, `SM_SR_PlatformLiftTopMount_A` | `MI_SR_PlatformLift_Body`, `MI_SR_PlatformLift_Energy` | `NS_SR_PlatformLift_EnergyPulse` | `BP_SR_PlatformLiftActuator` |

## Unreal Paths

| Type | Path |
|---|---|
| Mesh | `/Game/StarballRun/Art/Meshes/GameplayObjects` |
| Material | `/Game/StarballRun/Art/Materials/GameplayObjects` |
| VFX | `/Game/StarballRun/Art/VFX/GameplayObjects` |
| Blueprint | `/Game/StarballRun/Blueprints/GameplayObjects` |

## Blueprint Definitions

| Blueprint | Role | Required Components | Completion Criteria |
|---|---|---|---|
| `BP_SR_StarShardPickup` | Basic route-guiding collectible | star shard mesh, overlap collision, pickup VFX trigger | Reads as a gold shard and disappears on pickup |
| `BP_SR_EnergyOrbPickup` | Bonus collectible in risky spots | shell mesh, core mesh, overlap collision, pulse VFX trigger | Reads as more valuable and distinct from star shards |
| `BP_SR_HazardDevice` | Contact hazard | hazard mesh, hazard collision volume, warning ring VFX | Visual danger range matches collision expectation |
| `BP_SR_GoalGate` | Clear destination | gate frame mesh, portal disc mesh, clear overlap volume, idle/clear VFX | Reads as endpoint and clear trigger is obvious |
| `BP_SR_PlatformStatic` | Static traversal surface | platform mesh, simple box collision | Reads as a walkable surface |
| `BP_SR_MovingPlatform` | Moving traversal surface | platform mesh, energy rail mesh, movement timeline/component, optional trail VFX | Movement purpose is visible through rail/energy language |
| `BP_SR_PlatformLiftActuator` | Vertical platform movement | fixed base, variable column, guide rail, gear, gauge, top mount, platform mesh | Low/high/moving states are visually distinct |

## Static Mesh Definitions

| Mesh | Production Object | Shape / Parts | Pivot / Collision |
|---|---|---|---|
| `SM_SR_StarShard_A` | Star shard pickup display mesh | One large gold crystal shard with 2-3 small fragments | Pivot at center shard; overlap handled by Blueprint |
| `SM_SR_EnergyOrb_Shell_A` | Energy orb outer shell | Transparent cyan glass sphere with glowing rim | Pivot at sphere center; no gameplay collision |
| `SM_SR_EnergyOrb_Core_A` | Energy orb inner star core | Small emissive star core inside shell | Same center pivot as shell; no gameplay collision |
| `SM_SR_HazardDevice_A` | Hazard device body | Dark metal body, orange hot core, rotating ring, vents | Pivot at body center; collision volume handled separately |
| `SM_SR_GoalGate_A` | Goal gate frame | Pale stone arch, side pillars, gold trim, top star core | Pivot at bottom center; clear volume separate |
| `SM_SR_GoalGate_PortalDisc_A` | Portal display surface | Thin circular disc or plane inside frame | Pivot at portal center; no collision |
| `SM_SR_Platform_1x1_A` | Basic 1-tile platform | Flat stone top, blue metal frame, gold corner caps | Pivot at tile center; flat box collision |
| `SM_SR_Platform_1x2_A` | Basic 2-tile platform | Longer version of 1x1 platform | Pivot at center; 2-tile box collision |
| `SM_SR_Platform_Edge_A` | Platform edge trim | Narrow blue/gold side strip | No standalone gameplay collision |
| `SM_SR_Platform_Corner_A` | Platform corner cap | Gold corner decoration / protector | No standalone gameplay collision |
| `SM_SR_MovingPlatform_A` | Moving platform body | Platform with mechanical movement language | Pivot at movement path center; top collision |
| `SM_SR_MovingPlatform_EnergyRail_A` | Moving platform energy rail | Cyan glowing rail or underside guide | No collision; movement readability part |
| `SM_SR_PlatformLiftBase_A` | Fixed lift base | Stone/metal base block anchored to world | Pivot at bottom center; static |
| `SM_SR_PlatformLiftColumn_A` | Variable lift column | Telescoping or segmented column | Pivot at bottom; scale/segment changes with height |
| `SM_SR_PlatformLiftGuideRail_A` | Vertical guide rail | Fixed side rail showing travel axis | Decorative or simple collision |
| `SM_SR_PlatformLiftGear_A` | Drive gear | Gold gear and small support gear | Pivot at rotation center |
| `SM_SR_PlatformLiftGauge_A` | Energy/height gauge | Cyan vertical gauge or panel | No collision; shows movement state |
| `SM_SR_PlatformLiftTopMount_A` | Top mount | Bracket/socket connecting platform to column | Placed under moving `TopMount` component |

## Material Instances

| Material Instance | Target | Production Rule |
|---|---|---|
| `MI_SR_StarShard_Gold` | `SM_SR_StarShard_A` | Gold crystal/metal with strong emissive edges |
| `MI_SR_EnergyOrb_Glass` | `SM_SR_EnergyOrb_Shell_A` | Cyan transparent glass with rim emissive |
| `MI_SR_EnergyOrb_Core` | `SM_SR_EnergyOrb_Core_A` | Bright cyan/white star core emissive |
| `MI_SR_HazardDevice_Body` | Hazard body | Dark metal / gunmetal |
| `MI_SR_HazardDevice_HotCore` | Hazard core/ring | Orange/red warning emissive |
| `MI_SR_GoalGate_Stone` | Goal gate stone | Pale stone, low saturation |
| `MI_SR_GoalGate_Gold` | Goal trim | Gold trim and highlights |
| `MI_SR_GoalGate_Portal` | Portal disc | Purple/white portal emissive |
| `MI_SR_Platform_StoneMetal` | Platform slabs/frame | Stone top and blue metal frame |
| `MI_SR_Platform_GoldTrim` | Platform edge/corner | Gold corner caps and trim |
| `MI_SR_MovingPlatform_Body` | Moving platform body | Stone/metal platform body |
| `MI_SR_MovingPlatform_Energy` | Moving platform rail | Cyan rail emissive |
| `MI_SR_PlatformLift_Body` | Lift body parts | Stone/metal/gold trim |
| `MI_SR_PlatformLift_Energy` | Lift gauge/energy strips | Cyan energy emissive |

## VFX

| VFX | Target | Production Rule |
|---|---|---|
| `NS_SR_Collect_StarShard` | `BP_SR_StarShardPickup` | Short gold star-dust pickup burst |
| `NS_SR_Collect_EnergyOrb` | `BP_SR_EnergyOrbPickup` | Cyan pulse and small star specks |
| `NS_SR_HazardWarningRing` | `BP_SR_HazardDevice` | Orange ring/arc showing danger area |
| `NS_SR_HazardHeat` | `BP_SR_HazardDevice` | Heat shimmer around hot core |
| `NS_SR_GoalGate_Idle` | `BP_SR_GoalGate` | Subtle purple/white portal glow |
| `NS_SR_GoalGate_Clear` | `BP_SR_GoalGate` | One-second clear burst into the portal |
| `NS_SR_Platform_EdgeGlow` | Platform kit | Low-intensity edge readability glow |
| `NS_SR_MovingPlatform_Trail` | `BP_SR_MovingPlatform` | Cyan trail while moving |
| `NS_SR_PlatformLift_EnergyPulse` | `BP_SR_PlatformLiftActuator` | Cyan pulse during lift start/stop |

## Modeling References

Current references are split by static mesh:

- Concept image: `images/concept_reference/static_meshes/<mesh_lower>_concept_v001.png`
- Orthographic image: `images/modeling_reference/static_meshes/<mesh_lower>_orthographic_v001.png`

Old combined sheets are kept under `images/legacy/modeling_reference_pre_mesh_split/` for history only and should not be used as current modeling targets.

## Platform Assembly Rule

```text
basic platform top module
  + optional moving-platform energy rail
  + optional lift actuator
```

- `BP_SR_PlatformStatic` uses the basic platform kit.
- `BP_SR_MovingPlatform` combines the platform kit with an energy rail.
- `BP_SR_PlatformLiftActuator` attaches below a platform and controls vertical movement.
- Lift devices belong to gameplay objects because they change traversal, not background decoration.

## Lift Blueprint Structure

| Component / Property | Role |
|---|---|
| `Root` | Fixed world anchor |
| `LiftBaseMesh` | Fixed base mesh |
| `LiftColumnMesh` | Scales or swaps segments with height |
| `LiftGuideRailMesh` | Fixed vertical travel guide |
| `LiftGearMesh` | Rotates while moving |
| `LiftGaugeMesh` | Shows current movement/height energy |
| `TopMount` | Moving scene component |
| `PlatformMesh` | Walkable platform mesh and collision |
| `MinHeight` | Lowest position |
| `MaxHeight` | Highest position |
| `TravelTime` | Travel duration |
| `MoveMode` | Loop, trigger, or stepped movement |

## Approval Criteria

- Asset names and paths match this document.
- Modeling follows split concept/orthographic references.
- Collision readability is reviewed in `../reviews/`.
- IP safety is checked before public use.
