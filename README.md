# Worldwide Researcher

An evidence-first, multilingual research skill for **OpenAI Codex**. It identifies research questions, searches original evidence across countries and languages, weighs contrary findings, preserves an evidence ledger, and produces cited Markdown or PDF reports.

The project is **one Codex skill** with bundled reference files and four optional native agent **roles** used by its substantial-research workflow. Multiple topic researchers can be spawned as needed; this is not a separate hosted application.

## Contents

- `research-worldwide/SKILL.md` — research operating contract and quality gates.
- `research-worldwide/agents/openai.yaml` — skill metadata.
- `research-worldwide/references/source-index.md` — compact source router.
- `research-worldwide/references/source-catalog.md` — tested public/no-key source entrypoints.
- `research-worldwide/references/research-workflow.md` — detailed research procedure.
- `codex-agents/worldwide_planning_critic.toml` — independent pre-search critique.
- `codex-agents/worldwide_topic_researcher.toml` — original-source workstreams.
- `codex-agents/worldwide_challenge_researcher.toml` — counterevidence and discovery audit.
- `codex-agents/worldwide_final_report_critic.toml` — report and PDF review.

## Installation (Linux / macOS, Codex)

Clone this repository with your GitHub account (private-repo access is required):

```bash
gh repo clone dundunna1990/research-worldwide
cd research-worldwide
mkdir -p ~/.codex/skills ~/.codex/agents
cp -R research-worldwide ~/.codex/skills/
cp codex-agents/*.toml ~/.codex/agents/
```

If an installed copy already exists, back it up and reconcile local changes before replacing it. Then restart or reopen Codex so the skill and roles can be discovered.

For native multi-agent support, ensure your installed Codex version supports and enables `multi_agent`. A **separate** local setting in `~/.codex/config.toml` may be used to cap simultaneous subagents:

```toml
[agents]
max_concurrent_threads_per_session = 6
```

The lead agent may occupy an additional slot in Codex versions where subagent limits are counted separately. **Do not overwrite your existing Codex config**: merge this setting only if appropriate for your version. This repository deliberately does **not** contain the owner's full local Codex config, credentials, machine-specific paths, prior research workspaces, source hunters, or run logs.

## Use

In Codex, request:

```text
Use $research-worldwide to investigate [your research question].
```

For substantial investigations the skill will ask whether the final deliverable should be Markdown or PDF if you have not already specified a format.

## Research integrity

The source catalog is a **routing guide, not a whitelist**. Entries represent historically tested public access routes; availability, access rules, URLs and the underlying scholarship may change. The researcher must inspect original evidence and cite it accurately, challenge its own hypotheses, disclose uncertainty, and not mistake AI review for external scientific peer review.

The multi-agent workflow is designed for complex questions; simple factual questions should remain proportionate. Publication PASS decisions require actually executed reviews and verified evidence, not merely a success claim.

## Project scope

This repository contains the shareable skill and role configurations only. Automated source-hunter programs, local SQLite databases, temporary candidates, personal workspace files, and previously generated reports are maintained separately.
