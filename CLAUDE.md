# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

This is `iammanhIoi/iammanhIoi` — a GitHub profile repository. Its sole purpose is to render the profile README shown on https://github.com/iammanhIoi. There is no application code, build system, linter, or test suite here.

## Structure

- `README.md` — the profile page content (badges, tech stack, experience, contact links). This is the only file that matters functionally; edits here directly change what visitors see on the GitHub profile.
- `AGENTS.md` — a generic Codex/skills-workspace contributor guide (references a `skills/<skill-name>/` layout, `config.toml`, validator scripts, etc.). None of that structure actually exists in this repository — treat `AGENTS.md` as stale/inherited boilerplate, not a description of this repo's real layout.
- `.gitignore` — ignores `.idea/` (JetBrains project files).

## Working in this repo

- Changes are almost always edits to `README.md` (badges via shields.io, section content, links).
- There is nothing to build, lint, or test — verify changes by checking the rendered Markdown reads correctly (e.g. via a Markdown preview) rather than running any command.
- Keep badge/shield URLs and styling consistent with the existing ones when adding new badges.
