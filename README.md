# Codex GameDev Harness

이 디렉터리는 여러 개의 게임 프로젝트를 AI와 함께 운영하기 위한 **AI 게임 스튜디오 운영 프레임워크**를 보관한다.

구조는 두 영역으로 나뉜다.

```text
codex-gamedev-harness/
  framework/   # 모든 게임 프로젝트가 공유하는 규칙, 템플릿, schema
  projects/    # 게임 프로젝트별 실제 기획/아트/개발/QA/버전 문서
  integrations/ # Unreal MCP plugin 같은 외부 실행 backend 연동 기준
```

## 공통 프레임워크

`framework/`는 특정 게임에 종속되지 않는 공통 자료다.

```text
codex-gamedev-harness/framework/
  README.md
  schemas/
    feature_contract.schema.json
  templates/
    game_concept.template.md
    game_design_principles.template.md
    game_design_document.template.md
    system_spec.template.md
    art_harness_readme.template.md
    art_direction.template.md
    concept_brief.template.md
    art_asset_brief.template.md
    version.template.md
    traceability_matrix.template.md
  guides/
    new_project.md
    art_imagegen_workflow.md
```

## 게임 프로젝트

`projects/<project_id>/`는 특정 게임 하나의 실제 제작 문서다.

예:

```text
codex-gamedev-harness/projects/sample_game_001/
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

현재 실제 제작 테스트 프로젝트:

```text
codex-gamedev-harness/projects/starball_run_001/
```

## 제작 흐름

각 게임 프로젝트는 아래 흐름을 따른다.

```text
게임 컨셉
  ↓
게임 설계 원칙 / 목표 경험
  ↓
핵심 반복 구조 / 장기 반복 구조
  ↓
게임디자인 문서
  ↓
시스템 설계 문서
  ↓
아트 서브 하네스
  - 아트 방향성
  - 컨셉 이미지화
  - 캐릭터/오브젝트/환경/애니메이션/VFX 기준
  - 에셋 제작 브리프
  ↓
제작 작업 분해
  - 기획 작업
  - 아트 에셋 작업 지시서
  - 프로그램 개발 작업
  - UX 흐름
  - QA 검증 시나리오
  ↓
첫 플레이 가능 버전 계획
  ↓
GameDevMCP를 통한 언리얼 구현
  ↓
검증 / 플레이테스트
  ↓
버전 / 릴리즈 판정
```

## 문서와 JSON의 역할

사람이 검토하는 기본 문서는 마크다운이다.

JSON은 AI, 스크립트, MCP 도구가 읽기 위한 자동화용 자료다. JSON이 기획 문서의 중심이 되면 사람이 검토하기 어렵고 게임디자인 맥락이 사라진다. 따라서 JSON은 하위 자동화 계층에만 둔다.

## 새 게임 프로젝트 생성 기준

새 게임을 시작할 때는 `framework/templates/`의 템플릿을 복사해 `projects/<project_id>/` 아래에 만든다.

프로젝트 ID 예:

```text
prototype_action_001
puzzle_adventure_001
survival_builder_001
```

자세한 절차는 `framework/guides/new_project.md`를 따른다.

## 현재 샘플 프로젝트

현재 초안 문서는 아래 샘플 프로젝트에 들어 있다.

```text
codex-gamedev-harness/projects/sample_game_001/
```

이 프로젝트는 실제 게임 이름이 정해지기 전, 프레임워크 문서 구조를 검토하기 위한 샘플이다.

## 현재 제작 테스트 프로젝트

`codex-gamedev-harness/projects/starball_run_001/`은 별/공 수집, 장애물 회피, 골 도달을 검증하는 소형 플랫폼 게임 프로젝트다.

## GameDevMCPPlugin 연동

Unreal Editor 조작은 별도 저장소의 `GameDevMCPPlugin`을 실행 backend로 사용한다.

연동 기준은 `integrations/gamedevmcp_plugin/README.md`에 둔다.
