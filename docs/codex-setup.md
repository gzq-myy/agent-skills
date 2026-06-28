# Using agent-skills with Codex

This repository can be used as a Codex plugin. Codex reads the repository's
existing `skills/` directory directly, so the skill content stays in one place.

## Install from this clone

From a local checkout of this repository:

```bash
codex plugin marketplace add /path/to/agent-skills
codex plugin add agent-skills@agent-skills
```

For this machine, the path is:

```bash
codex plugin marketplace add /Users/gaozhengqi/Code/agent-skills
codex plugin add agent-skills@agent-skills
```

Verify the plugin is visible:

```bash
codex plugin list
```

Start a new Codex thread after installing so the updated plugin catalog is
loaded.

## Install from a fork

After pushing these files to your own fork or branch:

```bash
codex plugin marketplace add yourname/agent-skills --ref codex-plugin-support
codex plugin add agent-skills@agent-skills
```

If you merge the change into the fork's default branch, omit `--ref`.

## Usage

Invoke a skill directly in Codex chat with `@`, for example:

```text
@spec-driven-development
@planning-and-task-breakdown
@incremental-implementation
@test-driven-development
@code-review-and-quality
```

You can also describe the task normally and let Codex choose the matching skill
when plugin skills are available.

## How it works

- `.agents/plugins/marketplace.json` declares this repository as a Codex
  marketplace and points the `agent-skills` plugin at the repository root.
- `.codex-plugin/plugin.json` is the Codex plugin manifest.
- `skills/` is the shared skill directory consumed by Codex and other agents.

Claude Code slash commands in `.claude/commands/` remain Claude-specific. In
Codex, use the underlying skill name instead of the slash command.

## Troubleshooting

If Codex lists the marketplace but the plugin is not installed, run:

```bash
codex plugin add agent-skills@agent-skills
```

If you change the plugin manifest or skills locally, reinstall the plugin and
start a new Codex thread so the cached plugin bundle is refreshed.
