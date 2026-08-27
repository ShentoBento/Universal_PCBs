# Uni60 Solder PCB

<img src="images\Render_Front.png" width="800">

A solder PCB designed to fit most JST-dependent 60% Keyboards.

Firmware: https://github.com/ShentoBento/Universal_PCBs_Firmware/tree/main/Uni60/Solder

---

## Specs

<img src="images\Layout_Options.png" width="600">

- Solder
- MCU: STM32F072CBTx
- 5 JST SH connector positions
- 1.55mm socket diameters (compatible with millmax)
- 1 molex pico ezmate connector
- ISO support
- Split backspace
- Split right shift
- Split left shift
- Stepped/full caps
- 7u/6.25u bottom row
- 2.25/1.25u/2.75u split spacebar
- 3u/1u/3u split spacebar
- 10u spacebar
- VIA and Vial compatible (via the firmware linked above)

<img src="images\Connector_Positions.png" width="600">

---

## Requirements

- **KiCad 10** or newer. Earlier versions will not open these files.
- Nothing else. All symbols, footprints, and 3D models used by this project are
  included in this repo — no external libraries to install, no PCM packages,
  no library paths to configure.

---

## Opening the project

1. Clone or download this whole repo (not just the specific pcb folder).
2. Open `Uni60_Solder_KiCad/Uni60_Solder.KiCad_pro` in KiCad.

The library paths are stored relative to the project folder, so the repo works
from any location on any operating system. If KiCad reports missing symbols or
footprints, the most likely cause is that the `shentobento_kicad_library/`
folder was not cloned alongside.

---

## What's in this repo

### `Uni60_Solder_KiCad/`

The KiCad project. These are the files you edit.

| File | What it is |
|---|---|
| `Uni60_Solder.kicad_pro` | Project file — **open this one** |
| `Uni60_Solder.kicad_sch` | Schematic |
| `Uni60_Solder.kicad_pcb` | Board layout |
| `fp-lib-table`, `sym-lib-table` | Point KiCad at the bundled library |
| `fabrication-toolkit-options.json` | Settings for the JLCPCB fabrication plugin |

### `Uni60_Solder_KiCad/production/`

Ready-to-order manufacturing files, generated with the JLCPCB Fabrication Toolkit plugin.

| File | Upload it to |
|---|---|
| `Uni60_Solder.zip` | JLCPCB's gerber upload — this is the board itself |
| `bom.csv` | Assembly service (which parts) |
| `positions.csv` | Assembly service (where they go) |

If you modify the design, **regenerate these** with the JLCPCB Fabrication Toolkit plugin.

### `shentobento_kicad_library/`

Every symbol and footprint this project uses, in one place.

- `shentobento.kicad_sym` — all symbols
- `shentobento.pretty/` — all footprints
- `3dmodels/` — 3D models for the parts that need them

Symbols come with their footprints pre-assigned, so dragging a part into a
schematic gives you a working part with no footprint assignment step.

This folder is self-contained and can be copied into other keyboard projects.

### `files and images`

- `Uni60_PCB_Outline.dxf` — outline used for the pcb
- `JST Position.dxf` — the General-JST connector position

---

## Credits and licenses

Keyboard footprints and symbols are derived from
[marbastlib](https://github.com/ebastler/marbastlib) by ebastler, licensed under
CERN-OHL-P v2. See `shentobento_kicad_library/LICENSE-marbastlib.txt`.

Generic footprints (passives, SOT-23, LQFP-48, JST SH, test points) are copied
from the KiCad standard libraries.

Modifications made to third-party files are recorded in
`shentobento_kicad_library/NOTICE.md`.
