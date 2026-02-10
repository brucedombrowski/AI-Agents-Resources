# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) and AI agents working with code in this repository.

## Project Overview

Canonical agent role templates for government compliance projects. This repository provides model-agnostic role definitions, vendor-specific implementations, and reusable CI/CD workflows.

## Repository Structure

```
ai-agents/
├── templates/           # Model-agnostic role definitions
│   ├── project-setup.md
│   ├── requirements.md
│   ├── implementation.md
│   ├── documentation.md
│   └── review.md
├── workflows/           # Reusable CI/CD templates
│   ├── release-latex.yml    # LaTeX projects: build PDF + HTML, attach to release
│   └── release-binary.yml   # CLI tools: build binaries + SHA256, attach to release
└── claude/              # Claude Code implementation
    ├── agents.json      # Multi-agent configuration
    └── README.md
```

## Agent Roles

| Role | Purpose | Model Recommendation |
|------|---------|---------------------|
| project-setup | Repo structure, build config, templates | Sonnet |
| requirements | Extract/validate requirements from standards | Opus |
| implementation | Write compliant code per requirements | Sonnet |
| documentation | Decision memos, verification docs, LaTeX | Sonnet |
| review | Audit artifacts (read-only, separation of duties) | Opus |

## Adding a New Agent Role Template

1. Create `templates/<role-name>.md`
2. Follow the structure: Overview, Responsibilities, Standards, Output Format, Conventions
3. Map the role to NIST SP 800-53 controls or IEEE standards where applicable
4. Keep templates model-agnostic (describe *what*, not *how*)
5. Update README.md to include the new role in the table

## Adding a New Workflow Template

1. Create `workflows/<workflow-name>.yml`
2. Document trigger conditions, inputs, and outputs
3. Include artifact checksums (SHA256) for release attachments
4. Follow semantic versioning conventions
5. Update README.md to list the new workflow

## Updating claude/agents.json

The `claude/agents.json` file contains Claude-specific agent implementations:

```json
{
  "agent-name": {
    "description": "Brief description for Claude Code agent picker",
    "prompt": "Full prompt with responsibilities, standards, and conventions",
    "tools": ["Read", "Write", "Edit", "Bash", "Glob", "Grep"],
    "model": "sonnet"
  }
}
```

**Key conventions:**
- Use `{PROJECT_REPO}` placeholder for repository references
- Include "Interaction Logging" section in all agent prompts
- Map tools to agent capabilities (review agents get Read/Glob/Grep only)
- Specify model: "opus" for high-reasoning (requirements, review), "sonnet" for implementation

## Design Principles

1. **Model-agnostic templates**: Role definitions in `templates/` describe *what* each agent does, not *how* a specific model implements it
2. **Vendor implementations**: `claude/` contains Claude Code-specific configurations. Future vendors (e.g., OpenAI, Anthropic API) would add their own directories.
3. **Separation of duties**: Review agents cannot modify what they audit (NIST SP 800-53 AC-5)
4. **Interaction logging**: All agents log human-agent interactions as GitHub issues for audit traceability
5. **Semantic versioning**: Projects using these templates follow semver and Keep a Changelog

## Conventions

- **Issue templates**: Not included here — each project creates its own based on workflow needs
- **Agent prompts**: Include compliance standards (NIST, FIPS, CFR) and verification methods
- **Workflow artifacts**: Always include checksums (SHA256, SHA512) for release attachments
- **Documentation**: Decision memoranda follow the LaTeX template-wrapper pattern
- **Commit messages**: Conventional Commits format (feat, fix, docs, chore, refactor)

## Related Projects

These projects use the ai-agents templates:

- [WhitePaper](https://github.com/brucedombrowski/WhitePaper) — Academic paper on AI-assisted government compliance
- [SendCUIEmail](https://github.com/brucedombrowski/SendCUIEmail) — CUI encryption tool (FIPS 140-2, NIST SP 800-132, 32 CFR Part 2002)
- [Security Toolkit](https://github.com/brucedombrowski/security-toolkit) — Automated NIST control verification
- [Scrum](https://github.com/brucedombrowski/Scrum) — Scrum Guide implementation with AI agents
- [LaTeX](https://github.com/brucedombrowski/LaTeX) — LaTeX templates for government compliance documents

## Standards Encoded

Agent templates reference these open standards:

- **IEEE 1028** — Software Reviews and Audits
- **IEEE 29148** — Requirements Engineering
- **NIST SP 800-53** — Security and Privacy Controls (AC-5, SA-11, CM-3, AU-3)
- **ISO/IEC 25010** — Software Quality
- **MIL-STD-498** — Software Development and Documentation

## Usage

### Multi-agent mode (Claude Code)

```bash
claude --agents "$(cat claude/agents.json)"
```

### Single agent mode

```bash
claude --model opus   # For requirements or review work
claude --model sonnet # For implementation or documentation
```

## Author

**Bruce Dombrowski**
GitHub: [@brucedombrowski](https://github.com/brucedombrowski)

## License

MIT License — See [LICENSE](LICENSE) file.
