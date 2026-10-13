# AudioControl for Home Assistant (Arcam FMJ, legacy library)

A copy of Home Assistant's built-in `arcam_fmj` integration from **HA 2026.9.0**, pinned to `arcam-fmj==1.8.3`.

## Why
`arcam-fmj` 3.0.0 (shipped in HA 2026.10.0) filters commands per model and doesn't recognise AudioControl receivers that report `Device-Model=X9/X7`. Power-on and volume control fail with `Command 8 not supported on X9/X7`. See [elupus/arcam_fmj#112](https://github.com/elupus/arcam_fmj/issues/112). This repo keeps the older library, which doesn't have that check.

No functional changes were made: only `manifest.json` (name, version, pin) and a pre-resolved `translations/en.json`.

## Install (HACS)
1. HACS → ⋮ → **Custom repositories** → add `https://github.com/pdapice/ha-audiocontrol` as type **Integration**.
2. Download **AudioControl (Arcam FMJ legacy lib)**, then restart Home Assistant.
3. Your existing config entry keeps working (same domain `arcam_fmj`, so this overrides the built-in one).

Once upstream fixes model detection, remove this custom integration and restart to return to the built-in one.

Original code © Home Assistant contributors / @elupus, Apache-2.0.
