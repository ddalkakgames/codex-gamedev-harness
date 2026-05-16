# 공통 프레임워크

이 디렉터리는 모든 게임 프로젝트가 공유하는 규칙, 템플릿, schema, 가이드를 보관한다.

## 역할

- 새 게임 프로젝트의 기본 폴더 구조를 정의한다.
- 프로젝트별 `art/` 폴더를 아트 서브 하네스로 운영하는 기준을 제공한다.
- 사람이 읽는 마크다운 템플릿을 제공한다.
- 아트 방향과 컨셉을 이미지로 검토할 수 있는 imagegen 문서 흐름을 제공한다.
- AI와 자동화 도구가 읽는 JSON schema를 제공한다.
- 프로젝트별 문서 작성 순서를 안내한다.

## 디렉터리

```text
framework/
  schemas/    # 자동화 검증용 JSON schema
  templates/  # 사람이 읽는 문서 템플릿
  guides/     # 운영 가이드
```

## 주요 템플릿

| 템플릿 | 용도 |
|---|---|
| `game_concept.template.md` | 게임 컨셉 정의 |
| `game_design_principles.template.md` | 게임 설계 원칙 정의 |
| `game_design_document.template.md` | 게임디자인 문서 |
| `system_spec.template.md` | 시스템 설계 |
| `art_harness_readme.template.md` | 프로젝트별 아트 서브 하네스 입구 |
| `art_direction.template.md` | 아트 방향성 문서 |
| `concept_brief.template.md` | 아트 컨셉 브리프와 이미지 검토 |
| `art_asset_brief.template.md` | 에셋 작업 지시서 |
| `traceability_matrix.template.md` | 제작 추적표 |
| `version.template.md` | 버전 완료 기준 |

## 이미지 생성 활용 원칙

`imagegen`은 기획 문장을 실제 아트 산출물로 확정하는 도구가 아니라, 사용자가 아트 방향을 빠르게 이해하고 검토하기 위한 시각화 도구다.

- 생성 이미지는 컨셉 검토용 reference로 둔다.
- 최종 에셋으로 쓰려면 별도 제작, 리터치, 라이선스/IP 검토, Unreal 통합 검증을 거친다.
- 생성 이미지는 중앙 `art/images/`에 모으지 않고, 실제 사용하는 카테고리의 `images/<진행단계>/` 아래에 저장한다.
- 예: `art/gameplay_objects/images/modeling_reference/`, `art/characters/images/concept_reference/`
- imagegen 프롬프트 자체는 사용자 검토 문서에 노출하지 않는다.
- 문서에는 이미지, 생성 목적, 채택 여부, 수정 메모만 남긴다.

## 원칙

1. 공통 프레임워크에는 특정 게임의 기획 내용을 넣지 않는다.
2. 특정 게임의 컨셉, GDD, 시스템 설계, 아트 방향, 버전 문서는 `projects/<project_id>/`에 둔다.
3. 공통 템플릿은 프로젝트 문서를 시작하기 위한 양식이다.
4. JSON schema는 기획 문서의 중심이 아니라 자동화 검증 보조 도구다.
