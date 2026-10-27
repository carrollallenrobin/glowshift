# Glowshift

Godot 4.7.2 arena game, all procedural: no image, texture, or audio assets in the game. Everything is drawn in `main.gd` with `_draw()`, two shaders in `shaders/`, and sounds synthesized in `_build_sounds()`.

## Commands

- Run: `godot --path .`
- Test (must print `SMOKE OK`, exit 0, no `SCRIPT ERROR`): `godot --headless --path . --import && godot --headless --fixed-fps 60 --path . -s res://tests/smoke_test.gd`
- Export: `godot --headless --path . --export-release <macOS|Windows|Linux> <path>` (templates in `~/Library/Application Support/Godot/export_templates/4.7.2.stable`).
- Release: update `CHANGELOG.md`, `config/version` in `project.godot`, and the versions in `export_presets.cfg`, then push a `vX.Y.Z` tag; `.github/workflows/release.yml` builds and publishes.

## Rules

- Inner classes must not shadow Godot native class names (`Popup` broke the parse once).
- Polygons passed to `draw_colored_polygon` must not self-intersect.
- Glow comes from HDR colors (channels above 1.0) with `rendering/viewport/hdr_2d`; keep HUD text below the glow threshold so it stays readable.
- `game.persist = false` in tests so they never overwrite the player's best score.
- `build/` and `.godot/` are generated; `*.import` and `*.uid` files are committed.
