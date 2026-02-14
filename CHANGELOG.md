# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added
- Reference to [run-tracker](https://github.com/brucedombrowski/run-tracker) — GitHub issue-based run tracking extracted from ORBIT-CEF-Status into its own repo
- `workflows/` directory with reusable CI/CD templates
  - `release-latex.yml` — LaTeX projects: build PDF + HTML, attach to GitHub releases
  - `release-binary.yml` — CLI tools: build binaries + SHA256 checksums, attach to releases
- Release artifact requirements in project-setup template — source-code-only releases are insufficient for deliverable-oriented projects
- Release requirements table by project type (documents, CLI tools, libraries, web apps)

### Changed
- `templates/project-setup.md` — added release workflow responsibility and release requirements section

## [0.1.0] - 2026-02-09

### Added
- Model-agnostic agent role templates: project-setup, requirements, implementation, documentation, review
- Claude Code implementation (`claude/agents.json`) extracted from WhitePaper project
- README with architecture overview, design principles, and standards references
- Cross-repo agent ingestion documentation

[0.1.0]: https://github.com/brucedombrowski/ai-agents/releases/tag/v0.1.0
