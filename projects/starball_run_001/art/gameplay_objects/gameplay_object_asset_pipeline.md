# 게임플레이 오브젝트 에셋 제작 파이프라인

상태: 1차 제작 확정

## 목적

`별공 런` v0.3 아트 vertical slice에 들어갈 게임플레이 오브젝트를 Unreal에 올릴 실제 에셋 단위로 정리한다.

이 문서는 컨셉 이미지와 오브젝트 컨셉 문서를 모델링, 머티리얼, VFX, 블루프린트 제작 작업으로 변환하기 위한 기준이다.

## 출처

- 오브젝트 컨셉: `gameplay_object_concepts.md`
- 전체 아트 방향: `../direction/art_direction.md`
- 에셋 브리프: `../production/asset_brief.md`
- 기준 이미지: `images/concept_reference/core_objects_v002.png`

## 1차 제작 확정 범위

| ID | 오브젝트 | 게임플레이 역할 | 3D 모델링 대상 | v0.3 포함 |
|---|---|---|---|---|
| GPO-COL-001 | 별 조각 | 기본 수집물, 경로 안내 | 예 | 필수 |
| GPO-COL-002 | 에너지 공 | 위험 보상 수집물 | 예 | 필수 |
| GPO-HAZ-001 | 위험 장치 | 접촉 실패/리스폰 장애물 | 예 | 필수 |
| GPO-GOAL-001 | 골 게이트 | 스테이지 클리어 지점 | 예 | 필수 |
| GPO-PLAT-001 | 기본 발판 키트 | 이동 경로와 착지면 | 예 | 필수 |
| GPO-PLAT-002 | 이동 발판 장치 | 움직이는 발판 판독 | 예 | 필수 |
| GPO-PLAT-003 | 발판 높이 조절 장치 | 발판의 수직 이동/고저차 판독 | 예 | 필수 |

## Unreal 업로드 에셋 목록

| 오브젝트 | Mesh | Material / Material Instance | VFX | Blueprint |
|---|---|---|---|---|
| 별 조각 | `SM_SR_StarShard_A` | `MI_SR_StarShard_Gold` | `NS_SR_Collect_StarShard` | `BP_SR_StarShardPickup` |
| 에너지 공 | `SM_SR_EnergyOrb_Shell_A`, `SM_SR_EnergyOrb_Core_A` | `MI_SR_EnergyOrb_Glass`, `MI_SR_EnergyOrb_Core` | `NS_SR_Collect_EnergyOrb` | `BP_SR_EnergyOrbPickup` |
| 위험 장치 | `SM_SR_HazardDevice_A` | `MI_SR_HazardDevice_Body`, `MI_SR_HazardDevice_HotCore` | `NS_SR_HazardWarningRing`, `NS_SR_HazardHeat` | `BP_SR_HazardDevice` |
| 골 게이트 | `SM_SR_GoalGate_A`, `SM_SR_GoalGate_PortalDisc_A` | `MI_SR_GoalGate_Stone`, `MI_SR_GoalGate_Gold`, `MI_SR_GoalGate_Portal` | `NS_SR_GoalGate_Idle`, `NS_SR_GoalGate_Clear` | `BP_SR_GoalGate` |
| 기본 발판 키트 | `SM_SR_Platform_1x1_A`, `SM_SR_Platform_1x2_A`, `SM_SR_Platform_Edge_A`, `SM_SR_Platform_Corner_A` | `MI_SR_Platform_StoneMetal`, `MI_SR_Platform_GoldTrim` | 없음 또는 `NS_SR_Platform_EdgeGlow` | `BP_SR_PlatformStatic` |
| 이동 발판 장치 | `SM_SR_MovingPlatform_A`, `SM_SR_MovingPlatform_EnergyRail_A` | `MI_SR_MovingPlatform_Body`, `MI_SR_MovingPlatform_Energy` | `NS_SR_MovingPlatform_Trail` | `BP_SR_MovingPlatform` |
| 발판 높이 조절 장치 | `SM_SR_PlatformLiftBase_A`, `SM_SR_PlatformLiftColumn_A`, `SM_SR_PlatformLiftGuideRail_A`, `SM_SR_PlatformLiftGear_A`, `SM_SR_PlatformLiftGauge_A`, `SM_SR_PlatformLiftTopMount_A` | `MI_SR_PlatformLift_Body`, `MI_SR_PlatformLift_Energy` | `NS_SR_PlatformLift_EnergyPulse` | `BP_SR_PlatformLiftActuator` |

## Unreal 경로

| 종류 | 경로 |
|---|---|
| Mesh | `/Game/StarballRun/Art/Meshes/GameplayObjects` |
| Material | `/Game/StarballRun/Art/Materials/GameplayObjects` |
| VFX | `/Game/StarballRun/Art/VFX/GameplayObjects` |
| Blueprint | `/Game/StarballRun/Blueprints/GameplayObjects` |

## 에셋 상세 정의

이름만 있는 에셋을 만들지 않기 위해, 아래 정의를 제작 단위의 기준으로 삼는다. 전체 프로젝트의 authoritative manifest는 `../../project_memory/asset_manifest.md`이며, 이 문서는 게임플레이 오브젝트 제작자가 바로 볼 수 있는 작업용 상세표다.

### Blueprint

| Blueprint | 실제 역할 | 포함해야 하는 주요 컴포넌트 | 완료 기준 |
|---|---|---|---|
| `BP_SR_StarShardPickup` | 기본 경로를 안내하는 별 조각 수집 액터 | 별 조각 mesh, overlap collision, 수집 VFX trigger | 작은 크기에서도 금색 파편 수집물로 읽히고 수집 시 사라짐 |
| `BP_SR_EnergyOrbPickup` | 위험한 위치에 놓이는 보너스 수집 액터 | shell mesh, core mesh, overlap collision, pulse VFX trigger | 별 조각과 다른 실루엣/색으로 보이고 더 가치 있어 보임 |
| `BP_SR_HazardDevice` | 접촉 시 실패/리스폰을 유발하는 위험 액터 | hazard mesh, hazard collision volume, warning ring VFX | 실제 판정 범위가 보기보다 넓거나 좁아 보이지 않음 |
| `BP_SR_GoalGate` | 클리어 지점 액터 | gate frame mesh, portal disc mesh, clear overlap volume, idle/clear VFX | 멀리서도 도착지로 읽히고, 클리어 판정 위치가 명확함 |
| `BP_SR_PlatformStatic` | 정적 착지면 액터 | platform mesh, simple box collision | 배경 장식이 아니라 밟을 수 있는 표면으로 즉시 읽힘 |
| `BP_SR_MovingPlatform` | 수평/경로 이동 발판 액터 | platform mesh, energy rail mesh, movement timeline/component, optional trail VFX | 이동 발판임을 하단 레일/청록 장치로 알 수 있음 |
| `BP_SR_PlatformLiftActuator` | 발판을 수직으로 이동시키는 리프트 시스템 액터 | fixed base, variable column, guide rail, gear, gauge, top mount, platform mesh | 낮은 위치/높은 위치/이동 중 상태가 시각적으로 구분됨 |

### Static Mesh

| Mesh | 실제 제작물 | 파츠/형태 | 충돌/피벗 기준 |
|---|---|---|---|
| `SM_SR_StarShard_A` | 별 조각 pickup 표시 메시 | 큰 파편 1개와 작은 보조 파편 2~3개가 모인 금색 crystal | pivot은 중심 파편 중앙. 충돌은 Blueprint overlap이 담당 |
| `SM_SR_EnergyOrb_Shell_A` | 에너지 공 외부 shell | 투명한 청록 유리 구체, rim이 빛나는 얇은 외피 | pivot은 구체 중심. gameplay collision 없음 |
| `SM_SR_EnergyOrb_Core_A` | 에너지 공 내부 별핵 | shell 안에 떠 있는 작은 별 모양 emissive core | shell과 같은 중심 pivot. gameplay collision 없음 |
| `SM_SR_HazardDevice_A` | 위험 장치 본체 | 검은 금속 body, 주황 hot core, 회전 링, 방열판 | pivot은 body 중심. 판정은 별도 collision volume이 담당 |
| `SM_SR_GoalGate_A` | 골 게이트 프레임 | 밝은 석재 아치, 좌우 기둥, 금색 trim, 상단 별핵 | pivot은 base 중앙 하단. clear 판정은 별도 volume이 담당 |
| `SM_SR_GoalGate_PortalDisc_A` | 골 게이트 포털 표면 | frame 안쪽의 원형 disc 또는 얇은 plane | pivot은 portal 중심. collision 없음 |
| `SM_SR_Platform_1x1_A` | 기본 발판 1칸 모듈 | 한 명의 플레이어가 안정적으로 착지하는 기본 slab. 상단 석재 panel, 남색 금속 frame, 금색 corner cap 포함 | pivot은 tile 중앙. 상단은 평평한 box collision. grid 1칸 기준 |
| `SM_SR_Platform_1x2_A` | 기본 발판 2칸 모듈 | `SM_SR_Platform_1x1_A`를 두 칸 길이로 확장한 긴 착지면 | pivot은 전체 중앙. collision은 2칸 길이 box |
| `SM_SR_Platform_Edge_A` | 발판 가장자리 trim | 발판 side를 마감하는 좁은 남색/금색 strip | 단독 collision 없음. 본체 발판에 부착되는 장식/시각 판독 파츠 |
| `SM_SR_Platform_Corner_A` | 발판 모서리 cap | 금색 모서리 보호구/장식 cap | 단독 collision 없음. 모듈 조립용 |
| `SM_SR_MovingPlatform_A` | 이동 발판 본체 | 기본 발판보다 기계 장치가 붙은 platform body | pivot은 이동 경로 기준 중앙. 상단 collision 담당 |
| `SM_SR_MovingPlatform_EnergyRail_A` | 이동 발판 에너지 레일 | 하단 또는 측면의 청록 발광 rail/guide | collision 없음. 이동 가능성을 알려주는 시각 파츠 |
| `SM_SR_PlatformLiftBase_A` | 리프트 고정 베이스 | 바닥/벽에 붙는 석재/금속 base block | pivot은 base 중앙 하단. 움직이지 않음 |
| `SM_SR_PlatformLiftColumn_A` | 리프트 가변 컬럼 | 2~3단 telescope column 또는 segment column | pivot은 column 하단. 높이에 맞춰 scale 또는 segment 노출 |
| `SM_SR_PlatformLiftGuideRail_A` | 리프트 수직 가이드 레일 | 좌우에 배치되는 고정 rail | collision 없음 또는 장식 collision. 이동 축을 보여줌 |
| `SM_SR_PlatformLiftGear_A` | 리프트 구동 기어 | 큰 금색 gear와 보조 기어 | pivot은 회전 중심. 이동 중 회전 animation 대상 |
| `SM_SR_PlatformLiftGauge_A` | 리프트 에너지 게이지 | 청록 발광 vertical gauge/panel | collision 없음. 현재 높이/동작 상태 표시 |
| `SM_SR_PlatformLiftTopMount_A` | 리프트 상단 마운트 | 발판과 컬럼을 연결하는 bracket/socket | `TopMount` 하위에 배치되어 발판과 함께 이동 |

### Material Instance

| Material Instance | 적용 대상 | 제작 기준 |
|---|---|---|
| `MI_SR_StarShard_Gold` | `SM_SR_StarShard_A` | 금색 crystal/metal, 강한 edge emissive |
| `MI_SR_EnergyOrb_Glass` | `SM_SR_EnergyOrb_Shell_A` | 청록 투명 유리, rim emissive |
| `MI_SR_EnergyOrb_Core` | `SM_SR_EnergyOrb_Core_A` | 밝은 청록/백색 star core emissive |
| `MI_SR_HazardDevice_Body` | `SM_SR_HazardDevice_A` body | 검은 금속/gunmetal |
| `MI_SR_HazardDevice_HotCore` | `SM_SR_HazardDevice_A` core/ring | 주황/빨강 warning emissive |
| `MI_SR_GoalGate_Stone` | `SM_SR_GoalGate_A` stone parts | 밝은 석재, 낮은 채도 |
| `MI_SR_GoalGate_Gold` | `SM_SR_GoalGate_A` trim | 금색 trim, 높은 highlight |
| `MI_SR_GoalGate_Portal` | `SM_SR_GoalGate_PortalDisc_A` | 보라/흰색 portal emissive |
| `MI_SR_Platform_StoneMetal` | platform slab/frame | 석재 top panel과 남색 금속 frame |
| `MI_SR_Platform_GoldTrim` | platform edge/corner | 금색 corner cap과 trim |
| `MI_SR_MovingPlatform_Body` | `SM_SR_MovingPlatform_A` | 움직이는 발판 body용 석재/금속 |
| `MI_SR_MovingPlatform_Energy` | `SM_SR_MovingPlatform_EnergyRail_A` | 청록 rail emissive |
| `MI_SR_PlatformLift_Body` | lift base/column/gear | 리프트 body용 석재/금속/금색 trim |
| `MI_SR_PlatformLift_Energy` | lift gauge/energy strip | 청록 energy gauge emissive |

### Niagara / VFX

| VFX | 적용 대상 | 제작 기준 |
|---|---|---|
| `NS_SR_Collect_StarShard` | `BP_SR_StarShardPickup` | 수집 순간 금색 별가루가 짧게 모이며 사라짐 |
| `NS_SR_Collect_EnergyOrb` | `BP_SR_EnergyOrbPickup` | 청록 원형 pulse 1회와 작은 star speck |
| `NS_SR_HazardWarningRing` | `BP_SR_HazardDevice` | 위험 판정 범위를 미리 보여주는 주황 ring/arc |
| `NS_SR_HazardHeat` | `BP_SR_HazardDevice` | hot core 주변 열기 shimmer |
| `NS_SR_GoalGate_Idle` | `BP_SR_GoalGate` | 대기 상태 portal의 약한 보라/흰색 glow |
| `NS_SR_GoalGate_Clear` | `BP_SR_GoalGate` | 클리어 순간 별가루가 portal로 모이는 1초 내외 효과 |
| `NS_SR_Platform_EdgeGlow` | platform kit | 발판 edge가 배경에서 묻히지 않게 하는 낮은 강도 glow |
| `NS_SR_MovingPlatform_Trail` | `BP_SR_MovingPlatform` | 이동 중 하단/후방에 남는 청록 trail |
| `NS_SR_PlatformLift_EnergyPulse` | `BP_SR_PlatformLiftActuator` | 이동 시작/정지 때 column/gauge를 흐르는 청록 pulse |

## 공통 제작 규칙

- 충돌 범위가 게임플레이 판정보다 작아 보이면 안 된다.
- 수집물과 위험물은 색뿐 아니라 실루엣으로도 구분되어야 한다.
- 모델링은 v0.3에서 low-poly 또는 stylized mid-poly 기준으로 시작한다.
- 발판 상단면은 실제 플레이어가 밟는 면으로 즉시 읽혀야 한다.
- VFX는 메시 제작 완료 후 추가하되, 위험 범위와 수집 피드백은 설계에서 먼저 예약한다.
- 에셋 이름은 `SR` prefix를 사용하고, 템플릿 에셋을 덮어쓰지 않는다.

## 모델링용 3면도 reference

아래 이미지는 3D 모델링 시작을 위한 Static Mesh별 concept image와 정면/측면/상면 orthographic reference다. 최종 에셋이 아니며 모델러가 비율, 실루엣, 분리 파츠를 해석하기 위한 제작 기준이다.

현재 기준 reference는 메시 단위로 분리된 아래 경로를 따른다.

- Concept image: `images/concept_reference/static_meshes/<mesh_lower>_concept_v001.png`
- Orthographic image: `images/modeling_reference/static_meshes/<mesh_lower>_orthographic_v001.png`

기존 묶음형 3면도 reference인 `gameplay_star_shard_orthographic_v001.png`, `gameplay_energy_orb_orthographic_v001.png`, `gameplay_hazard_device_orthographic_v001.png`, `gameplay_goal_gate_orthographic_v001.png`, `gameplay_platform_kit_orthographic_v001.png`, `gameplay_moving_platform_orthographic_v001.png`, `gameplay_platform_lift_system_tripo3d_orthographic_v003.png`는 `images/legacy/modeling_reference_pre_mesh_split/`로 이동된 legacy reference다. 해당 파일들은 메시 분리 전 제작 맥락을 확인하기 위한 과거 자료이며, 현재 모델링 기준으로 사용하지 않는다.

| Mesh | Concept image | Modeling reference | 모델링 메모 |
|---|---|---|---|
| `SM_SR_StarShard_A` | `images/concept_reference/static_meshes/sm_sr_star_shard_a_concept_v001.png` | `images/modeling_reference/static_meshes/sm_sr_star_shard_a_orthographic_v001.png` | 중심 파편 1개와 작은 보조 파편 2~3개. pivot은 중심 파편 중앙 |
| `SM_SR_EnergyOrb_Shell_A` | `images/concept_reference/static_meshes/sm_sr_energy_orb_shell_a_concept_v001.png` | `images/modeling_reference/static_meshes/sm_sr_energy_orb_shell_a_orthographic_v001.png` | 외부 투명 구체 shell. 내부 core와 별도 메시로 제작 |
| `SM_SR_EnergyOrb_Core_A` | `images/concept_reference/static_meshes/sm_sr_energy_orb_core_a_concept_v001.png` | `images/modeling_reference/static_meshes/sm_sr_energy_orb_core_a_orthographic_v001.png` | shell 안에 배치되는 별핵 emissive core |
| `SM_SR_HazardDevice_A` | `images/concept_reference/static_meshes/sm_sr_hazard_device_a_concept_v001.png` | `images/modeling_reference/static_meshes/sm_sr_hazard_device_a_orthographic_v001.png` | 본체, 회전 링, 주황 코어, 방열판을 판독 가능하게 구성 |
| `SM_SR_GoalGate_A` | `images/concept_reference/static_meshes/sm_sr_goal_gate_a_concept_v001.png` | `images/modeling_reference/static_meshes/sm_sr_goal_gate_a_orthographic_v001.png` | 아치, 좌우 기둥, 금색 trim, 상단 별핵을 포함하는 프레임 |
| `SM_SR_GoalGate_PortalDisc_A` | `images/concept_reference/static_meshes/sm_sr_goal_gate_portal_disc_a_concept_v001.png` | `images/modeling_reference/static_meshes/sm_sr_goal_gate_portal_disc_a_orthographic_v001.png` | 게이트 프레임 안쪽에 들어가는 얇은 원형 portal disc |
| `SM_SR_Platform_1x1_A` | `images/concept_reference/static_meshes/sm_sr_platform_1x1_a_concept_v001.png` | `images/modeling_reference/static_meshes/sm_sr_platform_1x1_a_orthographic_v001.png` | grid 1칸 기준 기본 착지 slab. 상단면은 평평하게 유지 |
| `SM_SR_Platform_1x2_A` | `images/concept_reference/static_meshes/sm_sr_platform_1x2_a_concept_v001.png` | `images/modeling_reference/static_meshes/sm_sr_platform_1x2_a_orthographic_v001.png` | grid 2칸 길이의 긴 착지 slab. pivot은 전체 중앙 |
| `SM_SR_Platform_Edge_A` | `images/concept_reference/static_meshes/sm_sr_platform_edge_a_concept_v001.png` | `images/modeling_reference/static_meshes/sm_sr_platform_edge_a_orthographic_v001.png` | 발판 side를 마감하는 trim 파츠. 단독 collision 없음 |
| `SM_SR_Platform_Corner_A` | `images/concept_reference/static_meshes/sm_sr_platform_corner_a_concept_v001.png` | `images/modeling_reference/static_meshes/sm_sr_platform_corner_a_orthographic_v001.png` | 발판 모서리 cap 파츠. 모듈 조립용 |
| `SM_SR_MovingPlatform_A` | `images/concept_reference/static_meshes/sm_sr_moving_platform_a_concept_v001.png` | `images/modeling_reference/static_meshes/sm_sr_moving_platform_a_orthographic_v001.png` | 이동 발판 본체. 기본 발판과 구분되는 기계 장치 실루엣 필요 |
| `SM_SR_MovingPlatform_EnergyRail_A` | `images/concept_reference/static_meshes/sm_sr_moving_platform_energy_rail_a_concept_v001.png` | `images/modeling_reference/static_meshes/sm_sr_moving_platform_energy_rail_a_orthographic_v001.png` | 이동 가능성을 알려주는 하단 또는 측면 청록 energy rail |
| `SM_SR_PlatformLiftBase_A` | `images/concept_reference/static_meshes/sm_sr_platform_lift_base_a_concept_v001.png` | `images/modeling_reference/static_meshes/sm_sr_platform_lift_base_a_orthographic_v001.png` | 월드에 고정되는 리프트 base block. pivot은 base 중앙 하단 |
| `SM_SR_PlatformLiftColumn_A` | `images/concept_reference/static_meshes/sm_sr_platform_lift_column_a_concept_v001.png` | `images/modeling_reference/static_meshes/sm_sr_platform_lift_column_a_orthographic_v001.png` | 높이에 맞춰 scale 또는 segment 노출되는 telescope column |
| `SM_SR_PlatformLiftGuideRail_A` | `images/concept_reference/static_meshes/sm_sr_platform_lift_guide_rail_a_concept_v001.png` | `images/modeling_reference/static_meshes/sm_sr_platform_lift_guide_rail_a_orthographic_v001.png` | 고정 수직 guide rail. 발판 이동 축을 보여주는 시각 파츠 |
| `SM_SR_PlatformLiftGear_A` | `images/concept_reference/static_meshes/sm_sr_platform_lift_gear_a_concept_v001.png` | `images/modeling_reference/static_meshes/sm_sr_platform_lift_gear_a_orthographic_v001.png` | 이동 중 회전 animation 대상 gear. pivot은 회전 중심 |
| `SM_SR_PlatformLiftGauge_A` | `images/concept_reference/static_meshes/sm_sr_platform_lift_gauge_a_concept_v001.png` | `images/modeling_reference/static_meshes/sm_sr_platform_lift_gauge_a_orthographic_v001.png` | 현재 높이/동작 상태를 표시하는 청록 energy gauge |
| `SM_SR_PlatformLiftTopMount_A` | `images/concept_reference/static_meshes/sm_sr_platform_lift_top_mount_a_concept_v001.png` | `images/modeling_reference/static_meshes/sm_sr_platform_lift_top_mount_a_orthographic_v001.png` | 발판과 컬럼을 연결하는 bracket/socket. 발판과 함께 이동 |

## 발판 조립 규칙

발판의 시각 구조는 아래처럼 조립한다.

```text
기본 발판 상단 모듈
  + 선택: 이동 발판 에너지 레일
  + 선택: 높이 조절 장치
```

- `BP_SR_PlatformStatic`은 기본 발판 키트만 사용한다.
- `BP_SR_MovingPlatform`은 기본 발판 키트와 이동 발판 에너지 레일을 조립한다.
- `BP_SR_PlatformLiftActuator`는 기본 발판 또는 이동 발판 하단에 붙어 수직 이동/고저차를 표현한다.
- 높이 조절 장치는 배경 장식이 아니라 플레이어 경로를 바꾸는 게임플레이 장치이므로 `gameplay_objects` 소유로 관리한다.

## 높이 조절 Blueprint 구조

발판 높이 조절 장치는 Static Mesh별 concept/orthographic reference를 기준으로 제작하고, 실제 높이 조절은 아래 Blueprint 조립 구조가 담당한다.

| Component / Property | 역할 |
|---|---|
| `Root` | 리프트 기준점. 월드에 고정되는 base |
| `LiftBaseMesh` | `SM_SR_PlatformLiftBase_A`, 움직이지 않는 본체 |
| `LiftColumnMesh` | `SM_SR_PlatformLiftColumn_A`, 높이에 맞춰 segment 노출 또는 Z scale 변경 |
| `LiftGuideRailMesh` | 좌우 고정 가이드 레일. 발판 이동 축을 시각화 |
| `LiftGearMesh` | `SM_SR_PlatformLiftGear_A`, 이동 중 회전 |
| `LiftGaugeMesh` | 청록 에너지 게이지. 현재 동작/높이 상태를 시각화 |
| `TopMount` | 발판을 붙이는 SceneComponent. 실제 Z 이동 대상 |
| `PlatformMesh` | 기본 발판 메시. 충돌은 이 컴포넌트가 담당 |
| `MinHeight` | 가장 낮은 위치 |
| `MaxHeight` | 가장 높은 위치 |
| `TravelTime` | 한 방향 이동 시간 |
| `MoveMode` | 왕복, 트리거식, 단계식 |

동작 기준:

1. `Root`와 `LiftBaseMesh`는 움직이지 않는다.
2. `TopMount`와 그 아래의 `PlatformMesh`가 `MinHeight`와 `MaxHeight` 사이를 이동한다.
3. `LiftColumnMesh`는 현재 높이에 맞춰 늘어나거나 segment를 교체한다.
4. `LiftGuideRailMesh`는 고정되어 이동 축을 보여준다.
5. `LiftGearMesh`는 이동 중에만 회전한다.
6. `LiftGaugeMesh`는 이동 중 강하게, 정지 중 약하게 발광한다.
7. 플레이어 충돌은 `PlatformMesh`가 담당하고, 리프트 본체는 단순 충돌 또는 장식 충돌로 둔다.

## 제작 승인 기준

- 위 목록의 Mesh/Material/VFX/Blueprint 이름과 경로를 v0.3 기준으로 사용한다.
- 모델링은 3면도 reference와 `gameplay_object_concepts.md`의 금지 방향을 함께 따른다.
- 모델링 결과는 `../reviews/`에서 판독성, 충돌 범위, IP 안전성 기준으로 리뷰한다.
