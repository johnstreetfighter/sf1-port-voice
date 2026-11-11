# sf1-port-voice

The voice pack for [sf1-port](https://github.com/johnstreetfighter/sf1-port): the overhaul announcer's generated lines, stored in this separate pack (spec #216, ADR 0011).

- `manifest.json` lists each line (`<stem>.vox`) with its nibble count and CRC-32. The game checks the pack against it and refuses the whole pack on any mismatch.
- `<stem>.vox` is a line as 4-bit MSM5205 ADPCM at 4 kHz, two nibbles a byte, high nibble first.
- `archive/` holds every ElevenLabs voice-design preview and take, with its prompt, settings and seed, plus the ROM's FIGHT! and the listening sheet. The game ignores it.

The line list, prompts, the selected takes and the credit ledger are in the game repository's `tools/voice/`. The pipeline is `python tools/voice/pipeline.py` there, documented in `docs/reference/voice-pipeline.md`. The game looks for this folder beside the ROM set: `roms\sf` and `roms\sf1-port-voice`.

The archived build plan uses paths relative to this pack. Run the `sf-audio voice-pack` command from this directory when using that plan.

Push after each `build-pack`.
