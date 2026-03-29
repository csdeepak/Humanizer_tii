# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## What this repo is
This repository is a **Claude skill** implemented entirely as Markdown.

The runtime artifact is `SKILL.md`: Claude reads the YAML frontmatter (metadata + allowed tools) and the multi-stage processing pipeline that follows.

`README.md` is for humans: installation, usage, pipeline overview, and pattern reference tables.

## Key files (and how they relate)
- `SKILL.md`
  - The actual skill definition (v3.0.0).
  - Starts with YAML frontmatter (`---` … `---`) containing `name`, `version`, `description`, and `allowed-tools`.
  - After the frontmatter: SYSTEM CORE identity, USER CONTROLS, and a 4-stage processing pipeline (Structural Recomposition → Linguistic Normalization → Pattern Disruption → Final Validation).
  - Includes a comprehensive 25-pattern AI writing reference guide.
- `README.md`
  - Installation and usage instructions (including ZIP download for Claude skill upload).
  - Pipeline diagram, user controls table, summarized pattern tables, and version history.
- `LICENSE`
  - MIT License.

When changing behavior/content, treat `SKILL.md` as the source of truth, and update `README.md` to stay consistent.

## Common commands
### Install the skill into Claude Code
Recommended (clone directly into Claude Code skills directory):
```bash
mkdir -p ~/.claude/skills
git clone https://github.com/csdee/Humanizer_tii.git ~/.claude/skills/humanizer
```

### Upload to Claude (via ZIP)
1. Download ZIP from GitHub
2. Extract and upload `SKILL.md` to Claude as a project file

## How to "run" it (Claude)
- Upload `SKILL.md` as a skill/project file, then paste academic text
- Or in Claude Code: `/humanizer` then paste text

## Making changes safely
### Versioning (keep in sync)
- `SKILL.md` has a `version:` field in its YAML frontmatter.
- `README.md` has a "Version history" section.

If you bump the version, update both.

### Editing `SKILL.md`
- Preserve valid YAML frontmatter formatting and indentation.
- Keep the 4-stage pipeline structure intact.
- Keep the pattern numbering stable unless intentionally re-numbering.

### Documenting non-obvious fixes
If you change the prompt to handle a tricky failure mode, add a note to `README.md`'s version history describing what was fixed and why.