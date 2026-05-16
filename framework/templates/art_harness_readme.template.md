# 아트 서브 하네스

상태: 초안

## 목적

이 폴더는 한 게임 프로젝트의 아트 방향, 컨셉, 이미지 reference, 제작 브리프, 리뷰, 작업 항목을 한곳에서 관리한다.

아트 문서가 많아져도 기획/시스템/개발 문서와 섞이지 않도록 `art/` 자체를 별도 서브 하네스로 운영한다.

## 운영 원칙

1. 아트 방향은 게임 컨셉과 게임 설계 원칙에서 출발한다.
2. 컨셉 이미지는 사용자가 이해하고 검토하기 위한 reference이며 최종 에셋이 아니다.
3. 캐릭터, 오브젝트, 환경, 애니메이션/VFX 기준은 서로 분리해서 관리한다.
4. 실제 제작 단위는 `production/`의 에셋 브리프와 연결한다.
5. 변경 결정과 폐기 사유는 `reviews/`에 남긴다.

## 문서 지도

| 위치 | 역할 |
|---|---|
| `direction/art_direction.md` | 전체 아트 방향, 색상, 형태 언어, 금지 방향 |
| `concepts/concept_brief.md` | 컨셉 이미지와 검토 기준 |
| `characters/` | 주인공, NPC, 적, 보스 등 캐릭터 기준 |
| `gameplay_objects/` | 수집물, 장애물, 상호작용물, 목표물 기준 |
| `environment/` | 배경, 레벨 아트, prop, 조명 기준 |
| `animation_vfx/` | 애니메이션, VFX, 피드백 기준 |
| `production/asset_brief.md` | 실제 제작 에셋 목록과 완료 기준 |
| `reviews/` | 아트 리뷰 결과와 수정 결정 |
| `work_items/` | 아트 작업 단위와 진행 상태 |

## 이미지 저장 규칙

이미지는 중앙 `art/images/`에 모으지 않고, 사용하는 카테고리 폴더 아래에 둔다.

```text
art/<카테고리>/images/<진행단계>/<파일명>.png
```

| 진행단계 | 용도 |
|---|---|
| `concept_reference` | 컨셉 방향, 시각 검토, 아트 reference |
| `modeling_reference` | 3D 모델링용 3면도, 비율/파츠 reference |
| `paintover_reference` | 수정안, 리뷰용 paintover |
| `superseded_reference` | 새 기준으로 대체되어 더 이상 사용하지 않는 이전 reference |

## 기본 흐름

```text
게임 컨셉 / 게임 설계 원칙
  ↓
direction/art_direction.md + direction/images/concept_reference/
  ↓
concepts/concept_brief.md + concepts/images/concept_reference/
  ↓
characters / gameplay_objects / environment / animation_vfx + 각 카테고리 images/
  ↓
production/asset_brief.md
  ↓
reviews / work_items
  ↓
Unreal 에셋 제작과 통합
```
