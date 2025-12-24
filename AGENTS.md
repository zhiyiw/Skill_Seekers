# Repository Guidelines

## Project Structure & Module Organization
- `src/skill_seekers/`: core package (CLI, MCP, scraping, packaging).
- `tests/`: pytest suite with `test_*.py` files.
- `configs/`: preset configs (`configs/react.json`, etc.).
- `docs/`: deeper guides (architecture, testing, upload).
- `output/`: generated skills and cache (git-ignored).
- Root docs: `README.md`, `QUICKSTART.md`, `STRUCTURE.md`.

## Build, Test, and Development Commands
- `pip install -e .`: editable install for local development.
- `skill-seekers scrape --config configs/react.json`: run the unified CLI against a preset.
- `python3 src/skill_seekers/cli/doc_scraper.py --config configs/react.json`: legacy direct script.
- `python -m pytest tests/ -v`: run full test suite.
- `python -m pytest tests/test_mcp_server.py -v`: run a focused test file.
- `./setup_mcp.sh`: configure MCP integration for Claude Code.

## Coding Style & Naming Conventions
- PEP 8 with 4-space indentation and 100-char line limit.
- Use double quotes for strings.
- Naming: `snake_case` for functions/vars, `PascalCase` for classes, `UPPER_SNAKE_CASE` for constants.
- Add docstrings and type hints for public or complex logic.

## Testing Guidelines
- Framework: pytest with `pytest-asyncio`.
- Test discovery: `tests/`, files `test_*.py`, functions `test_*`.
- Coverage: aim for >80%; critical paths should be fully covered.
- Add regression tests for bug fixes and update docs/tests when behavior changes.

## Commit & Pull Request Guidelines
- Commit messages: short, imperative summaries (e.g., "Add github scraper config").
- PRs must target the `development` branch (not `main`).
- Ensure tests pass locally and update docs/`CHANGELOG.md` when applicable.
- Include a clear description, testing notes, and screenshots for user-facing changes.

## Configuration & Security Tips
- Keep API tokens in env vars (e.g., `GITHUB_TOKEN`, `ANTHROPIC_API_KEY`).
- Avoid committing generated content under `output/`.
