# Repository Guidelines

## Project Structure and Module Organization

- `handyview/` contains the PyQt5 application code (main entry: `handyview/handyviewer.py`).
- `assets/` and `icons/` hold UI assets and image resources.
- `docs/` contains usage notes and how-to guides.
- Build scripts live at the repo root (for example `pyinstaller_install_win.sh`, `pyinstaller_install_mac.sh`, `create_dmg.sh`).

## Build, Test, and Development Commands

- Install dependencies: `pip install -r requirements.txt`.
- Run locally: `python -m handyview.handyviewer [image_path]`.
- Build on Windows: `./pyinstaller_install_win.sh` (outputs `dist/handyview/handyviewer.exe`).
- Build on macOS: `./pyinstaller_install_mac.sh` (outputs `dist/handyviewer.app`).
- Optional macOS DMG: `./create_dmg.sh` (outputs `dist/handyviewer.dmg`).

## Coding Style and Naming Conventions

- Python formatting is configured in `setup.cfg` with `yapf` (PEP8 based) and `isort`.
- Linting uses `flake8` with line length 120 and a few ignored warnings (see `setup.cfg`).
- Follow existing naming: `snake_case` for functions/variables, `UpperCamelCase` for Qt classes/widgets.

## Testing Guidelines

- No test suite is present in this repository. If you add tests, document the runner and expected usage in this file and update CI if needed.

## Commit and Pull Request Guidelines

- Recent commits use short, descriptive messages (for example `update readme`, `fix bug: ...`, `v1.0.2`). Keep messages concise and action-oriented.
- PRs should include a clear description, a list of user-visible changes, and screenshots or GIFs for UI updates. Link related issues when applicable.

## Security and Configuration Tips

- Prefer virtualenv on macOS builds to avoid large app size (see `how_to_build.md`).
- If adding new dependencies, update `requirements.txt` and note any platform-specific steps.