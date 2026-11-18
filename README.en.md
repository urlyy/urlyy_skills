# urlyy_skills

These are the 20 agent skills I selected for this repository. They help with writing, clarifying requirements, developing software and explaining concepts visually. Each skill has its own folder at the root, with a `SKILL.md` entry point and the scripts, templates and references it needs.

[中文](README.md)

## Catalog

| Skill | Description | When to use | Source |
| --- | --- | --- | --- |
| [sloptrim-zh](sloptrim-zh/SKILL.md) | Natural Chinese editing while preserving facts and voice | Articles, emails and reports | [Link](https://github.com/ismilewolf-eng/sloptrim-zh) |
| [ste-writing](ste-writing/SKILL.md) | Rewrite prose in Simplified Technical English | Technical docs, READMEs and error messages | [Link](https://github.com/woosal1337/blog/blob/main/videos/ep01-the-cure-for-ai-slop/ste-writing-skill.md) |
| [grill](grill/SKILL.md) | Expose assumptions through focused questions | Unclear ideas and plan stress tests | [Link](https://github.com/nagi-studio/skills/tree/main/skills/pondering/grill) |
| [architect](architect/SKILL.md) | Compare and recommend technology stacks | Framework, database and deployment choices | [Link](https://github.com/nagi-studio/skills/tree/main/skills/rookie/architect) |
| [prove-it](prove-it/SKILL.md) | Require observable evidence of completion | Acceptance checks, recurring mistakes and test quality | [Link](https://github.com/nagi-studio/skills/tree/main/skills/rookie/prove-it) |
| [to-spec](to-spec/SKILL.md) | Turn an existing discussion into a specification | After discovery, before implementation | [Link](https://github.com/mattpocock/skills/tree/main/skills/engineering/to-spec) |
| [to-tickets](to-tickets/SKILL.md) | Split work into verifiable vertical slices and dependencies | Feature breakdown and sequencing | [Link](https://github.com/mattpocock/skills/tree/main/skills/engineering/to-tickets) |
| [implement](implement/SKILL.md) | Implement a specification or tickets | Coding against agreed requirements | [Link](https://github.com/mattpocock/skills/tree/main/skills/engineering/implement) |
| [implement-spec](implement-spec/SKILL.md) | Write code from a specification and its tickets | Following to-spec and to-tickets | [Link](https://github.com/mattpocock/skills/tree/main/skills/engineering/implement-spec) |
| [tdd](tdd/SKILL.md) | Develop through red/green test cycles | Test-first features and fixes | [Link](https://github.com/mattpocock/skills/tree/main/skills/engineering/tdd) |
| [diagnosing-bugs](diagnosing-bugs/SKILL.md) | Diagnose through reproduction and controlled experiments | Difficult bugs and performance regressions | [Link](https://github.com/mattpocock/skills/tree/main/skills/engineering/diagnosing-bugs) |
| [code-review](code-review/SKILL.md) | Review against repository standards and requirements | PR, branch and working-tree reviews | [Link](https://github.com/mattpocock/skills/tree/main/skills/engineering/code-review) |
| [pr](pr/SKILL.md) | Write reviewable pull request descriptions | Preparing a pull request | [Link](https://github.com/mattpocock/skills/tree/main/skills/engineering/pr) |
| [retro](retro/SKILL.md) | Review lessons from a coding session | End-of-session process improvements | [Link](https://github.com/mattpocock/skills/tree/main/skills/engineering/retro) |
| [wait-what](wait-what/SKILL.md) | Re-explain the previous answer | An explanation did not land | [Link](https://github.com/mattpocock/skills/tree/main/skills/productivity/wait-what) |
| [handoff](handoff/SKILL.md) | Document progress so another chat or agent can continue | Switching chats or agents | [Link](https://github.com/mattpocock/skills/tree/main/skills/productivity/handoff) |
| [writing-for-agents](writing-for-agents/SKILL.md) | Write actionable instructions for agents | Skills, AGENTS.md and CLAUDE.md | [Link](https://github.com/mattpocock/skills/tree/main/skills/productivity/writing-for-agents) |
| [tune-agents-md](tune-agents-md/SKILL.md) | Draft, audit or refine AGENTS.md | Durable rules, permission boundaries and recurring corrections | [Reference video](https://www.bilibili.com/video/BV13a4x6hEc1/) |
| [eli5](eli5/SKILL.md) | Explain concepts with simple text and HTML visuals | Learning unfamiliar concepts | [Link](https://github.com/anthropics/claude-plugins-community/tree/main/eli5/skills/eli5) |
| [html-plan](html-plan/SKILL.md) | Create an interactive HTML implementation plan | Reviewing design decisions before coding | [Link](https://github.com/anthropics/claude-plugins-community/tree/main/html-plan/skills/html-plan) |

## Getting started

1. Clone: `git clone https://github.com/urlyy/urlyy_skills.git`.
2. Copy each selected whole folder into the skill directory supported by your agent. Do not copy only `SKILL.md`; consult your client for its installation location.
3. Alternatively, ask the agent to read the local entry point directly: `Read grill/SKILL.md and follow it to clarify this idea: ...`.
4. Supply inputs, constraints and acceptance criteria. Use `/skill-name` or `$skill-name` only where your client supports that syntax.

### Example workflows

- Writing: use `sloptrim-zh` to edit a Chinese report without adding facts; use `ste-writing` for English technical prose.
- Discovery: use `grill` to expose unknowns, then `architect` to compare stacks.
- Delivery: use `to-spec`, then `to-tickets`, then either `implement` or `implement-spec`.
- Debugging: use `diagnosing-bugs` to establish a reproduction and investigate.
- Verification: use `code-review` for review and `prove-it` for acceptance evidence.
- Explanation: use `eli5` for a concept and `html-plan` for a proposed implementation.

The implementation skills overlap; usually select one. Some upstream workflows include commits, issue publishing and configuration changes. Specify the authorized scope when invoking them.

### Choosing a skill after a session

If a session went wrong and you're unsure what to change, use [retro](retro/SKILL.md). It reviews the session and ranks suggested improvements by severity. If you want the agent to edit a skill, add a test, or wire up a check, say what it can change in your prompt.

> Use `retro` to review this session and point out what went wrong. Where the evidence is clear, update the relevant skill in this project or add a regression test. Run the relevant checks afterward.

If a feature is done and you want to record how to maintain it in `AGENTS.md`, go straight to [tune-agents-md](tune-agents-md/SKILL.md). Link to an existing design doc and say when to read it.

> Use `tune-agents-md` to review this session, the requirements, and the code changes. Write down the conventions future maintainers will need in the nearest `AGENTS.md` that applies to the code. Say when each rule applies, what to do, and how to check the result. If there's a design doc, give its path and say when to read it.

## Dependencies and requirements

- `to-spec`, `to-tickets`, `implement-spec` and `code-review` bundle the upstream setup workflow and templates under `references/setup/`. These guides are loaded when project configuration is missing and are not separate discoverable skills.
- Each skill bundles its required guides: implementation includes TDD and review, retrospective includes writing guidance, and TDD includes module design. No separate skill installation is required; the agent reads internal resources as needed.
- Detection scripts require Python 3. `html-plan/runtime/pack.mjs` requires Node.js. External trackers require their connector or CLI and authorization.
- Existing metadata is preserved. Tool names, invocation policies and subagent support vary by client; full cross-client compatibility has not been validated.

## Sources

This collection draws on the following skills and references. Thanks to their authors:

- [sloptrim-zh](https://github.com/ismilewolf-eng/sloptrim-zh)
- [ste-writing](https://github.com/woosal1337/blog/blob/main/videos/ep01-the-cure-for-ai-slop/ste-writing-skill.md)
- [Nagi Studio Skills](https://github.com/nagi-studio/skills)
- [Matt Pocock Skills](https://github.com/mattpocock/skills)
- [Claude Plugins Community](https://github.com/anthropics/claude-plugins-community) (eli5, html-plan)
- [主题学习社 · 如何写好 Agents.md](https://www.bilibili.com/video/BV13a4x6hEc1/) (reference video for tune-agents-md)

Skills retain their original licenses. The root MIT license applies to this repository's original skills, documentation and maintenance contributions.
