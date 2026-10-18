# 1. Record architecture decisions

- Status: accepted
- Date: 2026-10-17

## Context

We need to record the architectural decisions made on this project so that
current and future contributors understand the reasoning behind them.

## Decision

We will use Architecture Decision Records (ADRs), as described by Michael Nygard.
Each significant architectural decision is documented as a short, numbered file
in `doc/adr/`.

The template is:

```markdown
# N. Short title of the decision

- Status: proposed | accepted | deprecated | superseded by [ADR-XXXX](XXXX-....md)
- Date: YYYY-MM-DD

## Context

What is the issue that we are seeing that is motivating this decision?

## Decision

What is the change that we are actually proposing or doing?

## Consequences

What becomes easier or harder because of this change?
```

## Consequences

- Architectural decisions and their rationale are discoverable.
- New contributors can understand the project's evolution.
- Contributors are expected to add an ADR for significant changes.
