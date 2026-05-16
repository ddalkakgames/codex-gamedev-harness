# 프로젝트 규칙

## 명명 규칙

| 대상 | 규칙 | 예시 |
|---|---|---|
| v0.2 Prototype Blueprint | `BP_Starball...` | `BP_StarballGoalGate` |
| v0.3 Gameplay Object Blueprint | `BP_SR_...` | `BP_SR_GoalGate` |
| Static Mesh | `SM_SR_...` | `SM_SR_Platform_1x1_A` |
| Material Instance | `MI_SR_...` | `MI_SR_Platform_StoneMetal` |
| Niagara System | `NS_SR_...` | `NS_SR_Collect_StarShard` |
| Level | `Lvl_Starball...` | `Lvl_Starball_FirstPlayable` |
| Actor Label | `SBR_...` | `SBR_Star_01` |
| Folder | `GameDevFramework/StarballRun/...` | `GameDevFramework/StarballRun/FirstPlayable` |

## 이름 사용 규칙

- 이름만 먼저 만들지 않는다. 새 Unreal 에셋 이름을 문서에 추가할 때는 역할, 형태, 소유 문서, Unreal 경로, 완료 기준을 같이 적는다.
- `BP_Starball...`은 템플릿 복제 기반 v0.2 프로토타입/시스템 블루프린트에 사용한다.
- `BP_SR_...`, `SM_SR_...`, `MI_SR_...`, `NS_SR_...`는 v0.3 이후 전용 아트/게임플레이 오브젝트 제작 에셋에 사용한다.
- 기존 엔진 템플릿 경로 `/Game/Variant_*`는 원본 후보일 뿐 StarballRun 소유 에셋이 아니다.
- 동일 역할의 v0.2 prototype과 v0.3 target이 같이 있을 때는 `project_memory/asset_manifest.md`에 관계를 명시한다.

## 문서 규칙

- 사람이 검토하는 문서는 Markdown으로 작성한다.
- AI/툴 전용 구조화 데이터가 필요할 때만 JSON을 추가한다.
- 새 기능은 기획 의도와 검증 기준을 먼저 적고 구현한다.
