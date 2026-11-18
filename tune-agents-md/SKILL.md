---
name: tune-agents-md
description: Draft, audit, or revise AGENTS.md using durable project conventions, user preferences, recurring corrections, and explicit permission boundaries.
---

# Tune AGENTS.md

Keep the rules that will change how an agent handles future work in the target scope. Use the user's request to decide whether to deliver a draft, report findings, or edit the file.

1. **Inspect the scope.** Locate the target `AGENTS.md` or its intended directory. Read relevant parent and nested instructions where available. Check existing docs, configuration, and check commands before proposing rules. Keep shared rules at the root and directory-specific rules near the affected files.
2. **Gather evidence.** Look for stable user preferences, hard-to-find sources of truth, authorization boundaries, and recurring corrections. Use the user's examples, existing instructions, and any retrospective findings they supply. When an essential convention or permission is unclear, ask a focused question about it and use the answer. Leave unrelated preferences and hypothetical restrictions out.
3. **Choose where the rule belongs.** Keep durable defaults and non-obvious project conventions in `AGENTS.md`. Use a relative link with a clear trigger for detailed guidance needed only on particular tasks. Leave one-off requirements in the task. Point to authoritative docs and commands where an agent can already look them up. For mistakes that tools can detect, favor automated checks. For actions that must be blocked, use tool permissions or other enforceable controls. Raise those changes separately when they fall outside this request.
4. **Write for execution.** State the condition, action, and any known exception. Where authorization matters, distinguish what the agent may do directly, what requires approval, and what is prohibited. Keep the user's existing boundaries unless they request a change. Make completion checks observable.

For example, replace “Keep the catalog up to date” with “When adding, removing, or renaming a skill, update both language editions of the catalog and verify each affected link resolves to the skill's entry point.”

Before handing off, check each retained or added rule against a plausible future task. Identify what the agent should do differently, verify paths and commands against the workspace where possible, and resolve duplication without losing requirements. Summarize changes or findings and flag decisions that still need the user. Revisit rules after real use and prune stale or ineffective entries.
