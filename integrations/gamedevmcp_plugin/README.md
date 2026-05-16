# GameDevMCPPlugin Integration

## 역할

`Codex GameDev Harness`는 게임 제작 운영 프레임워크이고, `GameDevMCPPlugin`은 Unreal Editor 조작을 담당하는 실행 backend다.

```text
Codex GameDev Harness
  -> GameDevMCPPlugin MCP endpoint
    -> Unreal Editor
```

## 협업 경계

- Framework는 어떤 게임을 어떤 순서로 만들지, 어떤 산출물을 검증할지 정의한다.
- GameDevMCPPlugin은 Unreal asset, level, blueprint, material, animation, UMG 등을 실제 Editor 안에서 생성/수정/조회한다.
- Framework는 plugin 내부 C++ 구현에 직접 의존하지 않고 MCP tool capability와 schema를 통해 연동한다.

## 연동 기준

| 항목 | 기준 |
|---|---|
| Plugin endpoint | UE Plugin native Streamable HTTP MCP endpoint |
| Tool source | `GameDevMCPPlugin/Resources/schemas_30_tools.json` |
| 호출 방식 | MCP `tools/list`, `tools/call` |
| 검증 방식 | 프로젝트별 integration smoke와 slice validation |

## 프로젝트 문서에서 기록할 것

각 게임 프로젝트는 `project_memory/` 또는 `implementation/` 문서에 아래 내용을 기록한다.

- 필요한 GameDevMCPPlugin 버전
- 필요한 MCP tool capability
- 사용한 Unreal 프로젝트 경로
- 첫 연결 검증 결과
- 자동 생성/수정한 Unreal asset 목록

