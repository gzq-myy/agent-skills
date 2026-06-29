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

Use the short Codex entrypoint skills in chat:

```text
@agent-spec
@agent-plan
@agent-build
@agent-build auto
@agent-test
@agent-review
@agent-ship
@agent-code-simplify
@agent-webperf
```

These mirror the Claude Code slash command workflows. Codex does not currently
register plugin-provided slash commands, so these entrypoints use the
`agent-*` prefix to avoid collisions with built-in commands.

You can still invoke the underlying lifecycle skills directly, such as
`@spec-driven-development` or `@planning-and-task-breakdown`, when you want the
base workflow without command-style orchestration.

## How it works

- `.agents/plugins/marketplace.json` declares this repository as a Codex
  marketplace and points the `agent-skills` plugin at the repository root.
- `.codex-plugin/plugin.json` is the Codex plugin manifest.
- `skills/` is the shared skill directory consumed by Codex and other agents.
  Short wrapper skills such as `@agent-spec`, `@agent-plan`, and `@agent-build` provide Codex
  entrypoints for the Claude Code slash command workflows.

Claude Code slash commands in `.claude/commands/` remain Claude-specific. In
Codex, use the corresponding entrypoint skill instead of the slash command.

## Troubleshooting

If Codex lists the marketplace but the plugin is not installed, run:

```bash
codex plugin add agent-skills@agent-skills
```

If you change the plugin manifest or skills locally, reinstall the plugin and
start a new Codex thread so the cached plugin bundle is refreshed.
