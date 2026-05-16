# 새 게임 프로젝트 만들기

## 목적

여러 게임을 동시에 진행할 때 각 게임의 문서와 산출물이 섞이지 않도록 프로젝트별 문서 루트를 만든다.

## 프로젝트 ID 정하기

프로젝트 ID는 소문자, 숫자, 밑줄을 사용한다.

예:

```text
prototype_action_001
puzzle_adventure_001
survival_builder_001
```

## 폴더 만들기

```text
GameDevFramework/projects/<project_id>/
  README.md
  design/
  systems/
  art/
    README.md
    direction/
    concepts/
    characters/
    gameplay_objects/
    environment/
    animation_vfx/
    production/
    reviews/
    work_items/
  engineering/
  ux/
  qa/
  production/
  slices/
  versions/
  work_items/
  project_memory/
```

## 문서 작성 순서

1. `design/game_concept.md`
2. `design/game_design_principles.md`
3. `design/game_design_document.md`
4. `systems/core_loop.system.md`
5. `art/README.md`
6. `art/direction/art_direction.md`
7. `art/concepts/concept_brief.md`
8. `art/production/asset_brief.md`
9. `production/traceability_matrix.md`
10. `slices/first_playable_slice.md`
11. `versions/v0_2_first_playable.md`

## 아트 서브 하네스

아트 산출물은 양이 빠르게 늘어나므로 `art/`를 단순 문서 폴더가 아니라 별도 서브 하네스로 관리한다.

| 폴더 | 역할 |
|---|---|
| `art/README.md` | 아트 서브 하네스의 운영 입구와 문서 지도 |
| `art/direction/` | 전체 아트 방향, 색상, 형태 언어, 금지 방향 |
| `art/concepts/` | 컨셉 브리프, 이미지 검토, 시각 탐색 기록 |
| `art/characters/` | 플레이어, NPC, 적, 보스 등 캐릭터 기준 |
| `art/gameplay_objects/` | 수집물, 장애물, 상호작용물, 목표물 기준 |
| `art/environment/` | 배경, 레벨 아트, prop, 조명 기준 |
| `art/animation_vfx/` | 애니메이션, 이펙트, 피드백 기준 |
| `art/production/` | 에셋 브리프, 제작 전략, 산출물 목록 |
| `art/<category>/images/concept_reference/` | 카테고리별 컨셉 reference 이미지 |
| `art/<category>/images/modeling_reference/` | 카테고리별 3D 모델링 reference 이미지 |
| `art/reviews/` | 아트 리뷰 결과와 수정 결정 |
| `art/work_items/` | 아트 작업 단위와 상태 |

## 아트 컨셉 이미지화 순서

사용자가 아트 방향을 글만으로 이해하기 어렵다면 `imagegen`을 사용해 문서에 검토용 이미지를 포함한다.

1. `art/direction/art_direction.md`에 키워드, 화면 우선순위, 색상, 제외 조건을 작성한다.
2. `art/concepts/concept_brief.md`에 사용자가 검토해야 할 컨셉 항목과 이미지 슬롯을 작성한다.
3. Codex가 필요한 이미지를 내부적으로 `imagegen`으로 생성한다.
4. 선택한 이미지를 해당 카테고리의 `images/<진행단계>/` 아래에 저장한다.
5. `art/concepts/concept_brief.md`, `art/direction/art_direction.md`, `art/production/asset_brief.md` 등 필요한 문서에 Markdown 이미지 링크를 추가한다.
6. 이미지가 기획 의도와 맞는지 검토 결과를 문서에 기록한다.

생성 이미지는 최종 아트가 아니라 방향 검토 자료다. 실제 게임 에셋으로 쓰려면 별도 제작, 수정, 최적화, Unreal 통합 검증이 필요하다.

imagegen 프롬프트는 사용자 검토 문서에 노출하지 않는다. 문서에는 이미지와 검토 결과만 남긴다.

## 이미지 저장 기준

이미지는 `art/images/`에 모아두지 않는다. 문서 성격과 제작 단계에 맞는 카테고리 폴더 아래에 둔다.

```text
art/<category>/images/<stage>/<file>.png
```

| Stage | 용도 |
|---|---|
| `concept_reference` | 아트 방향, 컨셉 검토, 분위기 reference |
| `modeling_reference` | 3D 모델링용 3면도, 파츠/비율 reference |
| `paintover_reference` | 리터치, 수정안, 리뷰용 paintover |
| `superseded_reference` | 새 기준으로 대체되어 더 이상 사용하지 않는 이전 reference |

예:

- `art/characters/images/concept_reference/player_sheet_v001.png`
- `art/gameplay_objects/images/modeling_reference/collectible_orthographic_v001.png`
- `art/environment/images/concept_reference/level_key_v001.png`

## 복사 기준

`framework/templates/`의 템플릿을 복사해서 프로젝트 문서를 시작한다.

| 템플릿 | 복사 위치 |
|---|---|
| `art_harness_readme.template.md` | `art/README.md` |
| `art_direction.template.md` | `art/direction/art_direction.md` |
| `concept_brief.template.md` | `art/concepts/concept_brief.md` |
| `art_asset_brief.template.md` | `art/production/asset_brief.md` |

프로젝트 문서가 실제 결정사항을 담기 시작하면 템플릿 문구는 제거하고, 해당 게임의 구체적인 내용으로 바꾼다.

## 금지 사항

- 공통 `framework/` 아래에 특정 게임 컨셉을 쓰지 않는다.
- 시스템 설계 없이 바로 에셋/기능 문서를 만들지 않는다.
- 버전 문서 없이 "여기까지 완성"이라고 판단하지 않는다.
- 생성 이미지를 라이선스/IP 검토 없이 최종 에셋으로 확정하지 않는다.
