# Claude Code Implementation

Claude Code (`claude --agents`) implementation of the model-agnostic agent templates.

## Usage

```bash
claude --agents "$(cat claude/agents.json)"
```

## Cross-Repo Agent Ingestion

Agents in Claude Code projects ingest instruction files from other repositories:
- `CLAUDE.md` — project-specific agent instructions
- `AGENTS.md` — legacy agent instructions (SendCUIEmail convention)
- `agents.json` — multi-agent configuration

This cross-repo ingestion enables agents to learn from and build on patterns established in other projects. The ai-agents repo serves as the canonical source; individual projects may extend or specialize these templates.

## Model Selection

| Role | Model | Rationale |
|------|-------|-----------|
| project-setup | Sonnet | Structured, template-following tasks |
| requirements | Opus | Regulatory interpretation demands highest reasoning |
| implementation | Sonnet | Speed/quality balance for code generation |
| documentation | Sonnet | Structured document generation |
| review | Opus | Conservative judgment, cross-reference validation |

## Status

This is active research. Templates are being refined iteratively across multiple concurrent projects. See the [WhitePaper](https://github.com/brucedombrowski/WhitePaper) for methodology documentation.
