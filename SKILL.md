---
name: brain-decisions
description: >-
  Mines conversation history and codebase changes for architectural decisions, design choices,
  and settled trade-offs (the 'Why'), formats them into structured Architecture Decision Records (ADRs),
  and saves them to Second Brain with #decision !durable.
---

# Brain Decisions — Architectural Decision Record Miner (`/brain-decisions`)

Use this skill to extract the critical design decisions and trade-offs made during a session so you never wonder "why did we build it this way?" months later.

---

## What Happens When Invoked

When `/brain-decisions` is triggered, execute these steps:

### Step 1: Detect Settled Architectural Choices
Inspect the conversation history and code diffs for:
- Comparisons between technologies, libraries, or architectures (e.g. choice of UI toolkit, transport protocol, file formats)
- Fixed technical trade-offs (e.g. polling vs event-driven, memory vs cpu optimizations, sample rate decisions)
- Rejections of specific approaches with the reason why
- Invariant rules or non-negotiable project conventions adopted

### Step 2: Format into Lightweight ADRs
Structure each discovered decision into standard ADR format:
- **Title**: Short summary of choice (e.g. `Use UDP Unicast for Local Live Actions OSC`)
- **Context**: The problem being solved or constraint faced
- **Decision**: The selected path and specific configuration
- **Consequences**: What this enables and what trade-offs were accepted

### Step 3: Check Second Brain for Duplicates
Query `second-brain` using `recall` with `--tag decision` to ensure the decision isn't already stored.

### Step 4: Output and Save
Present the formatted ADRs with pre-configured save commands:
```
/brain-save ADR: Chose UDP Unicast on port 9001 for Live Actions bridge to eliminate TCP handshake latency #decision #live-actions !durable
```
If the user confirms, call `remember` immediately with `volatility: "durable"` and `#decision` tag.

---

## Syntax

```
/brain-decisions [optional project or topic]
```

## Examples

```
/brain-decisions
/brain-decisions Live Actions Helper
```
