# Bruce Dombrowski Inc — Our Team

## Company Overview

Bruce Dombrowski Inc is a one-human software consultancy specializing in federal information security compliance. We deliver cryptographic tooling, compliance documentation, and government-quality software through a hybrid human-AI team structure. All AI agents are powered by Claude (Anthropic) and serve specialized functional roles reporting to the CEO.

---

## Organizational Structure

```
Bruce Dombrowski Inc

┌─────────────────────────────────────────────────────────┐
│                                                           │
│              Bruce Dombrowski (Human)                    │
│            CEO / Principal Engineer                      │
│                                                           │
└─────┬───────────────────────────────────────────────────┘
      │
      ├─────► Project Setup Agent (Sonnet)
      │       Infrastructure & Configuration
      │
      ├─────► Requirements Agent (Opus)
      │       Standards Analysis & Compliance
      │
      ├─────► Implementation Agent (Sonnet)
      │       Code Development & Testing
      │
      ├─────► Documentation Agent (Sonnet)
      │       Formal Artifacts & Traceability
      │
      └─────► Review Agent (Opus)
              Quality Assurance & Audit
```

---

## Leadership

### Bruce Dombrowski — CEO / Principal Engineer (Human)

**Role**: The decision maker, product owner, and domain expert for all projects.

**Responsibilities**:
- Define project objectives and success criteria
- Provide domain expertise in federal information security requirements
- Review and approve all AI agent outputs
- Make final architectural and policy decisions
- Interface with stakeholders and customers
- Authorize releases and deployments

**Key Authority**: All AI agents report directly to Bruce. No agent has autonomous decision-making authority.

**Contact**: GitHub [@brucedombrowski](https://github.com/brucedombrowski)

---

## Engineering Team

### Project Setup Agent — Infrastructure Specialist

**Agent Type**: Claude Sonnet 4.5
**Reports To**: CEO
**Tool Access**: Full read/write + terminal

**Responsibilities**:
- Initialize and maintain repository structure
- Create and update CLAUDE.md, .gitignore, and project configuration files
- Set up build infrastructure (Makefile, CI/CD workflows, package configurations)
- Manage multi-agent configuration files (agents.json)
- Create documentation templates following government formatting conventions
- Enforce semantic versioning and changelog maintenance
- Configure release workflows that attach built artifacts to GitHub releases

**Key Deliverables**:
- Repository scaffolding and directory structure
- Build automation (Makefile, latexmk config, release scripts)
- CHANGELOG.md and version management
- GitHub Actions workflows for releases
- Agent configuration files

**Standards Applied**:
- Semantic Versioning (semver.org)
- Keep a Changelog (keepachangelog.com)
- NIST SP 800-53 CM-3 (Configuration Change Control)

---

### Requirements Agent — Compliance Analyst

**Agent Type**: Claude Opus 4.6
**Reports To**: CEO
**Tool Access**: Full read/write + web access

**Responsibilities**:
- Read and interpret government standards (NIST, FIPS, CFR, Executive Orders)
- Generate structured requirements documents in JSON format
- Ensure every requirement includes: unique ID, governing standard, section reference, requirement text, priority (mandatory/recommended), and verification method
- Validate that requirements are complete — no applicable requirements from a cited standard should be omitted
- Flag ambiguous or conflicting requirements for human review
- Use RFC 2119 language correctly (SHALL for mandatory, SHOULD for recommended, MAY for optional)

**Key Deliverables**:
- Requirements documents (REQ-YYYY-NNN.json)
- Standards interpretation memos
- Compliance gap analysis
- Requirement traceability foundations

**Standards Applied**:
- IEEE 29148 (Requirements Engineering)
- RFC 2119 (Requirement Level Keywords)
- FIPS 197, FIPS 140-2/140-3
- NIST SP 800-series (132, 171, 53, 38A, 90A, 63B)
- 32 CFR Part 2002 (Controlled Unclassified Information)
- Executive Order 13556 (CUI Policy)

---

### Implementation Agent — Software Engineer

**Agent Type**: Claude Sonnet 4.5
**Reports To**: CEO
**Tool Access**: Full read/write + terminal

**Responsibilities**:
- Write code that implements requirements from REQ documents
- Ensure all cryptographic operations use platform-provided, validated libraries only
- Never introduce third-party dependencies for security-critical operations
- Follow compliance standards encoded in CLAUDE.md
- Write automated tests that verify compliance requirements
- Document compliance-relevant configuration values with comments citing the governing standard

**Key Deliverables**:
- Production source code (PowerShell, Python, C#, etc.)
- Automated test suites
- Implementation notes linking code to requirements
- Configuration files with regulatory citations

**Standards Applied**:
- NIST SP 800-53 SA-11 (Developer Testing and Evaluation)
- FIPS 197 (AES encryption)
- NIST SP 800-132 (PBKDF2 key derivation)
- NIST SP 800-38A (Block cipher modes)
- 32 CFR Part 2002 (CUI handling)

**Case Study Reference**: [SendCUIEmail](https://github.com/brucedombrowski/SendCUIEmail)

---

### Documentation Agent — Technical Writer

**Agent Type**: Claude Sonnet 4.5
**Reports To**: CEO
**Tool Access**: Full read/write + terminal

**Responsibilities**:
- Write decision memoranda (DMs) documenting design and policy choices
- Generate verification documents (VERs) that map requirements to implementation evidence
- Produce traceability matrices linking requirements → implementation → tests
- Write and edit documentation following project-specific templates (LaTeX, Markdown)
- Maintain bibliography files with accurate citations to government standards
- Update process documentation with session logs and decisions

**Key Deliverables**:
- Decision Memoranda (DM-YYYY-NNN)
- Verification Documents (VER-YYYY-NNN)
- Traceability matrices (JSON and formatted reports)
- White papers and academic publications
- BibTeX files with government standard citations
- User-facing README and CHANGELOG files

**Standards Applied**:
- MIL-STD-498 (Software Development and Documentation)
- IEEE 29148 (Requirements Engineering — traceability aspects)

---

### Review Agent — Quality Assurance Auditor

**Agent Type**: Claude Opus 4.6
**Reports To**: CEO
**Tool Access**: **Read-only** (no Write or Edit tools — enforces separation of duties)

**Responsibilities**:
- Verify requirements documents are complete (no gaps in coverage of cited standards)
- Check citation accuracy: standard numbers, section references, publication dates
- Validate cross-references between documents (REQ ↔ VER ↔ DM ↔ code)
- Flag inconsistencies between requirements and implementation
- Check LaTeX documents for compilation issues, broken references, missing citations
- Review BibTeX entries for accuracy and completeness
- Verify that CUI markings follow 32 CFR Part 2002 formatting
- Report findings with structured severity (CRITICAL/MINOR) per IEEE 1028

**Key Deliverables**:
- Audit reports with structured findings
- GitHub issues documenting critical and minor problems
- Verification status (PASS / PASS WITH NOTES / FAIL)
- Recommendations for corrective action

**Standards Applied**:
- IEEE 1028 (Software Reviews and Audits)
- IEEE 29148 (Requirements Engineering — traceability verification)
- NIST SP 800-53 AC-5 (Separation of Duties)
- NIST SP 800-53 SA-11 (Developer Testing and Evaluation)
- ISO/IEC 25010 (Software Quality)
- MIL-STD-498 A.5.19 (Traceability)

**Key Principle**: The Review Agent has no Write or Edit tools. Auditors identify problems but do not fix them. This enforces the separation of duties required by NIST SP 800-53 AC-5.

---

## How We Work

### Human-AI Collaboration Model

Bruce Dombrowski Inc operates on a **human-in-command, AI-as-specialist** model:

1. **Bruce defines the mission**: Project requirements, compliance objectives, and success criteria come from the human CEO.

2. **Agents execute specialized tasks**: Each AI agent has a narrow, well-defined role. Agents follow encoded compliance standards and produce structured outputs for human review.

3. **Bruce approves all outputs**: No agent has autonomous decision-making authority. All agent outputs (code, documents, requirements, audit findings) are reviewed and approved by the CEO before becoming final.

4. **Interaction logging for audit traceability**: Every significant human-agent interaction is logged as a GitHub issue. This creates a complete audit trail for compliance verification (NIST SP 800-53 AU-3).

5. **Separation of duties**: The Review Agent has read-only access and cannot modify what it audits. This enforces the separation of duties required by federal information security controls.

### Multi-Agent Workflow Example

A typical project follows this workflow:

```
1. CEO → Requirements Agent: "Extract requirements from NIST SP 800-132"
   ↓
2. Requirements Agent → CEO: Produces REQ-2026-001.json
   ↓
3. CEO → Review Agent: "Audit REQ-2026-001.json for completeness"
   ↓
4. Review Agent → CEO: Reports findings (PASS WITH NOTES)
   ↓
5. CEO → Implementation Agent: "Implement REQ-2026-001"
   ↓
6. Implementation Agent → CEO: Produces Encrypt.ps1 with tests
   ↓
7. CEO → Documentation Agent: "Generate VER-2026-001 mapping requirements to code"
   ↓
8. Documentation Agent → CEO: Produces verification document
   ↓
9. CEO → Review Agent: "Audit VER-2026-001 and verify code references"
   ↓
10. Review Agent → CEO: Reports findings (PASS)
    ↓
11. CEO: Approves release
```

### Agent Invocation

Agents can be invoked individually or as a coordinated team:

**Single agent mode**:
```bash
claude --model opus   # For requirements or review work
claude --model sonnet # For implementation or documentation
```

**Multi-agent mode** (using the configuration file):
```bash
claude --agents "$(cat claude/agents.json)"
```

### Interaction Logging (Audit Trail)

All agents are required to log significant interactions as GitHub issues:

- **human-prompt**: When the CEO assigns a task to an agent
- **agent-output**: When an agent produces findings or deliverables
- **decision**: When the CEO approves, rejects, or modifies an agent's output

This creates a complete, auditable record of all project decisions and work products, as required by NIST SP 800-53 AU-3 (Audit and Accountability — Content of Audit Records).

---

## Technology Stack

- **AI Platform**: Claude (Anthropic)
  - **Opus 4.6**: High-reasoning tasks (requirements analysis, quality assurance)
  - **Sonnet 4.5**: Balanced speed/quality (implementation, documentation, infrastructure)

- **Development Tools**: Claude Code CLI, Git, GitHub Actions, LaTeX, PowerShell, Python

- **Standards Framework**: IEEE 1028, IEEE 29148, NIST SP 800-series, FIPS, MIL-STD-498

---

## Projects

Bruce Dombrowski Inc delivers government-quality software and compliance documentation. Current projects include:

- **[WhitePaper](https://github.com/brucedombrowski/WhitePaper)** — Academic paper examining AI-assisted development for federal information security requirements
- **[SendCUIEmail](https://github.com/brucedombrowski/SendCUIEmail)** — CUI file encryption tool addressing FIPS 140-2, NIST SP 800-132, and 32 CFR Part 2002
- **[Security Toolkit](https://github.com/brucedombrowski/security-toolkit)** — Automated NIST control verification
- **[Scrum](https://github.com/brucedombrowski/Scrum)** — Scrum Guide implementation with AI agents
- **[LaTeX](https://github.com/brucedombrowski/LaTeX)** — LaTeX templates for government compliance documents
- **[ai-agents](https://github.com/brucedombrowski/ai-agents)** — Canonical agent role templates for government compliance projects

---

## Why This Structure Works

1. **Specialization**: Each agent has a narrow, well-defined role. This reduces the risk of scope creep and improves output quality.

2. **Compliance by design**: Agent prompts encode federal information security standards. Compliance requirements are baked into the workflow, not bolted on afterward.

3. **Auditability**: Every interaction is logged as a GitHub issue. This creates a complete audit trail for verification and certification.

4. **Separation of duties**: The Review Agent cannot modify what it audits. This enforces the separation of duties required by NIST SP 800-53 AC-5.

5. **Human accountability**: Bruce approves all outputs. The AI agents are tools, not autonomous decision-makers. This preserves human accountability and judgment.

6. **Model-agnostic design**: Agent role definitions describe *what* each agent does, not *how* a specific model implements it. This makes the workflow portable across AI platforms.

---

## License

MIT License — See [LICENSE](../LICENSE) file.

---

## Contact

**Bruce Dombrowski**
GitHub: [@brucedombrowski](https://github.com/brucedombrowski)

---

*This document describes the organizational structure of Bruce Dombrowski Inc as of February 2026. All AI agents are powered by Claude (Anthropic). Human accountability and compliance-by-design are core principles.*
