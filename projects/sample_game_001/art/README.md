# 샘플 게임 아트 서브 하네스

상태: 샘플 초안

## 목적

이 폴더는 프로젝트별 아트 문서가 많아졌을 때 어떤 식으로 분리되어야 하는지 보여주는 샘플이다.

실제 게임 컨셉은 아직 확정되지 않았으므로, 내용보다 구조 검토를 목적으로 한다.

## 문서 지도

| 위치 | 역할 |
|---|---|
| `direction/art_direction.md` | 전체 아트 방향 |
| `concepts/` | 컨셉 브리프와 이미지 검토 |
| `characters/` | 캐릭터 기준 |
| `gameplay_objects/` | 게임플레이 오브젝트 기준 |
| `environment/` | 배경과 레벨 아트 기준 |
| `animation_vfx/` | 애니메이션과 이펙트 기준 |
| `production/asset_brief.md` | 에셋 작업 지시서 템플릿 |
| `reviews/` | 아트 리뷰 기록 |
| `work_items/` | 아트 전용 작업 항목 |

## 이미지 저장 규칙

이미지는 중앙 `art/images/`가 아니라 사용하는 카테고리의 `images/<진행단계>/` 아래에 둔다.

예:

- `characters/images/concept_reference/player_sheet_v001.png`
- `gameplay_objects/images/modeling_reference/collectible_orthographic_v001.png`
