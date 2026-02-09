# AI Agents

Canonical agent role templates for government compliance projects. Model-agnostic patterns with vendor-specific implementations.

## Architecture

```
ai-agents/
├── templates/           # Model-agnostic role definitions
│   ├── project-setup.md
│   ├── requirements.md
│   ├── implementation.md
│   ├── documentation.md
│   └── review.md
├── claude/              # Claude Code implementation
│   ├── agents.json      # Ready for: claude --agents "$(cat claude/agents.json)"
│   └── README.md
└── scrum/               # Scrum team structure (planned)
```

## Agent Roles

| Role | Purpose | Reasoning Demand |
|------|---------|-----------------|
| Project Setup | Repo structure, build config, templates | Low |
| Requirements | Extract/validate requirements from standards | High |
| Implementation | Write compliant code per requirements | Medium |
| Documentation | Decision memos, verification docs, LaTeX | Medium |
| Review | Audit artifacts (read-only, separation of duties) | High |

## Design Principles

1. **Model-agnostic templates**: Role definitions in `templates/` describe *what* each agent does, not *how* a specific model implements it
2. **Vendor implementations**: `claude/`, and future directories, contain model-specific configurations
3. **Separation of duties**: Review agents cannot modify what they audit (NIST SP 800-53 AC-5)
4. **Interaction logging**: All agents log human-agent interactions for audit traceability
5. **Semantic versioning**: Projects using these templates follow semver and Keep a Changelog

## Standards

Agent templates encode compliance with:

- **IEEE 1028** — Software Reviews and Audits
- **IEEE 29148** — Requirements Engineering
- **NIST SP 800-53** — Security and Privacy Controls (AC-5, SA-11, CM-3, AU-3)
- **ISO/IEC 25010** — Software Quality
- **MIL-STD-498** — Software Development and Documentation

## Usage

### Claude Code

```bash
claude --agents "$(cat claude/agents.json)"
```

### Single agent

```bash
claude --model opus  # For requirements or review work
claude --model sonnet  # For implementation or documentation
```

## Projects Using These Templates

- [WhitePaper](https://github.com/brucedombrowski/WhitePaper) — Academic paper on AI-assisted government compliance
- [SendCUIEmail](https://github.com/brucedombrowski/SendCUIEmail) — CUI encryption tool
- [Security Toolkit](https://github.com/brucedombrowski/security-toolkit) — Automated NIST control verification
- [Scrum](https://github.com/brucedombrowski/Scrum) — Scrum Guide implementation with AI agents

## License

See individual project repositories for licensing.
