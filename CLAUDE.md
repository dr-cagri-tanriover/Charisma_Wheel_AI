# Charisma Wheel AI

<!-- One or two sentences: what this project is and who it is for. -->

## Docs

Project documentation lives in `docs/`. Start with `docs/README.md`.

## Commands

<!-- Build, run, test, and lint commands go here once the project has them. -->

## Conventions

<!-- Code style, naming, directory layout, and anything Claude should know when working here. -->

## Git and data rules

### Git identity and operations

- Use only the global git `user.name` and `user.email` already configured on this machine. Never set or use any other name or email (no local config overrides, no `-c user.name=...` or `-c user.email=...`, no `--author` flags, no `Co-Authored-By` trailers) without confirming with the user first.
- If the global identity is missing, stop and ask the user.
- Do not commit, add remotes, or push unless the user asks.

### Project context

This is a Python project that generates feedback with local AI models to complement Charisma Wheel scores. The scores are computed from users' online survey answers.

### Data and model files are never committed

These rules mirror `.gitignore`. Survey data and local model files must stay out of git:

- Data: `data/`, `datasets/`, `*.csv`, `*.xlsx`, `*.parquet`, `*.sqlite`, `*.db`
- Model weights: `*.gguf`, `*.ggml`, `*.safetensors`, `*.bin`, `*.pt`, `*.pth`, `*.ckpt`, `*.onnx`, `models/`, `model_weights/`, `weights/`, `.cache/huggingface/`
- Environment files: `.env` and `.env.*` (only `.env.example` is tracked)

### Adding an exception

- Add a negation line to `.gitignore`, for example `!tests/fixtures/sample.csv`.
- A file cannot be re-included if one of its parent directories is ignored. In that case, change the directory rule from `dir/` to `dir/*` and add `!dir/` and the file's negation line.
- Only track small, synthetic, non-personal files this way.
- Confirm with the user before tracking any data file.

### Files that must stay tracked

`CLAUDE.md` and `docs/` are tracked and must not be ignored. `CLAUDE.md` is the source of truth for project rules.

## Python environment

- Python version: 3.12.
- The virtual environment lives at `.venv` in the project folder.
- Manage the virtual environment and packages with uv exclusively: `uv add`, `uv remove`, `uv sync`, `uv run`. Never use pip, `python -m venv`, conda, or poetry.
- Do not edit dependencies by hand outside uv commands. Only the `pyproject.toml` metadata (name, version, requires-python, and similar) may be edited directly.
- Commit `pyproject.toml`, `uv.lock`, and `.python-version`. Never commit `.venv`.

## License

Proprietary, all rights reserved. See LICENSE.md.
