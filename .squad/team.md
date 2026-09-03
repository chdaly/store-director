# Squad Team

> store-director

## Coordinator

| Name | Role | Notes |
|------|------|-------|
| Squad | Coordinator | Routes work, enforces handoffs and reviewer gates. |

## Members

| Name | Role | Charter | Status |
|------|------|---------|--------|
| Lead | Experience Lead | .squad/agents/lead/charter.md | 🏗️ Active |
| Narrative | Content Designer | .squad/agents/narrative/charter.md | 📝 Active |
| Data | BI Simulator | .squad/agents/data/charter.md | 📊 Active |
| Frontend | Prototype Dev | .squad/agents/frontend/charter.md | ⚛️ Active |
| Tester | Demo QA | .squad/agents/tester/charter.md | 🧪 Active |
| Scribe | Session Logger | .squad/agents/scribe/charter.md | 📋 Scribe |
| Ralph | Work Monitor | .squad/agents/ralph/charter.md | 🔄 Monitor |
| Rai | RAI Reviewer | .squad/agents/Rai/charter.md | 🛡️ RAI |
| Fact Checker | Fact Checker | .squad/agents/fact-checker/charter.md | 🔍 Verifier |

## Coding Agent

<!-- copilot-auto-assign: false -->

| Name | Role | Charter | Status |
|------|------|---------|--------|
| @copilot | Coding Agent | — | 🤖 Coding Agent |

### Capabilities

**🟢 Good fit — auto-route when enabled:**
- Bug fixes with clear reproduction steps
- Test coverage (adding missing tests, fixing flaky tests)
- Lint/format fixes and code style cleanup
- Dependency updates and version bumps
- Small isolated features with clear specs
- Boilerplate/scaffolding generation
- Documentation fixes and README updates

**🟡 Needs review — route to @copilot but flag for squad member PR review:**
- Medium features with clear specs and acceptance criteria
- Refactoring with existing test coverage
- API endpoint additions following established patterns
- Migration scripts with well-defined schemas

**🔴 Not suitable — route to squad member instead:**
- Architecture decisions and system design
- Multi-system integration requiring coordination
- Ambiguous requirements needing clarification
- Security-critical changes (auth, encryption, access control)
- Performance-critical paths requiring benchmarking
- Changes requiring cross-team discussion

## Project Context

- **Project:** store-director
- **Owner:** Chris Daly
- **Goal:** A shareable, fully self-contained HTML page simulating how M365 Copilot + Power BI transforms data consumption for Target Store Directors — replacing morning report prep and review with narrative delivery.
- **Deliverable:** One `.html` file, zero external dependencies, runs from `file://`
- **Background research:** `docs/store-director-background/`
- **Created:** 2026-09-03
