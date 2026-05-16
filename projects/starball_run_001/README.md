# 별공 런 프로젝트

`starball_run_001`은 Codex GameDev Harness의 실제 제작 테스트용 소형 플랫폼 게임이다.

## 한 줄 설명

플레이어가 짧은 2.5D 스테이지에서 별 조각과 에너지 공을 모으고, 움직이는 장애물을 피해서 골 게이트에 도달하는 플랫폼 게임.

## 제작 목표

- 게임 기획에서 시작해 시스템, 아트, 개발, QA 산출물로 연결되는 전체 흐름을 검증한다.
- 한 번에 큰 게임을 만들지 않고, 검증 가능한 vertical slice를 쌓아서 버전 단위로 완성도를 판단한다.
- Unreal MCP를 통해 에셋 열람, 액터 배치, 블루프린트 생성/수정, 설정 변경이 실제 제작 프로세스에 맞게 작동하는지 확인한다.

## 현재 버전 목표

| 버전 | 상태 | 완료 기준 |
|---|---|---|
| v0.1 | 문서화 진행 | 콘셉트, 게임 설계 원칙, 핵심 루프, 1차 스테이지 요구사항 확정 |
| v0.2 | 구현 예정 | 시작 지점, 수집물, 장애물, 골 지점이 있는 첫 플레이어블 스테이지 |
| v0.3 | 이후 | 점수, 제한 시간, 실패/성공 UI, 리트라이 흐름 |

## 문서 지도

- `design/`: 게임 콘셉트, 게임 설계 원칙, 게임 디자인 문서
- `systems/`: 핵심 루프와 수집/장애물/클리어 시스템
- `art/`: 별공 런 아트 서브 하네스
- `art/README.md`: 아트 서브 하네스 입구와 문서 지도
- `art/direction/art_direction.md`: 전체 아트 방향, 색상, 형태 언어
- `art/concepts/concept_brief.md`: 아트 컨셉 브리프와 이미지 검토
- `art/characters/lumi_character_concept.md`: 주인공 루미의 형태, 색, 움직임 기준
- `art/gameplay_objects/gameplay_object_concepts.md`: 수집물, 위험물, 골, 발판 기준
- `art/environment/environment_concept.md`: 천문 공방 상층 배경 기준
- `art/animation_vfx/animation_vfx_direction.md`: 애니메이션과 VFX 기준
- `art/production/art_production_strategy.md`: 전용 아트 제작 전략
- `art/production/asset_brief.md`: v0.3 아트 vertical slice 에셋 브리프
- `art/<카테고리>/images/<진행단계>/`: 생성 이미지와 아트 reference 저장 위치
- `art/reviews/`: 아트 리뷰 결과와 수정 결정
- `art/work_items/`: 아트 전용 작업 항목
- `engineering/`: Unreal 구현 설계와 작업 백로그
- `ux/`: HUD, 피드백, 입력 흐름
- `qa/`: 플레이 검증 기준
- `production/`: 제작 파이프라인, 로드맵, 추적표
- `slices/`: vertical slice 정의
- `versions/`: 버전별 완성 기준
- `project_memory/`: 프로젝트 공통 기억, 용어, 에셋/기능 목록
- `implementation/`: 실제 MCP/언리얼 적용 로그

## IP 기준

이 프로젝트는 기존 상용 게임이나 캐릭터를 복제하지 않는다. 참고하는 것은 “플랫폼 이동, 수집, 회피, 골 도달”이라는 장르 구조이며, 이름, 캐릭터, 맵, 연출, 고유 규칙은 독자적으로 만든다.

## 실전 제작 기준

실전 연습이므로 최종까지 템플릿 에셋에 의존하지 않는다. v0.2는 플레이 가능성 검증을 위해 기존 에셋을 쓰되, 같은 시점에 전용 아트 제작 전략과 브리프를 확정한다. v0.3부터는 전용 캐릭터 실루엣, 수집물, 장애물, 발판, 골 게이트, 배경 키트를 실제 게임 화면에 통합한다.
