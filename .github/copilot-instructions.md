# Copilot / AI Agent Instructions for python-tutorials

Purpose
- Short: help an AI coding agent be productive editing and extending this repository.

Repository overview (big picture)
- This repo is a small collection of teaching materials: see [README.md](README.md) and the notebooks under [NumPy/](NumPy/IntroNumPy.ipynb).
- No services, servers, or packages are defined — primary artifacts are Jupyter notebooks demonstrating NumPy usage.

Immediate goals for agents
- Make minimal, focused edits to notebooks in `NumPy/` (fix typos, clarify prose, add short examples).
- When adding runnable code, prefer adding a new `.py` module and import it from the notebook (keeps notebooks smaller and repeatable).

Developer workflows & commands
- Open the repository in VS Code and use the Jupyter extension to edit/run notebooks interactively.
- Typical local setup (no requirements file present):
  - `python -m pip install --upgrade pip`
  - `python -m pip install jupyter numpy`
  - `python -m jupyter lab` (or `jupyter notebook`)
- To execute a notebook non-interactively (useful for CI or verifying changes):
  - `jupyter nbconvert --to notebook --execute NumPy/IntroNumPy.ipynb --inplace`

Conventions & patterns specific to this repo
- Notebooks live in `NumPy/` and are user-facing teaching artifacts — prefer minimal churn to cell outputs unless updating examples.
- If a change adds reusable code, add it as `src/` or `tools/` (create these directories when needed) and import from notebooks.
- Avoid large refactors inside `.ipynb` files; prefer adding companion `.py` helpers and demonstrating usage via `%run` or `import` from a notebook cell.

Testing, linting, CI
- There is no existing test or CI configuration. If you add tests, follow common Python patterns (pytest) and add a `requirements.txt` or `pyproject.toml`.

Examples from this codebase
- Primary teaching file: [NumPy/IntroNumPy.ipynb](NumPy/IntroNumPy.ipynb)
- High-level docs: [README.md](README.md)

Editing guidelines for AI agents (actionable)
- Keep edits atomic: one concept or fix per PR.
- When updating a notebook, run `jupyter nbconvert --to notebook --execute --inplace` and commit the executed notebook so outputs stay consistent.
- When adding dependencies, add a short `requirements.txt` and include an install step in the PR description.

When unsure
- Ask the maintainer to confirm whether notebook outputs should be preserved or cleared for a given change.

Feedback
- If anything here is unclear or you'd like different detail (commands, CI examples, or a conventions section), tell me which area to expand.
