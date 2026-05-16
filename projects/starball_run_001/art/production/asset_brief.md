# 에셋 브리프

## 목적

`별공 런` v0.3 아트 vertical slice를 만들기 위해 필요한 전용 에셋과 완료 기준을 정의한다.

## 참조 문서

- 전체 방향: `../direction/art_direction.md`
- 주인공: `../characters/lumi_character_concept.md`
- 오브젝트: `../gameplay_objects/gameplay_object_concepts.md`
- 게임플레이 오브젝트 제작 파이프라인: `../gameplay_objects/gameplay_object_asset_pipeline.md`
- 환경: `../environment/environment_concept.md`
- 애니메이션/VFX: `../animation_vfx/animation_vfx_direction.md`

## 현재 reference 이미지

아래 이미지는 현재 에셋 제작 기준의 reference다.

![루미 캐릭터 시트](../characters/images/concept_reference/character_sheet_v001.png)

![핵심 오브젝트](../gameplay_objects/images/concept_reference/core_objects_v002.png)

![환경 키 이미지](../environment/images/concept_reference/environment_key_v001.png)

| 이미지 | 용도 | 상태 |
|---|---|---|
| `../characters/images/concept_reference/character_sheet_v001.png` | 루미 proxy 제작 기준 | 생성 완료, 검토 대기 |
| `../gameplay_objects/images/concept_reference/core_objects_v002.png` | 수집물/위험물/골/발판 제작 기준 | 생성 완료, 검토 대기 |
| `../environment/images/concept_reference/environment_key_v001.png` | 배경 rough kit 제작 기준 | 생성 완료, 검토 대기 |

게임플레이 오브젝트의 모델링용 3면도 reference는 `../gameplay_objects/gameplay_object_asset_pipeline.md`에 첨부한다.

## v0.3 필수 에셋

| ID | 에셋 | 산출물 | 완료 기준 |
|---|---|---|---|
| ART-CHAR-001 | 루미 proxy 캐릭터 | 간단 메시 또는 스프라이트풍 메시 | 작은 수리공 실루엣, 장갑/부츠/헬멧이 보임 |
| ART-CHAR-002 | 루미 기본 머티리얼 | 작업복/장갑/별 장식/에너지 포인트 | 배경 위에서 위치가 보임 |
| ART-COL-001 | 별 조각 | 메시, 머티리얼, 수집 VFX | 작아도 금색 파편으로 읽힘 |
| ART-COL-002 | 에너지 공 | 메시, 머티리얼, 수집 VFX | 별 조각과 형태/색이 다름 |
| ART-HAZ-001 | 위험 장치 | 메시, 머티리얼, 예고 VFX | 실제 충돌 범위를 예측 가능 |
| ART-GOAL-001 | 골 게이트 | 메시, 머티리얼, 활성화 VFX | 도착지로 인식됨 |
| ART-PLAT-001 | 기본 발판 kit | 기본/가장자리/짧은 발판 | 상단 충돌면이 명확함 |
| ART-PLAT-002 | 움직이는 발판 시각 요소 | 발판 메시, 청록 궤적 장치 | 이동 발판임을 알 수 있음 |
| ART-PLAT-003 | 발판 높이 조절 장치 | 리프트 기둥, 기어 박스, 에너지 게이지 | 발판의 수직 이동/고저차를 예측할 수 있음 |
| ART-ENV-001 | 배경 rough kit | 원경/중경/근경 rough | 플레이 요소보다 낮은 대비 |

## v0.4 확장 에셋

| ID | 에셋 | 산출물 | 완료 기준 |
|---|---|---|---|
| ART-CHAR-101 | 루미 최종 모델 | rig 가능한 모델 | 기본 애니메이션 적용 가능 |
| ART-ENV-101 | 천문 공방 장식 prop | 망원경, 기어, 램프, 별지도 | 배경 정체성 강화 |
| ART-VFX-101 | 클리어 연출 | 게이트 활성화, 별가루 | 1초 내외로 클리어 감정 전달 |
| ART-UI-101 | 수집물 아이콘 | 별/공 아이콘 | HUD에서 구분 가능 |

## 제작 우선순위

1. 루미 proxy 캐릭터.
2. 별 조각과 에너지 공.
3. 위험 장치와 위험 범위 VFX.
4. 골 게이트.
5. 발판 kit.
6. 발판 높이 조절 장치.
7. 배경 rough kit.
8. UI 아이콘과 추가 장식.

## 공통 제작 조건

- 실제 충돌 범위와 시각 범위가 크게 다르면 안 된다.
- 작게 보아도 역할이 구분되어야 한다.
- 색상 없이 실루엣만 보아도 수집물/위험물/골이 구분되어야 한다.
- 전용 에셋은 템플릿 에셋을 덮어쓰기하지 않고 `/Game/StarballRun/Art` 아래에 새로 둔다.
- imagegen 이미지는 reference일 뿐 최종 에셋 파일이 아니다.
- 구체적인 Unreal 에셋명은 이름만 추가하지 않는다. 에셋명, 역할, 형태, 경로, 완료 기준은 `../../project_memory/asset_manifest.md`와 `../gameplay_objects/gameplay_object_asset_pipeline.md`에 함께 정의한다.

## Unreal 경로 규칙

| 종류 | Unreal 경로 |
|---|---|
| 캐릭터 | `/Game/StarballRun/Art/Characters/Lumi` |
| 메시 | `/Game/StarballRun/Art/Meshes` |
| 머티리얼 | `/Game/StarballRun/Art/Materials` |
| 텍스처 | `/Game/StarballRun/Art/Textures` |
| VFX | `/Game/StarballRun/Art/VFX` |
| UI | `/Game/StarballRun/UI` |

게임플레이 오브젝트는 아래 세부 경로를 사용한다.

| 종류 | Unreal 경로 |
|---|---|
| Mesh | `/Game/StarballRun/Art/Meshes/GameplayObjects` |
| Material | `/Game/StarballRun/Art/Materials/GameplayObjects` |
| VFX | `/Game/StarballRun/Art/VFX/GameplayObjects` |
| Blueprint | `/Game/StarballRun/Blueprints/GameplayObjects` |

## 검수 질문

- 루미가 별 자체가 아니라 수리공으로 보이는가?
- 별 조각과 에너지 공이 동시에 있을 때 헷갈리지 않는가?
- 위험 장치의 닿으면 안 되는 범위를 예측할 수 있는가?
- 발판 상단면과 배경 장식이 구분되는가?
- 골 게이트가 화면 끝 목표로 보이는가?
