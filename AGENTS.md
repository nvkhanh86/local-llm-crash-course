# AGENTS.md

## Repository

`nvkhanh86/local-llm-crash-course`

## Git-first prompt handoff — mandatory

For every Git-first workflow, the full executable prompt/spec must be durable on Git before another AI is invoked.

- Store the complete action, scope, constraints, acceptance gates, evidence references, and stop boundary in the canonical task/handoff/decision/verification artifact on the authorized branch.
- Chat prompts to Claude, Codex, Cursor, ChatGPT, or any other coding agent are short pointer prompts only: identify the task/role, refresh Git, read the latest canonical task/handoff/full prompt from Git, execute the authorized action, and obey the durable stop boundary.
- Do not repeat long history, matrices, SHAs, diagnosis, or evidence in chat when they already exist on Git.
- If the full prompt is not durable yet, publish it first; do not substitute a long chat prompt.
- The receiving AI must refresh remote state and retrieve the full prompt from Git before acting. Chat is a wake-up pointer, not the source of truth.
- Temporary exception: only when Git is unavailable and the owner explicitly authorizes a temporary non-durable handoff. Durable Git publication must be the next lifecycle action.

Default pointer prompt:

```text
Continue <TASK-ID>.
Git is source of truth.
Refresh <canonical-branch>.
Read the latest canonical task/handoff and the full prompt/spec stored on Git.
Execute only the authorized next action and obey the durable stop boundary.
```

## Core rule

Preserve repository-specific scope and existing human approval gates. Remote Git durable state outranks chat history.
