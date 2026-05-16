# Unreal MCP 적용 계획

## 목표

문서화된 v0.2 첫 플레이어블 요구사항을 TestMcp 프로젝트에 작은 프로토타입으로 적용한다.

## 1차 적용 방식

기존 `Variant_SideScrolling` 템플릿 에셋을 우선 활용한다.

1. MCP native HTTP 연결 확인
2. 현재 에디터 월드 확인
3. 기존 수집물/발판 에셋 경로 검증
4. `GameDevFramework/StarballRun/FirstPlayable` 폴더에 테스트 액터 배치
5. 맵 체크 실행
6. 결과를 이 문서에 기록

## 주의

현재 에디터에 열려 있는 맵이 사이드 스크롤링 맵이 아닐 수 있다. 이 경우 1차 배치는 “게임 루프 배치 검증”으로 보고, 실제 첫 플레이어블 맵 고정은 다음 작업에서 진행한다.

## 적용 로그

### 2026-05-07 1차 적용

MCP native HTTP endpoint 연결을 확인했다.

- URL: `http://172.17.32.1:19091/mcp`
- UE 버전: `5.7.4-51494982+++UE5+Release-5.7`
- 등록 도구 수: 514

StarballRun 전용 에셋을 TestMcp 로컬 콘텐츠에 생성했다.

| 작업 | 결과 |
|---|---|
| `/Game/Variant_SideScrolling/Lvl_SideScrolling` 복제 | `/Game/StarballRun/Maps/Lvl_Starball_FirstPlayable` 생성 |
| 캐릭터/게임모드/컨트롤러 복제 | `BP_StarballCharacter`, `BP_StarballGameMode`, `BP_StarballPlayerController` 생성 |
| 수집물/발판 복제 | `BP_StarballCollectible`, `BP_StarballMovingPlatform`, `BP_StarballSoftPlatform` 생성 |
| 블루프린트 컴파일 | 6개 모두 성공 |

현재 열린 월드는 `/Game/ThirdPerson/Lvl_ThirdPerson`이었다. 이 월드에 검증용 `SBR_*` 액터 19개를 배치했다.

| 분류 | 수량 |
|---|---:|
| PlayerStart | 1 |
| 별 조각 후보 | 10 |
| 에너지 공 후보 | 3 |
| 움직이는 발판 | 1 |
| 소프트 발판 | 1 |
| lava hazard 후보 | 2 |
| goal trigger 후보 | 1 |

`world.validation.map_check` 결과:

- actor count: 134
- error count: 0
- warning count: 18

경고는 기존 ThirdPerson 월드의 missing root component/duplicate label 경고이며, 1차 StarballRun 배치로 인한 치명 오류는 없다.

## 현재 제약

MCP에는 현재 에디터 맵을 특정 맵으로 여는 전용 도구가 없다. 그래서 1차 배치는 현재 열려 있던 ThirdPerson 월드에 들어갔다. 전용 맵 `/Game/StarballRun/Maps/Lvl_Starball_FirstPlayable`을 연 뒤 같은 배치를 고정하는 작업이 다음 단계다.

## 다음 작업

1. 에디터에서 `/Game/StarballRun/Maps/Lvl_Starball_FirstPlayable` 열기
2. `SBR_*` 코스 배치를 해당 맵 기준으로 재배치
3. `BP_StarballGoalGate`, `BP_StarballHazard` 전용 로직 구현
4. 수동 플레이로 시작, 수집, 회피, 클리어 루프 검증
