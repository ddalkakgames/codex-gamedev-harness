# 별공 런 아트 서브 하네스

## 목적

`starball_run_001`의 아트 방향, 컨셉 이미지, 캐릭터/오브젝트/환경 기준, 제작 브리프, 리뷰, 작업 항목을 `art/` 안에서 독립적으로 관리한다.

아트는 단순히 이미지 목록이 아니라 게임 기획과 시스템을 플레이어가 읽을 수 있는 형태로 바꾸는 제작 축이다. 따라서 이 폴더는 프로젝트 안의 작은 아트 제작 하네스로 운영한다.

## 현재 아트 목표

작은 별 수리공 `루미`가 하늘 위 천문 공방을 달리며 별 조각과 에너지 공을 모으고, 위험 장치를 피해 골 게이트를 여는 stylized 2.5D 플랫폼 게임 화면을 만든다.

## 운영 원칙

1. 모든 아트 결정은 `../design/`의 게임 컨셉과 게임 설계 원칙을 따른다.
2. 수집물, 위험물, 골, 발판은 설명 없이 역할이 구분되어야 한다.
3. 컨셉 이미지는 검토용 reference이며 최종 에셋으로 확정하지 않는다.
4. 실제 제작은 `production/asset_brief.md`의 에셋 단위와 완료 기준으로 분해한다.
5. 수정/폐기 결정은 `reviews/`에 남기고, 실제 작업은 `work_items/`에서 추적한다.

## 문서 지도

| 위치 | 역할 |
|---|---|
| `direction/art_direction.md` | 전체 아트 방향, 색상, 형태 언어, 화면 우선순위 |
| `concepts/concept_brief.md` | 루미와 핵심 오브젝트의 컨셉 요약, 이미지 검토 |
| `characters/lumi_character_concept.md` | 주인공 루미의 형태, 색상, 움직임 기준 |
| `gameplay_objects/gameplay_object_concepts.md` | 별 조각, 에너지 공, 위험 장치, 골 게이트, 발판 기준 |
| `gameplay_objects/gameplay_object_asset_pipeline.md` | Unreal 업로드용 게임플레이 오브젝트 에셋 목록과 3면도 reference |
| `environment/environment_concept.md` | 천문 공방 상층 배경과 레이어 기준 |
| `animation_vfx/animation_vfx_direction.md` | 입력 반응, 수집, 위험, 골 VFX 기준 |
| `production/art_production_strategy.md` | 전용 아트 제작 전략과 단계 |
| `production/asset_brief.md` | v0.3 아트 vertical slice 에셋 목록과 완료 기준 |
| `reviews/` | 이미지/에셋 리뷰 결과와 수정 결정 |
| `work_items/` | 아트 작업 단위와 상태 |

## 이미지 저장 규칙

이미지는 `art/images/`에 모아두지 않고, 실제 사용하는 카테고리 폴더 아래에 둔다.

```text
art/<카테고리>/images/<진행단계>/<파일명>.png
```

현재 사용하는 진행단계는 아래와 같다.

| 진행단계 | 용도 |
|---|---|
| `concept_reference` | 컨셉 방향, 시각 검토, 아트 reference |
| `modeling_reference` | 3D 모델링용 3면도, 비율/파츠 reference |
| `superseded_reference` | 새 기준으로 대체되어 더 이상 사용하지 않는 이전 reference |

예:

- `characters/images/concept_reference/character_sheet_v001.png`
- `gameplay_objects/images/concept_reference/core_objects_v002.png`
- `gameplay_objects/images/modeling_reference/static_meshes/sm_sr_star_shard_a_orthographic_v001.png`

## 제작 흐름

```text
게임 컨셉 / 게임 설계 원칙
  ↓
direction/art_direction.md + direction/images/concept_reference/
  ↓
concepts/concept_brief.md + concepts/images/concept_reference/
  ↓
characters / gameplay_objects / environment / animation_vfx + 각 카테고리 images/
  ↓
production/art_production_strategy.md
  ↓
production/asset_brief.md
  ↓
reviews / work_items
  ↓
Unreal 전용 에셋 제작과 통합
```

## 현재 완료 기준

v0.3 아트 vertical slice에서는 아래가 충족되어야 한다.

- 루미가 별 자체가 아니라 작은 별 수리공으로 보인다.
- 별 조각, 에너지 공, 위험 장치, 골 게이트가 색상과 형태로 구분된다.
- 첫 스테이지 한 화면에서 발판, 위험 범위, 수집 경로, 목표가 읽힌다.
- 배경은 천문 공방 정체성을 주되 플레이 요소보다 튀지 않는다.
- 템플릿 에셋이 남아 있어도 핵심 판독 요소는 StarballRun 전용 방향을 가진다.
