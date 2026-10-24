# Brain Decisions

> **Tri-Platform Agent Skill** for Claude Desktop / Code, Grok CLI, and Google Antigravity / Gemini.  
> Architecture Decision Record (ADR) Miner — Mines conversation history and codebase changes for architectural decisions, design choices, and settled trade-offs, formatting them into durable ADRs.

---

## Overview

`brain-decisions` provides standardized capabilities across conversational AI platforms:
- Automatic extraction of design trade-offs, discarded alternatives, and 'Why' rationale.
- Standard ADR schema (Context, Decision, Consequences, Status).
- Durable persistence with #decision and !durable flags.
- Tri-platform NTFS junctions connecting Claude, Grok, and Antigravity.
- Standard documentation suite: SKILL.md, HOW_TO_USE.txt, IMPLEMENTATION_PLAN.md, and README.md.

---

## Tri-Platform Architecture

Zero duplicate code across platforms. Canonical source resides in `.agents`:
- **Canonical Source**: `C:\Users\<you>\.agents\skills\brain-decisions`
- **Claude**: `C:\Users\<you>\.claude\skills\brain-decisions` (NTFS Junction)
- **Grok**: `C:\Users\<you>\.grok\skills\brain-decisions` (NTFS Junction)
- **Antigravity**: `C:\Users\<you>\.gemini\config\skills\brain-decisions` (NTFS Junction)

---

## Documentation Suite

- [`HOW_TO_USE.txt`](HOW_TO_USE.txt): Standardized user guide and prompt templates.
- [`IMPLEMENTATION_PLAN.md`](IMPLEMENTATION_PLAN.md): Feature checklist and roadmap.
- [`App Changes Tracker.html`](App%20Changes%20Tracker.html): Interactive visual version log.
- [`SKILL.md`](SKILL.md): Agent system instructions and triggers.
