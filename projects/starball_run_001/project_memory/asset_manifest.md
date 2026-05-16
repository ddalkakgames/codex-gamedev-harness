# 에셋 목록

## 기존 활용 후보

| 역할 | 경로 | 상태 |
|---|---|---|
| 사이드 스크롤링 레벨 | `/Game/Variant_SideScrolling/Lvl_SideScrolling` | 후보 |
| 사이드 스크롤링 캐릭터 | `/Game/Variant_SideScrolling/Blueprints/BP_SideScrollingCharacter` | 후보 |
| 사이드 스크롤링 게임모드 | `/Game/Variant_SideScrolling/Blueprints/BP_SideScrollingGameMode` | 후보 |
| 기본 수집물 | `/Game/Variant_SideScrolling/Blueprints/Items/BP_SideScrollingPickup` | 후보 |
| 움직이는 발판 | `/Game/Variant_SideScrolling/Blueprints/Items/BP_SideScrollingMovingPlatform` | 후보 |
| 소프트 발판 | `/Game/Variant_SideScrolling/Blueprints/Items/BP_SideScrollingSoftPlatform` | 후보 |
| 위험 바닥 | `/Game/Variant_Combat/Blueprints/Interactables/BP_CombatLavaFloor` | 후보 |

## 신규 제작/복제됨

| 에셋 | 우선순위 | 비고 |
|---|---|---|
| `/Game/StarballRun/Maps/Lvl_Starball_FirstPlayable` | 높음 | `Lvl_SideScrolling` 복제 |
| `/Game/StarballRun/Blueprints/BP_StarballCharacter` | 높음 | `BP_SideScrollingCharacter` 복제 |
| `/Game/StarballRun/Blueprints/BP_StarballGameMode` | 높음 | `BP_SideScrollingGameMode` 복제 |
| `/Game/StarballRun/Blueprints/BP_StarballPlayerController` | 높음 | `BP_SideScrollingPlayerController` 복제 |
| `/Game/StarballRun/Blueprints/Items/BP_StarballCollectible` | 높음 | `BP_SideScrollingPickup` 복제, 컴파일 성공 |
| `/Game/StarballRun/Blueprints/Items/BP_StarballMovingPlatform` | 높음 | `BP_SideScrollingMovingPlatform` 복제, 컴파일 성공 |
| `/Game/StarballRun/Blueprints/Items/BP_StarballSoftPlatform` | 중간 | `BP_SideScrollingSoftPlatform` 복제, 컴파일 성공 |

## 신규 제작 예정

| 에셋 | 우선순위 | 비고 |
|---|---|---|
| `BP_StarballHazard` | 높음 | 실패 조건 |
| `BP_StarballGoalGate` | 높음 | 클리어 조건 |
| `BP_StarballCourseManager` | 중간 | v0.3 확장 가능 |

## 전용 아트 제작 예정

| 에셋 | Unreal 경로 | 버전 | 비고 |
|---|---|---|---|
| 플레이어 캐릭터 proxy | `/Game/StarballRun/Art/Meshes` | v0.3 | 실루엣 우선 |
| 별 조각 메시/머티리얼 | `/Game/StarballRun/Art/Meshes`, `/Game/StarballRun/Art/Materials` | v0.3 | 기본 경로 안내 |
| 에너지 공 메시/머티리얼 | `/Game/StarballRun/Art/Meshes`, `/Game/StarballRun/Art/Materials` | v0.3 | 보너스 수집물 |
| 위험 장애물 메시 | `/Game/StarballRun/Art/Meshes` | v0.3 | 충돌 범위 예측 가능 |
| 골 게이트 메시/VFX | `/Game/StarballRun/Art/Meshes`, `/Game/StarballRun/Art/VFX` | v0.3 | 도착지 인식 |
| 플랫폼 키트 | `/Game/StarballRun/Art/Meshes` | v0.3 | 기본/가장자리/움직이는 발판/높이 조절 장치 |
| 배경 키트 | `/Game/StarballRun/Art/Meshes`, `/Game/StarballRun/Art/Textures` | v0.4 | 판독성 유지 |

## 게임플레이 오브젝트 1차 제작 확정

상세 제작 파이프라인과 3면도 reference는 `../art/gameplay_objects/gameplay_object_asset_pipeline.md`를 따른다.

| 오브젝트 | Mesh | Material / Material Instance | VFX | Blueprint |
|---|---|---|---|---|
| 별 조각 | `SM_SR_StarShard_A` | `MI_SR_StarShard_Gold` | `NS_SR_Collect_StarShard` | `BP_SR_StarShardPickup` |
| 에너지 공 | `SM_SR_EnergyOrb_Shell_A`, `SM_SR_EnergyOrb_Core_A` | `MI_SR_EnergyOrb_Glass`, `MI_SR_EnergyOrb_Core` | `NS_SR_Collect_EnergyOrb` | `BP_SR_EnergyOrbPickup` |
| 위험 장치 | `SM_SR_HazardDevice_A` | `MI_SR_HazardDevice_Body`, `MI_SR_HazardDevice_HotCore` | `NS_SR_HazardWarningRing`, `NS_SR_HazardHeat` | `BP_SR_HazardDevice` |
| 골 게이트 | `SM_SR_GoalGate_A`, `SM_SR_GoalGate_PortalDisc_A` | `MI_SR_GoalGate_Stone`, `MI_SR_GoalGate_Gold`, `MI_SR_GoalGate_Portal` | `NS_SR_GoalGate_Idle`, `NS_SR_GoalGate_Clear` | `BP_SR_GoalGate` |
| 기본 발판 키트 | `SM_SR_Platform_1x1_A`, `SM_SR_Platform_1x2_A`, `SM_SR_Platform_Edge_A`, `SM_SR_Platform_Corner_A` | `MI_SR_Platform_StoneMetal`, `MI_SR_Platform_GoldTrim` | `NS_SR_Platform_EdgeGlow` | `BP_SR_PlatformStatic` |
| 이동 발판 장치 | `SM_SR_MovingPlatform_A`, `SM_SR_MovingPlatform_EnergyRail_A` | `MI_SR_MovingPlatform_Body`, `MI_SR_MovingPlatform_Energy` | `NS_SR_MovingPlatform_Trail` | `BP_SR_MovingPlatform` |
| 발판 높이 조절 장치 | `SM_SR_PlatformLiftBase_A`, `SM_SR_PlatformLiftColumn_A`, `SM_SR_PlatformLiftGuideRail_A`, `SM_SR_PlatformLiftGear_A`, `SM_SR_PlatformLiftGauge_A`, `SM_SR_PlatformLiftTopMount_A` | `MI_SR_PlatformLift_Body`, `MI_SR_PlatformLift_Energy` | `NS_SR_PlatformLift_EnergyPulse` | `BP_SR_PlatformLiftActuator` |

## 전수조사 결과

2026-05-14 기준 `starball_run_001` 문서에 등장하는 Unreal 에셋명은 아래 네 종류로 분류한다.

| 분류 | prefix / 경로 | 의미 | 정의 상태 |
|---|---|---|---|
| 템플릿 원본 후보 | `/Game/Variant_*`, `/Game/ThirdPerson/*` | 기존 UE 템플릿/검증 월드. StarballRun 소유 아님 | 후보 역할만 정의 |
| v0.2 prototype | `BP_Starball...`, `/Game/StarballRun/Blueprints/Items/*` | 템플릿 복제 기반 첫 플레이어블 검증용 | prototype 역할 정의 |
| v0.3 gameplay object target | `BP_SR_*`, `SM_SR_*`, `MI_SR_*`, `NS_SR_*` | 전용 아트 vertical slice 제작 대상 | 아래 상세 정의 |
| 폴더/상위 경로 | `/Game/StarballRun/Art/*`, `/Game/StarballRun/Blueprints/*` | 에셋 저장 위치 | 경로 규칙으로 정의 |

이 문서 이후 새 에셋명을 추가할 때는 이름만 추가하지 않고, 아래 표 수준의 실체 정의를 함께 작성한다.

정리 결과, 현재 문서 검색에서 잡히는 `BP_*`, `SM_*`, `MI_*`, `NS_*`, `Lvl_*` 표기는 모두 아래 상세 정의에 포함되어 있거나, 다음 섹션의 접두어/표기 예시로 분류되어 있다.

## 에셋이 아닌 접두어 / 표기 예시

아래 항목은 문서 검색에서 에셋명처럼 잡히지만 실제 제작 대상 에셋이 아니다. 단독 파일로 만들지 않는다.

| 표기 | 실제 의미 | 처리 |
|---|---|---|
| `BP_Starball` | `BP_StarballCharacter`, `BP_StarballGameMode` 같은 v0.2 prototype Blueprint 접두어 | standalone Blueprint 금지 |
| `BP_SR_` | `BP_SR_GoalGate` 같은 v0.3 gameplay object Blueprint 접두어 | standalone Blueprint 금지 |
| `SM_SR_` | StarballRun static mesh 접두어 | standalone mesh 금지 |
| `MI_SR_` | StarballRun material instance 접두어 | standalone material instance 금지 |
| `NS_SR_` | StarballRun Niagara system 접두어 | standalone Niagara system 금지 |
| `Lvl_Starball` | `Lvl_Starball_FirstPlayable` 같은 StarballRun level 접두어 | standalone level 금지 |
| `SBR_*` | 월드에 배치되는 actor label 규칙 | Unreal asset 아님 |

## Unreal 폴더 경로 정의

| 경로 | 용도 | 비고 |
|---|---|---|
| `/Game/StarballRun/Maps` | StarballRun 전용 level 저장 위치 | `Lvl_Starball_FirstPlayable` 소유 |
| `/Game/StarballRun/Blueprints` | StarballRun 시스템/플레이어 Blueprint 위치 | GameMode, PlayerController, CourseManager |
| `/Game/StarballRun/Blueprints/Items` | v0.2 prototype item Blueprint 위치 | 템플릿 복제 기반 수집물/발판 |
| `/Game/StarballRun/Blueprints/GameplayObjects` | v0.3 전용 gameplay object Blueprint 위치 | `BP_SR_*` 사용 |
| `/Game/StarballRun/Art` | StarballRun 전용 아트 루트 | 템플릿 에셋 덮어쓰기 금지 |
| `/Game/StarballRun/Art/Characters/Lumi` | 루미 캐릭터 전용 메시/머티리얼/텍스처 | 캐릭터 하네스 문서 소유 |
| `/Game/StarballRun/Art/Meshes` | 전용 static/skeletal mesh 상위 폴더 | gameplay object는 하위 폴더 사용 |
| `/Game/StarballRun/Art/Meshes/GameplayObjects` | 게임플레이 오브젝트 static mesh 위치 | `SM_SR_*` 사용 |
| `/Game/StarballRun/Art/Materials` | 전용 material/material instance 상위 폴더 | gameplay object는 하위 폴더 사용 |
| `/Game/StarballRun/Art/Materials/GameplayObjects` | 게임플레이 오브젝트 material instance 위치 | `MI_SR_*` 사용 |
| `/Game/StarballRun/Art/Textures` | 전용 texture 위치 | 캐릭터/오브젝트/환경 공용 |
| `/Game/StarballRun/Art/VFX` | 전용 Niagara/VFX 상위 폴더 | gameplay object는 하위 폴더 사용 |
| `/Game/StarballRun/Art/VFX/GameplayObjects` | 게임플레이 오브젝트 Niagara 위치 | `NS_SR_*` 사용 |
| `/Game/StarballRun/UI` | HUD, icon, widget 위치 | v0.4 이후 확장 |
| `/Game/Variant_SideScrolling/*` | UE 템플릿 원본 후보 | StarballRun 소유 아님, 직접 수정 금지 |
| `/Game/Variant_Combat/*` | UE 템플릿 원본 후보 | StarballRun 소유 아님, 직접 수정 금지 |
| `/Game/ThirdPerson/*` | 초기 검증 때 열린 템플릿 월드 | StarballRun 최종 맵 아님 |

## 레벨 / 맵 정의

| 에셋 | 상태 | 정의 | 소유/비고 |
|---|---|---|---|
| `/Game/Variant_SideScrolling/Lvl_SideScrolling` | 외부 후보 | 사이드 스크롤링 템플릿의 원본 맵. StarballRun 첫 플레이어블의 복제 원본 | 수정 금지 |
| `/Game/ThirdPerson/Lvl_ThirdPerson` | 외부 검증 월드 | 2026-05-07 1차 MCP 배치가 임시로 들어간 당시 열린 월드 | StarballRun 최종 맵 아님 |
| `/Game/StarballRun/Maps/Lvl_Starball_FirstPlayable` | v0.2 prototype | 30~60초 수집/회피/골 도달 코스를 담는 첫 플레이어블 전용 맵 | StarballRun 소유 |

## 템플릿 원본 후보 상세 정의

아래 에셋은 StarballRun 전용 에셋의 복제 원본 또는 동작 참고용이다. StarballRun 프로젝트 문서에는 등장하지만, 직접 수정하거나 최종 산출물로 간주하지 않는다.

| 에셋 | 경로 | 실제 의미 | StarballRun에서의 사용 |
|---|---|---|---|
| `BP_SideScrollingCharacter` | `/Game/Variant_SideScrolling/Blueprints/BP_SideScrollingCharacter` | UE 사이드 스크롤링 템플릿 플레이어 캐릭터 | `BP_StarballCharacter` 복제 원본 |
| `BP_SideScrollingGameMode` | `/Game/Variant_SideScrolling/Blueprints/BP_SideScrollingGameMode` | UE 사이드 스크롤링 템플릿 게임모드 | `BP_StarballGameMode` 복제 원본 |
| `BP_SideScrollingPlayerController` | `/Game/Variant_SideScrolling/Blueprints/BP_SideScrollingPlayerController` | UE 사이드 스크롤링 템플릿 플레이어 컨트롤러 | `BP_StarballPlayerController` 복제 원본 |
| `BP_SideScrollingPickup` | `/Game/Variant_SideScrolling/Blueprints/Items/BP_SideScrollingPickup` | 템플릿 수집물 Blueprint | `BP_StarballCollectible` 복제 원본 |
| `BP_SideScrollingMovingPlatform` | `/Game/Variant_SideScrolling/Blueprints/Items/BP_SideScrollingMovingPlatform` | 템플릿 이동 발판 Blueprint | `BP_StarballMovingPlatform` 복제 원본 |
| `BP_SideScrollingSoftPlatform` | `/Game/Variant_SideScrolling/Blueprints/Items/BP_SideScrollingSoftPlatform` | 템플릿 통과형/소프트 발판 Blueprint | `BP_StarballSoftPlatform` 복제 원본 |
| `BP_CombatLavaFloor` | `/Game/Variant_Combat/Blueprints/Interactables/BP_CombatLavaFloor` | Combat 템플릿의 접촉 피해/위험 바닥 Blueprint | `BP_StarballHazard` 또는 `BP_SR_HazardDevice` 실패 판정 참고 후보 |

## Prototype Blueprint 정의

| 에셋 | 경로 | 상태 | 정의 | v0.3 관계 |
|---|---|---|---|---|
| `BP_StarballCharacter` | `/Game/StarballRun/Blueprints/BP_StarballCharacter` | 복제됨 | v0.2 플레이어 조작 prototype. SideScrolling 캐릭터를 StarballRun용으로 복제한 캐릭터 BP | 루미 전용 캐릭터 proxy/최종 모델 통합 대상 |
| `BP_StarballGameMode` | `/Game/StarballRun/Blueprints/BP_StarballGameMode` | 복제됨 | v0.2 게임모드 prototype. 시작/클리어/실패/스코어 흐름의 상위 규칙을 담당 | 유지하면서 HUD/결과 흐름 확장 |
| `BP_StarballPlayerController` | `/Game/StarballRun/Blueprints/BP_StarballPlayerController` | 복제됨 | v0.2 플레이어 입력과 카메라 제어 확장 후보 | 유지 |
| `BP_StarballCollectible` | `/Game/StarballRun/Blueprints/Items/BP_StarballCollectible` | 복제됨 | 별 조각/에너지 공을 임시 데이터/프로퍼티로 구분하는 generic 수집물 prototype | `BP_SR_StarShardPickup`, `BP_SR_EnergyOrbPickup`로 분리 예정 |
| `BP_StarballMovingPlatform` | `/Game/StarballRun/Blueprints/Items/BP_StarballMovingPlatform` | 복제됨 | 템플릿 이동 발판을 StarballRun 코스 배치용으로 복제한 prototype | `BP_SR_MovingPlatform`으로 시각/구조 교체 |
| `BP_StarballSoftPlatform` | `/Game/StarballRun/Blueprints/Items/BP_StarballSoftPlatform` | 복제됨 | 일방향/통과형 발판 후보 prototype | v0.3 필수 아트 범위에서는 보류 |
| `BP_StarballHazard` | `/Game/StarballRun/Blueprints/GameplayObjects/BP_StarballHazard` | 예정 | 접촉 시 리스폰/실패 처리만 검증하는 위험물 prototype | `BP_SR_HazardDevice`로 승격 |
| `BP_StarballGoalGate` | `/Game/StarballRun/Blueprints/GameplayObjects/BP_StarballGoalGate` | 예정 | 클리어 판정 볼륨과 클리어 이벤트를 검증하는 골 prototype | `BP_SR_GoalGate`로 승격 |
| `BP_StarballCourseManager` | `/Game/StarballRun/Blueprints/BP_StarballCourseManager` | 예정 | 타이머, 리스폰 지점, 결과 흐름을 관리하는 코스 단위 manager | 유지 |

## Gameplay Object Blueprint 정의

| 에셋 | 정의 | 핵심 컴포넌트 | 비고 |
|---|---|---|---|
| `BP_SR_StarShardPickup` | 별 조각 수집 전용 액터 | `SM_SR_StarShard_A`, overlap collision, `NS_SR_Collect_StarShard` | 기본 경로 안내 수집물 |
| `BP_SR_EnergyOrbPickup` | 에너지 공 보너스 수집 전용 액터 | `SM_SR_EnergyOrb_Shell_A`, `SM_SR_EnergyOrb_Core_A`, overlap collision, `NS_SR_Collect_EnergyOrb` | 위험 보상 수집물 |
| `BP_SR_HazardDevice` | 접촉 실패/리스폰을 유발하는 위험 장치 액터 | `SM_SR_HazardDevice_A`, hazard collision volume, warning VFX | 표시 메시와 실제 판정 범위를 맞춰야 함 |
| `BP_SR_GoalGate` | 스테이지 클리어 지점 액터 | `SM_SR_GoalGate_A`, `SM_SR_GoalGate_PortalDisc_A`, clear overlap volume | 판정 볼륨과 게이트 표시 메시 분리 |
| `BP_SR_PlatformStatic` | 정적 발판 액터 | platform mesh component, simple collision | 기본/가장자리/코너 파츠 조합 |
| `BP_SR_MovingPlatform` | 수평/경로 이동 발판 액터 | platform mesh, `SM_SR_MovingPlatform_EnergyRail_A`, movement component/Timeline | 수직 리프트와 구분 |
| `BP_SR_PlatformLiftActuator` | 발판을 위아래로 이동시키는 조립형 리프트 액터 | `LiftBaseMesh`, `LiftColumnMesh`, `LiftGuideRailMesh`, `LiftGearMesh`, `LiftGaugeMesh`, `TopMount`, `PlatformMesh` | 실제 이동 대상은 `TopMount + PlatformMesh` |

## Static Mesh 상세 정의

| 에셋 | 실체 정의 | 형태/파츠 | 피벗/충돌 기준 | Reference |
|---|---|---|---|---|
| `SM_SR_StarShard_A` | 별 조각 pickup의 표시 메시 | 깨진 별 파편 모양의 금색 faceted crystal. 중심 파편 1개와 보조 파편 2~3개 | pivot은 중심 파편 중앙. 충돌은 BP overlap sphere/box가 담당 | `art/gameplay_objects/images/modeling_reference/static_meshes/sm_sr_star_shard_a_orthographic_v001.png` |
| `SM_SR_EnergyOrb_Shell_A` | 에너지 공 외부 유리 구체 | 투명/청록 구체 shell, 내부 core가 보이도록 얇은 rim | pivot은 구체 중심. 충돌 없음 또는 BP overlap에 위임 | `art/gameplay_objects/images/modeling_reference/static_meshes/sm_sr_energy_orb_shell_a_orthographic_v001.png` |
| `SM_SR_EnergyOrb_Core_A` | 에너지 공 내부 별핵 | 작은 청록/백색 별핵 메시 | shell과 같은 중심 pivot. 충돌 없음 | `art/gameplay_objects/images/modeling_reference/static_meshes/sm_sr_energy_orb_core_a_orthographic_v001.png` |
| `SM_SR_HazardDevice_A` | 위험 장치 표시 메시 | 검은 금속 본체, 주황 hot core, 회전 링/방열판이 포함된 compact obstacle | pivot은 본체 중심. 실제 판정은 BP hazard volume 기준 | `art/gameplay_objects/images/modeling_reference/static_meshes/sm_sr_hazard_device_a_orthographic_v001.png` |
| `SM_SR_GoalGate_A` | 골 게이트 프레임 메시 | 밝은 석재 아치, 좌우 기둥, 금색 trim, 상단 별핵 frame | pivot은 base 중앙 하단. 판정은 별도 clear overlap volume | `art/gameplay_objects/images/modeling_reference/static_meshes/sm_sr_goal_gate_a_orthographic_v001.png` |
| `SM_SR_GoalGate_PortalDisc_A` | 골 게이트 내부 포털 표시 메시 | 원형 disc 또는 얇은 plane, 보라/흰색 portal material 적용 | pivot은 portal 중심. 충돌 없음 | `art/gameplay_objects/images/modeling_reference/static_meshes/sm_sr_goal_gate_portal_disc_a_orthographic_v001.png` |
| `SM_SR_Platform_1x1_A` | 기본 발판 1칸 모듈 | 플레이어가 밟는 정사각/짧은 직사각 상단 slab. 석재 top panel, 남색 금속 frame, 금색 corner cap 포함 | pivot은 tile 중앙. 상단 collision은 평평한 box. grid 기준 1칸 | `art/gameplay_objects/images/modeling_reference/static_meshes/sm_sr_platform_1x1_a_orthographic_v001.png` |
| `SM_SR_Platform_1x2_A` | 기본 발판 2칸 모듈 | `SM_SR_Platform_1x1_A` 두 칸 길이의 긴 발판 slab | pivot은 전체 중앙. collision은 2칸 길이 box | `art/gameplay_objects/images/modeling_reference/static_meshes/sm_sr_platform_1x2_a_orthographic_v001.png` |
| `SM_SR_Platform_Edge_A` | 발판 가장자리 trim 모듈 | 발판 side를 마감하는 남색/금색 narrow strip | 단독 gameplay collision 없음. 발판 본체 collision에 포함 가능 | `art/gameplay_objects/images/modeling_reference/static_meshes/sm_sr_platform_edge_a_orthographic_v001.png` |
| `SM_SR_Platform_Corner_A` | 발판 corner cap 모듈 | 금색 모서리 마감 장식 파츠 | 단독 gameplay collision 없음. 모듈 조립용 | `art/gameplay_objects/images/modeling_reference/static_meshes/sm_sr_platform_corner_a_orthographic_v001.png` |
| `SM_SR_MovingPlatform_A` | 이동 발판 본체 | 기본 발판보다 이동 장치가 붙은 platform body | pivot은 이동 경로 기준 중앙. 상단 collision 담당 | `art/gameplay_objects/images/modeling_reference/static_meshes/sm_sr_moving_platform_a_orthographic_v001.png` |
| `SM_SR_MovingPlatform_EnergyRail_A` | 이동 발판 하단/측면 에너지 레일 | 청록 발광 rail, side guide module, underside energy bar | collision 없음. 이동 발판임을 시각화 | `art/gameplay_objects/images/modeling_reference/static_meshes/sm_sr_moving_platform_energy_rail_a_orthographic_v001.png` |
| `SM_SR_PlatformLiftBase_A` | 리프트 고정 베이스 | 석재/금속 base block. 월드에 고정되는 기준점 | pivot은 base 중앙 하단. 단순 collision 또는 장식 collision | `art/gameplay_objects/images/modeling_reference/static_meshes/sm_sr_platform_lift_base_a_orthographic_v001.png` |
| `SM_SR_PlatformLiftColumn_A` | 리프트 가변 컬럼 | 2~3단 telescope column 또는 segment 컬럼 | pivot은 column 하단. 현재 높이에 따라 scale/segment 노출 | `art/gameplay_objects/images/modeling_reference/static_meshes/sm_sr_platform_lift_column_a_orthographic_v001.png` |
| `SM_SR_PlatformLiftGuideRail_A` | 리프트 고정 가이드 레일 | 좌우 수직 rail. 발판의 이동 축을 보여주는 실물 파츠 | base 기준 고정. collision 없음 또는 장식 collision | `art/gameplay_objects/images/modeling_reference/static_meshes/sm_sr_platform_lift_guide_rail_a_orthographic_v001.png` |
| `SM_SR_PlatformLiftGear_A` | 리프트 구동 기어 | 베이스 측면의 큰 금색 gear와 보조 기어 | pivot은 회전 중심. 이동 중 회전 animation | `art/gameplay_objects/images/modeling_reference/static_meshes/sm_sr_platform_lift_gear_a_orthographic_v001.png` |
| `SM_SR_PlatformLiftGauge_A` | 리프트 에너지 게이지 | 청록 발광 vertical gauge 또는 small energy panel | collision 없음. 이동 상태/높이 상태 표시 | `art/gameplay_objects/images/modeling_reference/static_meshes/sm_sr_platform_lift_gauge_a_orthographic_v001.png` |
| `SM_SR_PlatformLiftTopMount_A` | 리프트 상단 마운트 | 발판 하단과 컬럼을 연결하는 moving socket/bracket | `TopMount` SceneComponent 하위에 배치. 발판과 함께 이동 | `art/gameplay_objects/images/modeling_reference/static_meshes/sm_sr_platform_lift_top_mount_a_orthographic_v001.png` |

## Material Instance 상세 정의

| 에셋 | 적용 대상 | 정의 |
|---|---|---|
| `MI_SR_StarShard_Gold` | `SM_SR_StarShard_A` | 금색 crystal/metal 혼합. 강한 emissive edge와 투명감 |
| `MI_SR_EnergyOrb_Glass` | `SM_SR_EnergyOrb_Shell_A` | 청록 투명 유리 shell, rim emissive |
| `MI_SR_EnergyOrb_Core` | `SM_SR_EnergyOrb_Core_A` | 밝은 청록/백색 emissive star core |
| `MI_SR_HazardDevice_Body` | `SM_SR_HazardDevice_A` body | 검은 금속/짙은 gunmetal |
| `MI_SR_HazardDevice_HotCore` | `SM_SR_HazardDevice_A` core/ring | 주황/빨강 warning emissive |
| `MI_SR_GoalGate_Stone` | `SM_SR_GoalGate_A` stone parts | 밝은 석재, 낮은 채도 |
| `MI_SR_GoalGate_Gold` | `SM_SR_GoalGate_A` trim | 금색 trim, 높은 명도 highlight |
| `MI_SR_GoalGate_Portal` | `SM_SR_GoalGate_PortalDisc_A` | 보라/흰색 portal emissive |
| `MI_SR_Platform_StoneMetal` | platform slabs/frame | 석재 top panel과 남색 금속 frame의 기본 material set |
| `MI_SR_Platform_GoldTrim` | platform corner/edge caps | 금색 corner cap/trim material |
| `MI_SR_MovingPlatform_Body` | `SM_SR_MovingPlatform_A` | 이동 발판 body용 남색 금속/석재 material |
| `MI_SR_MovingPlatform_Energy` | `SM_SR_MovingPlatform_EnergyRail_A` | 청록 energy rail emissive |
| `MI_SR_PlatformLift_Body` | lift base/column/gear non-emissive | 리프트 body용 남색 금속/석재/금색 trim material |
| `MI_SR_PlatformLift_Energy` | lift gauge/energy strips | 청록 energy gauge/rail emissive |

## Niagara / VFX 상세 정의

| 에셋 | 적용 대상 | 정의 |
|---|---|---|
| `NS_SR_Collect_StarShard` | `BP_SR_StarShardPickup` | 수집 시 금색 별가루가 루미 쪽으로 빨려 들어가는 짧은 효과 |
| `NS_SR_Collect_EnergyOrb` | `BP_SR_EnergyOrbPickup` | 수집 시 청록 원형 pulse 1회와 작은 star speck 효과 |
| `NS_SR_HazardWarningRing` | `BP_SR_HazardDevice` | 위험 판정 범위/예고를 보여주는 주황 ring/arc |
| `NS_SR_HazardHeat` | `BP_SR_HazardDevice` | hot core 주변의 짧은 열기/경고 shimmer |
| `NS_SR_GoalGate_Idle` | `BP_SR_GoalGate` | 비활성/대기 상태 portal의 약한 보라/흰색 glow |
| `NS_SR_GoalGate_Clear` | `BP_SR_GoalGate` | 클리어 순간 별가루가 portal로 모이는 1초 내외 효과 |
| `NS_SR_Platform_EdgeGlow` | `BP_SR_PlatformStatic` 또는 platform kit | 발판 edge가 살짝 읽히도록 하는 낮은 강도 glow. 필수 VFX는 아님 |
| `NS_SR_MovingPlatform_Trail` | `BP_SR_MovingPlatform` | 이동 중 하단/후방에 남는 청록 trail |
| `NS_SR_PlatformLift_EnergyPulse` | `BP_SR_PlatformLiftActuator` | 리프트 이동 시작/정지 시 gauge와 column에 흐르는 청록 pulse |
