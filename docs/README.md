# Charisma Wheel AI: Documentation

## Overview

<!-- What the project does and the problem it solves. -->

Charisma Wheel AI is a Python project. It uses local AI models to generate written feedback that complements Charisma Wheel scores, which are already computed from users' online survey answers.

## Contents

- `README.md`: this index. Add a link here for each new doc.

## Getting started

<!-- Setup and first-run instructions. -->

## Architecture

<!-- Main components and how they fit together. -->

## Decisions

<!-- Notable design decisions and the reasons behind them. -->

## Git, data and models

Data files and model weights are not tracked by git. `.gitignore` excludes these patterns:

- Data: `data/`, `datasets/`, `*.csv`, `*.xlsx`, `*.parquet`, `*.sqlite`, `*.db`
- Model weights: `*.gguf`, `*.ggml`, `*.safetensors`, `*.bin`, `*.pt`, `*.pth`, `*.ckpt`, `*.onnx`, `models/`, `model_weights/`, `weights/`, `.cache/huggingface/`
- Environment files: `.env` and `.env.*` (only `.env.example` is tracked)

### Adding an exception

- Add a negation line to `.gitignore`, for example `!tests/fixtures/sample.csv`.
- A file cannot be re-included if one of its parent directories is ignored. In that case, change the directory rule from `dir/` to `dir/*` and add `!dir/` and the file's negation line.
- Only track small, synthetic, non-personal files this way.
- Confirm with the user before tracking any data file.

`CLAUDE.md` and `docs/` are tracked and must not be ignored. `CLAUDE.md` is the source of truth for project rules.

## Python environment

- Python version: 3.12.
- The virtual environment lives at `.venv` in the project folder.
- Manage the virtual environment and packages with uv exclusively: `uv add`, `uv remove`, `uv sync`, `uv run`. Never use pip, `python -m venv`, conda, or poetry.
- Do not edit dependencies by hand outside uv commands. Only the `pyproject.toml` metadata (name, version, requires-python, and similar) may be edited directly.
- Commit `pyproject.toml`, `uv.lock`, and `.python-version`. Never commit `.venv`.

## License

Proprietary, all rights reserved. See LICENSE.md.
