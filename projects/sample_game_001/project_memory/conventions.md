# 프로젝트 규칙

상태: 초안
목적: AI가 게임디자인과 언리얼 프로젝트 작업을 연결할 때 따를 기본 규칙

## 문서 우선순위

사람이 검토하는 마크다운 문서가 기본이다.

우선순위:

1. 게임 컨셉 / 게임디자인 문서 / 시스템 설계
2. 제작 작업 분해 문서
3. 세로 단면 / 버전 문서
4. 작업 항목 / 기능 계약
5. JSON 복사본 또는 script artifact

## ID 규칙

| 대상 | 예시 |
|---|---|
| 게임 설계 원칙 | `principle_readable_tactical_action` |
| 시스템 | `core_loop`, `combat`, `progression` |
| 시스템 구성요소 | `combat_hit_reaction`, `level_goal_rule` |
| 작업 항목 | `wi_combat_hit_reaction_001` |
| 에셋 지시서 | `ab_enemy_scout_001` |
| 버전 | `v0.2_first_playable` |

## 에셋 폴더 정책

프로토타입 에셋은 버전 또는 세로 단면 기준으로 둔다.

```text
/Game/Prototype/<version_or_slice>/
```

제품 수준으로 승격할 때는 시스템/콘텐츠 기준으로 이동한다.

```text
/Game/Game/Characters/
/Game/Game/Levels/
/Game/Game/UI/
/Game/Game/VFX/
/Game/Game/Systems/
```

## 임시 에셋과 제품 에셋

임시 에셋은 디자인 검증을 위한 에셋이다.

임시 에셋에는 아래 metadata/tag를 남긴다.

- `generated_by=GameDevFramework`
- `version=<version_id>`
- `slice=<slice_id>`
- `asset_stage=prototype`

제품 에셋 승격은 버전 검증 이후 별도 검토로 결정한다.

## 언리얼 변경 정책

AI는 아래 순서를 따른다.

1. 게임 컨셉 또는 GDD 결정 확인
2. 시스템 설계 확인
3. 제작 작업 분해 확인
4. 작업 항목 또는 기능 계약 생성
5. GameDevMCP 도구 실행
6. compile/save/map check 검증
7. 구현/검증 보고서 작성
8. 제작 추적표와 manifest 갱신

## 검증 정책

완료 판정은 계층별로 다르다.

- 작업 항목: 해당 검증 항목 통과
- 시스템 구성요소: 관련 작업 항목 통과 및 통합 검증 통과
- 세로 단면: 플레이어에게 약속한 경험이 플레이테스트 또는 자동화로 증명됨
- 버전: 버전 검증 기준과 알려진 문제 정리 완료
