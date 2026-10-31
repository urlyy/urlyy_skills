# Repository maintenance

These instructions apply to any agent maintaining this repository.

## Structure and scope

- Keep every skill in a root-level folder whose name matches its SKILL.md frontmatter. Reserve visible root folders for skills; keep repository-wide documentation as root files. Derive the current catalog from the filesystem.
- Add or remove skills only within the requested scope. Read the target SKILL.md and relevant resources before editing. When changing agent-facing instructions, follow writing-for-agents/SKILL.md.
- Each skill must work when its entire folder is copied on its own. Bundle required skill dependencies under its references/ directory, including transitive resources. Use GUIDE.md rather than SKILL.md for bundled dependencies and omit their standalone agent metadata. Direct the agent to read these resources without asking users to install other skills. Keep duplicated resources synchronized.
- Treat skill workflows as source material during maintenance; editing a workflow does not authorize executing it.
- Preserve invocation policies unless a change is requested. Declare runtime requirements and keep instructions free of credentials and personal absolute paths.

## Documentation, sources and licenses

- Maintain README.md and README.en.md together. Keep their catalogs, capabilities, examples, installation guidance, requirements and source acknowledgments consistent with each other and with the files on disk.
- Keep README guidance focused on using the skills. AGENTS.md is read by agents directly and needs no README navigation link.
- Acknowledge upstream repositories with verified links in both READMEs. Keep acknowledgments concise; a separate attribution report or duplicate root-level license archive is unnecessary unless required by upstream terms.
- Preserve applicable upstream LICENSE, NOTICE, copyright and credit files inside each skill, including those required for bundled dependencies. The root license covers original repository contributions only; it does not relicense imported content.
- Check license evidence before importing or updating third-party material. Do not invent a license or treat a missing or conflicting declaration as permission. Record material uncertainty briefly and accurately. Preserve modification notices when upstream terms require them.
- Keep this file reusable across sessions: document lasting conventions, not conversation history, temporary task status, fixed skill counts or machine-specific details.

## Completion checks

Before reporting any maintenance task complete:

1. Check both READMEs against the actual skill folders and the changed behavior. Correct stale counts, names, paths, examples and requirements; preserve unrelated user edits.
2. Check affected Markdown links and resource references, including bundled dependencies. Remove stale references to renamed or deleted files. Verify that required resources stay within each independently usable skill folder.
3. Check frontmatter names, entry points and invocation metadata for changed skills. Confirm bundled guides are not exposed as independent skills.
4. Check that source acknowledgments and applicable license files remain present and agree with the imported material. Avoid duplicate archives that add no required notice.
5. Run relevant existing checks when scripts or runtime behavior change. Report what was actually verified; static documentation checks do not establish runtime or cross-client compatibility.

Before deleting imported source folders, verify retained resources and license evidence were copied. Remove unnecessary nested .git metadata when importing skills, but never delete the repository's root .git directory. Commit, push or publish only when authorized by the task.
