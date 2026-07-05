# Repository Guidelines

## Project Structure & Module Organization

This repository is a local Codex workspace centered on reusable skills.

- `skills/<skill-name>/SKILL.md`: required skill definition and instructions.
- `skills/<skill-name>/scripts/`: deterministic helper scripts, usually Python.
- `skills/<skill-name>/references/`: detailed documentation loaded only when needed.
- `skills/<skill-name>/assets/`: templates, fonts, images, and other output resources.
- `skills/<skill-name>/evaluations/`: JSON scenarios and optional evaluation notes.
- `config.toml`: local Codex configuration.

Generated runtime directories such as `sessions/`, `cache/`, `log/`, `memories/`, and `shell_snapshots/` are not source modules.

## Build, Test, and Development Commands

There is no repository-wide build system. Validate and test the skill you changed.

```bash
python3 -m pip install PyYAML
python3 skills/skill-creator/scripts/quick_validate.py skills/my-skill
```

Install `PyYAML` once. The validator checks `SKILL.md` frontmatter, required fields, and naming constraints.

Package a completed skill with:

```bash
python3 skills/skill-creator/scripts/package_skill.py skills/my-skill
```

For skills with dependencies, install from the local requirements file:

```bash
python3 -m pip install -r skills/slack-gif-creator/requirements.txt
```

## Coding Style & Naming Conventions

Use lowercase hyphen-case for skill directories and frontmatter names, such as `issue-triage`. Skill names must be at most 64 characters. Every `SKILL.md` must begin with YAML frontmatter containing concise `name` and `description` fields.

Keep skill instructions direct and under 500 lines. Move detailed material into `references/`. Python scripts use four-space indentation, `snake_case` names, and standard-library solutions where practical. Preserve existing style in Markdown, JSON, and YAML. Avoid redundant README or changelog files inside skills.

## Testing Guidelines

Run `quick_validate.py` for every new or modified skill. Execute changed scripts with representative inputs. When an `evaluations/` directory exists, follow its `README.md` and manually verify each JSON scenario against specific, observable success criteria.

## Commit & Pull Request Guidelines

No Git history is available in this workspace, so use concise imperative commit messages, for example `Add evaluation cases for issue triage`. Keep each commit scoped to one skill or concern.

Pull requests should explain the trigger or use case, list validation performed, and note new dependencies or assets. Include screenshots only for visual outputs.

## Security & Configuration

Never commit `auth.json`, session data, SQLite databases, logs, caches, or secrets from `config.toml`. Review generated assets for sensitive user or workspace content before sharing.
