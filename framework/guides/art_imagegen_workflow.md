# Imagegen 아트 시각화 workflow

## 목적

아트 방향성이나 게임 컨셉을 글로만 설명하면 사용자가 이해하기 어렵다. 이 workflow는 `imagegen`으로 검토용 이미지를 만들고, Markdown 문서에 포함해 기획/아트/개발이 같은 장면을 보며 논의하게 한다.

## 적용 시점

- 게임 컨셉이 1차로 정리된 뒤
- 아트 방향성 문서가 초안 상태일 때
- 전용 에셋 제작 전에 사용자와 분위기, 실루엣, 색상, 화면 구성을 맞춰야 할 때

## 산출물 위치

```text
GameDevFramework/projects/<project_id>/art/
  direction/
    art_direction.md
  concepts/
    concept_brief.md
  production/
    asset_brief.md
  concepts/
    images/
      concept_reference/
        concept_overview_v001.png
  gameplay_objects/
    images/
      concept_reference/
        core_objects_v001.png
      modeling_reference/
        collectible_orthographic_v001.png
```

## 절차

1. `art/direction/art_direction.md`에 사람이 이해할 수 있는 아트 방향을 먼저 쓴다.
2. 이미지가 필요한 문서에 이미지 슬롯과 검토 항목을 작성한다.
3. Codex가 문서 내용을 바탕으로 내부적으로 `imagegen` 이미지를 생성한다.
4. 선택한 이미지를 해당 카테고리의 `images/<진행단계>/` 아래로 옮긴다.
5. Markdown 문서에 상대 경로 이미지 링크를 포함한다. 예를 들어 `art/gameplay_objects/gameplay_object_asset_pipeline.md`에서는 `![설명](images/modeling_reference/파일명.png)` 형식을 사용한다.
6. 사용자가 검토한 내용을 “채택/수정/폐기”로 기록한다.

## 이미지 요청 기준

문서에는 프롬프트를 직접 노출하지 않는다. 대신 Codex가 이미지를 생성할 수 있도록 사람이 이해하기 쉬운 이미지 요청 기준을 남긴다.

- 게임 장르와 카메라
- 화면에 보여야 하는 핵심 요소
- 스타일과 색상 방향
- 플레이 판독성 기준
- 피해야 할 외부 IP, 분위기, 소재
- 이미지 용도: 컨셉 검토용, 최종 에셋 아님

## 문서에 남길 기록

| 항목 | 설명 |
|---|---|
| 이미지 파일 | 프로젝트 상대 경로 |
| 생성 목적 | 무엇을 검토하려고 만들었는지 |
| 채택 여부 | 채택, 수정 필요, 폐기 |
| 수정 메모 | 다음 생성/제작 때 반영할 내용 |

## 주의

- 생성 이미지는 최종 에셋이 아니다.
- 실제 게임에 쓰려면 리터치, 모델링/텍스처링, 최적화, Unreal 통합을 거친다.
- 기존 상용 게임의 캐릭터, UI, 고유 실루엣, 보스/스테이지 구성을 직접 복제하지 않는다.
- 이미지가 멋져 보여도 플레이 판독성을 해치면 폐기한다.
