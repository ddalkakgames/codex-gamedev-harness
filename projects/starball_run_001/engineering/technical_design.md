# 기술 설계

## 목표

Unreal MCP로 레벨 배치, 블루프린트 생성/수정, 설정 변경을 반복하면서 첫 플레이어블을 만든다.

## 기준 엔진

Unreal Engine 5.7 설치형 엔진.

## 우선 활용 에셋

| 역할 | 후보 경로 |
|---|---|
| 사이드 스크롤링 맵 | `/Game/Variant_SideScrolling/Lvl_SideScrolling` |
| 플레이어 | `/Game/Variant_SideScrolling/Blueprints/BP_SideScrollingCharacter` |
| 게임모드 | `/Game/Variant_SideScrolling/Blueprints/BP_SideScrollingGameMode` |
| 수집물 | `/Game/Variant_SideScrolling/Blueprints/Items/BP_SideScrollingPickup` |
| 움직이는 발판 | `/Game/Variant_SideScrolling/Blueprints/Items/BP_SideScrollingMovingPlatform` |
| 소프트 발판 | `/Game/Variant_SideScrolling/Blueprints/Items/BP_SideScrollingSoftPlatform` |
| 위험 바닥 후보 | `/Game/Variant_Combat/Blueprints/Interactables/BP_CombatLavaFloor` |

## 신규 블루프린트 후보

| 블루프린트 | 책임 |
|---|---|
| `BP_StarballGameMode` | 게임 상태와 스코어 관리 |
| `BP_StarballPlayerController` | 플레이어 입력/카메라/일시정지 확장 후보 |
| `BP_StarballCharacter` | v0.2 플레이어 조작 prototype |
| `BP_StarballCollectible` | 별/공 수집 처리 |
| `BP_StarballMovingPlatform` | v0.2 움직이는 발판 prototype |
| `BP_StarballSoftPlatform` | v0.2 소프트 발판 prototype |
| `BP_StarballHazard` | 충돌 시 실패 처리 |
| `BP_StarballGoalGate` | 클리어 처리 |
| `BP_StarballCourseManager` | 타이머, 리스폰, 결과 흐름 |

## v0.2 Prototype과 v0.3 Target 구분

| v0.2 prototype | v0.3 target | 관계 |
|---|---|---|
| `BP_StarballCollectible` | `BP_SR_StarShardPickup`, `BP_SR_EnergyOrbPickup` | 하나의 generic prototype을 별 조각/에너지 공 전용 pickup으로 분리 |
| `BP_StarballMovingPlatform` | `BP_SR_MovingPlatform` | 템플릿 이동 발판 로직을 전용 메시/레일 구조로 교체 |
| `BP_StarballHazard` | `BP_SR_HazardDevice` | 실패 판정 prototype을 위험 장치 전용 액터로 승격 |
| `BP_StarballGoalGate` | `BP_SR_GoalGate` | 클리어 판정 prototype을 골 게이트 전용 액터로 승격 |
| `BP_StarballGameMode` | 유지 | 게임 상태/스코어 관리 시스템 BP |
| `BP_StarballCourseManager` | 유지 | 코스 시간, 리스폰, 결과 흐름 관리 BP |

v0.3 target 에셋의 상세 정의는 `../project_memory/asset_manifest.md`와 `../art/gameplay_objects/gameplay_object_asset_pipeline.md`를 따른다.

## 구현 순서

1. 기존 사이드 스크롤링 맵과 캐릭터를 기준으로 플레이 공간을 확보한다.
2. 수집물과 발판을 배치해 30~60초 코스를 만든다.
3. 위험 영역과 리스폰 규칙을 추가한다.
4. 골 게이트와 클리어 판정을 추가한다.
5. 수집물, 장애물, 골 게이트 블루프린트가 전용 메시/머티리얼을 교체할 수 있게 구조화한다.
6. HUD와 결과 흐름을 추가한다.
7. v0.3 아트 vertical slice 에셋을 통합한다.

## 아트 통합 원칙

- 게임플레이 로직과 시각 에셋 참조를 분리한다.
- `BP_StarballCollectible`은 별 조각과 에너지 공을 데이터/프로퍼티로 구분할 수 있어야 한다.
- `BP_StarballHazard`는 충돌 컴포넌트와 표시 메시가 어긋나지 않도록 기준 크기를 문서화한다.
- `BP_StarballGoalGate`는 클리어 판정 볼륨과 게이트 표시 메시를 분리한다.
- 전용 에셋 경로는 `/Game/StarballRun/Art` 아래로 통일한다.

## MCP 검증 포인트

- 에셋 검색이 실제 프로젝트 구조와 일치하는가?
- 액터 배치가 월드에 반영되는가?
- 블루프린트 생성/컴파일이 에디터에서 성공하는가?
- 맵 체크가 치명 오류 없이 통과하는가?
- 전용 아트 교체 후에도 충돌/오버랩 판정이 유지되는가?
