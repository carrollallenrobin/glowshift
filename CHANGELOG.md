# Changelog

This changelog tracks notable Glowshift changes.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and versions follow [Semantic Versioning](https://semver.org/).

## [Unreleased]

## [1.1.0] - 2026-10-27

### Added

- Play in the browser at https://gabrimatic.github.io/glowshift/. The web build draws its glow by hand, since the browser renderer has no bloom.
- Gamepad support: left stick or D-pad to move, `A`, bumpers, or right trigger to dash, `Start` to pause.
- A synthesized synthwave music loop, built a slice at a time across the first frames so nothing stalls, including in the browser.
- Close calls: a hunter that brushes past without touching you scores 5 points times your combo.
- Arrows on the screen edge show where hunters are about to come in.
- The game over screen names what caught you and counts your close calls.
- "COMBO LOST" feedback when a combo of x3 or more runs out.
- Settings for sound (`M`), music (`N`), and reduced effects (`V`), saved between sessions. Reduced effects turns off flashes and color fringing and calms the screen shake.
- The game pauses on its own when its window loses focus, and hides the cursor while you play.
- The version number on the title screen.
- Release downloads come with `SHA256SUMS.txt`.

### Changed

- Your best score moves into the new settings file. The 1.0.0 best score carries over on first launch.
- Sound code lives in `scripts/synth.gd` and settings in `scripts/settings.gd`.
- Lighter chromatic aberration, so the HUD stays readable during big chains.

## [1.0.0] - 2026-10-27

### Added

- Arena gameplay: collect sparks, dodge hunters, dash through them to destroy them.
- Dash kills refill the dash, so kills chain.
- Combo multiplier up to x10 for quick spark pickups.
- Four hunter types: chaser, dart (telegraphs its path), splitter, and mini.
- Three power-ups: shield, slow time, and magnet.
- A new level every 20 seconds, with faster and more frequent hunters.
- Neon bloom, a spring grid that ripples with explosions, a nebula and parallax star background, and screen effects on hits.
- Sound effects synthesized at startup.
- Local best score, pause, and fullscreen toggle.
- Headless smoke test and CI.
- macOS, Windows, and Linux release builds.

[Unreleased]: https://github.com/gabrimatic/glowshift/compare/v1.1.0...HEAD
[1.1.0]: https://github.com/gabrimatic/glowshift/compare/v1.0.0...v1.1.0
[1.0.0]: https://github.com/gabrimatic/glowshift/releases/tag/v1.0.0
