# Contributing

Thanks for helping with Glowshift. Bug reports, balance feedback, and pull requests are all useful.

## Setup

Requirements: **Godot 4.7.2** (standard build, not .NET).

```bash
git clone https://github.com/gabrimatic/glowshift.git
cd glowshift
godot --path .
```

## Before you open a pull request

Run the smoke test and make sure it prints `SMOKE OK` with no `SCRIPT ERROR` lines:

```bash
godot --headless --path . --import
godot --headless --fixed-fps 60 --path . -s res://tests/smoke_test.gd
```

If you change gameplay, play a few full runs too. The test checks that systems work, not that the game feels right.

## Code style

- Use static types everywhere (`var speed := 380.0`, `func _kill(h: Hunter, by_dash: bool) -> void`).
- Indent with tabs, as the Godot editor does.
- Keep tuning values in the constants at the top of `main.gd`.
- Do not name inner classes after Godot's built-in classes (`Popup`, `Timer`, `Label`, and so on); GDScript rejects them.
- Keep the game asset-free: draw with code and shaders, and synthesize sounds. A change that needs a binary asset should say why in the pull request.

## Pull requests

- Keep each pull request to one change.
- Describe what changed and how you tested it. Add a screenshot or short clip for visual changes.
- Add a line under `## [Unreleased]` in `CHANGELOG.md` for anything a player would notice.

## Reporting bugs

Open an issue with your OS, the Glowshift version (or commit), what you did, what you expected, and what happened.

## Releases

Maintainers release by updating `CHANGELOG.md`, bumping `config/version` in `project.godot` and the versions in `export_presets.cfg`, then pushing a `vX.Y.Z` tag. The release workflow builds and publishes everything else.
