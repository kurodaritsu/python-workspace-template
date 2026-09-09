# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

`python-workspace-template` is a git template repo that is used as its base contents for other Python projects. It uses **uv** for package management, **ruff** for linting and formatting, **ty** for type checking, and **pytest** for testing.

## Workflow

- Check if the user is building something using this template by checking its remote repository name:
  ```bash
  # NOTE: This may also exit non-zero if there's no repo configured
  git remote get-url origin
  ```
- If the user asks you to build something with this repository template as its context, you might as well edit this file (`CLAUDE.md`) to something that fits to your development workflow.
- The `app/`, `data/`, `docs/`, `models/`, `notebooks/` and `scripts/` are placeholder directories. You may delete them by removing `.gitkeep` inside of each directory depending on your use case on this repo.
- If you're using `src/`, rename the module docstrings `"""` in [`src/__init__.py`](./src/__init__.py).
- Rename the project name in [`pyproject.toml`](./pyproject.toml) accordingly.
- Ask the user if they want to keep the MIT License initially configured here if they are making a new project with this template. Make changes on the owner name and year if necessary. If the user asks for another license, apply it to [`LICENSE`](./LICENSE).

## Preset Rules & Skills

Behavioral guidance lives in `.claude/rules/`. These can be changed based on user's preference.

- [`package-management.md`](.claude/rules/package-management.md) - uv dependency management
- [`lint-and-format.md`](.claude/rules/lint-and-format.md) - ruff linting and formatting policy
- [`logging.md`](.claude/rules/logging.md) - use `get_logger`, never `print()`
- [`type-checking.md`](.claude/rules/type-checking.md) - ty type checker policy
- [`git-workflow.md`](.claude/rules/git-workflow.md) - feature branches, protected main
