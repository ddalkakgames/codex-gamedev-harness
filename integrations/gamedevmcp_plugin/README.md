# GameDevMCPPlugin Integration

`Codex GameDev Harness` is the production framework. `GameDevMCPPlugin` is the Unreal Editor execution backend.

```text
Codex GameDev Harness
  -> GameDevMCPPlugin MCP endpoint
    -> Unreal Editor
```

## Responsibility Boundary

- The harness defines what game should be made, in what order, and how outputs are validated.
- GameDevMCPPlugin creates, modifies, queries, and validates Unreal assets, levels, Blueprints, materials, animation assets, UMG widgets, and related editor state.
- The harness should depend on MCP tool capabilities and schemas, not on plugin-internal C++ implementation details.

## Integration Contract

| Topic | Standard |
|---|---|
| Plugin endpoint | UE Plugin native Streamable HTTP MCP endpoint |
| Tool source | `GameDevMCPPlugin/Resources/schemas_30_tools.json` |
| Calls | MCP `tools/list` and `tools/call` |
| Validation | Project-level smoke tests and slice validation |

## What Each Project Should Record

- Required GameDevMCPPlugin version
- Required MCP tool capabilities
- Target Unreal project path
- First connection result
- Unreal assets generated or modified through MCP
- Validation results and remaining issues
