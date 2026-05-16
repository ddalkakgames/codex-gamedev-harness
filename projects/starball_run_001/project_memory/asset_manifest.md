# Asset Manifest

## Existing Template Candidates

| Role | Path | Status |
|---|---|---|
| Side-scrolling level | `/Game/Variant_SideScrolling/Lvl_SideScrolling` | Candidate source |
| Side-scrolling character | `/Game/Variant_SideScrolling/Blueprints/BP_SideScrollingCharacter` | Candidate source |
| Side-scrolling game mode | `/Game/Variant_SideScrolling/Blueprints/BP_SideScrollingGameMode` | Candidate source |
| Basic collectible | `/Game/Variant_SideScrolling/Blueprints/Items/BP_SideScrollingPickup` | Candidate source |
| Moving platform | `/Game/Variant_SideScrolling/Blueprints/Items/BP_SideScrollingMovingPlatform` | Candidate source |
| Soft platform | `/Game/Variant_SideScrolling/Blueprints/Items/BP_SideScrollingSoftPlatform` | Candidate source |
| Hazard floor | `/Game/Variant_Combat/Blueprints/Interactables/BP_CombatLavaFloor` | Candidate reference |

## Created / Duplicated Prototype Assets

| Asset | Priority | Notes |
|---|---|---|
| `/Game/StarballRun/Maps/Lvl_Starball_FirstPlayable` | High | Duplicated from `Lvl_SideScrolling` |
| `/Game/StarballRun/Blueprints/BP_StarballCharacter` | High | Duplicated from template character |
| `/Game/StarballRun/Blueprints/BP_StarballGameMode` | High | Duplicated from template game mode |
| `/Game/StarballRun/Blueprints/BP_StarballPlayerController` | High | Duplicated from template controller |
| `/Game/StarballRun/Blueprints/Items/BP_StarballCollectible` | High | Duplicated, compile succeeded |
| `/Game/StarballRun/Blueprints/Items/BP_StarballMovingPlatform` | High | Duplicated, compile succeeded |
| `/Game/StarballRun/Blueprints/Items/BP_StarballSoftPlatform` | Medium | Duplicated, compile succeeded |

## Planned Prototype Assets

| Asset | Priority | Notes |
|---|---|---|
| `BP_StarballHazard` | High | Failure condition prototype |
| `BP_StarballGoalGate` | High | Clear condition prototype |
| `BP_StarballCourseManager` | Medium | Timer, respawn, score, result flow |

## v0.3 Gameplay Object Targets

Detailed production definitions and modeling references live in `../art/gameplay_objects/gameplay_object_asset_pipeline.md`.

| Object | Mesh | Material / Material Instance | VFX | Blueprint |
|---|---|---|---|---|
| Star shard | `SM_SR_StarShard_A` | `MI_SR_StarShard_Gold` | `NS_SR_Collect_StarShard` | `BP_SR_StarShardPickup` |
| Energy orb | `SM_SR_EnergyOrb_Shell_A`, `SM_SR_EnergyOrb_Core_A` | `MI_SR_EnergyOrb_Glass`, `MI_SR_EnergyOrb_Core` | `NS_SR_Collect_EnergyOrb` | `BP_SR_EnergyOrbPickup` |
| Hazard device | `SM_SR_HazardDevice_A` | `MI_SR_HazardDevice_Body`, `MI_SR_HazardDevice_HotCore` | `NS_SR_HazardWarningRing`, `NS_SR_HazardHeat` | `BP_SR_HazardDevice` |
| Goal gate | `SM_SR_GoalGate_A`, `SM_SR_GoalGate_PortalDisc_A` | `MI_SR_GoalGate_Stone`, `MI_SR_GoalGate_Gold`, `MI_SR_GoalGate_Portal` | `NS_SR_GoalGate_Idle`, `NS_SR_GoalGate_Clear` | `BP_SR_GoalGate` |
| Basic platform kit | `SM_SR_Platform_1x1_A`, `SM_SR_Platform_1x2_A`, `SM_SR_Platform_Edge_A`, `SM_SR_Platform_Corner_A` | `MI_SR_Platform_StoneMetal`, `MI_SR_Platform_GoldTrim` | `NS_SR_Platform_EdgeGlow` | `BP_SR_PlatformStatic` |
| Moving platform | `SM_SR_MovingPlatform_A`, `SM_SR_MovingPlatform_EnergyRail_A` | `MI_SR_MovingPlatform_Body`, `MI_SR_MovingPlatform_Energy` | `NS_SR_MovingPlatform_Trail` | `BP_SR_MovingPlatform` |
| Platform lift | `SM_SR_PlatformLiftBase_A`, `SM_SR_PlatformLiftColumn_A`, `SM_SR_PlatformLiftGuideRail_A`, `SM_SR_PlatformLiftGear_A`, `SM_SR_PlatformLiftGauge_A`, `SM_SR_PlatformLiftTopMount_A` | `MI_SR_PlatformLift_Body`, `MI_SR_PlatformLift_Energy` | `NS_SR_PlatformLift_EnergyPulse` | `BP_SR_PlatformLiftActuator` |

## Unreal Folder Rules

| Path | Purpose |
|---|---|
| `/Game/StarballRun/Maps` | Starball Run levels |
| `/Game/StarballRun/Blueprints` | Game mode, player, and system Blueprints |
| `/Game/StarballRun/Blueprints/Items` | v0.2 prototype item Blueprints |
| `/Game/StarballRun/Blueprints/GameplayObjects` | v0.3 gameplay object Blueprints |
| `/Game/StarballRun/Art/Meshes/GameplayObjects` | Gameplay object static meshes |
| `/Game/StarballRun/Art/Materials/GameplayObjects` | Gameplay object material instances |
| `/Game/StarballRun/Art/VFX/GameplayObjects` | Gameplay object Niagara systems |

## Non-Asset Prefixes

| Text | Meaning |
|---|---|
| `BP_Starball` | Prototype Blueprint prefix, not a standalone asset |
| `BP_SR_` | Gameplay object Blueprint prefix, not a standalone asset |
| `SM_SR_` | Static mesh prefix, not a standalone asset |
| `MI_SR_` | Material instance prefix, not a standalone asset |
| `NS_SR_` | Niagara prefix, not a standalone asset |
| `SBR_*` | Actor label rule, not an Unreal asset |
