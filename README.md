# 3.3 V / 500 mA Li-Ion LDO Board

A two-layer KiCad design for a low-noise 3.3 V linear supply intended for a single-cell Li-Ion input.

## Design targets

| Parameter | Target |
|---|---:|
| Input voltage | 3.8–4.2 V DC |
| Output voltage | 3.3 V DC |
| Maximum output current | 500 mA |

These are design targets, not measured performance. The repository includes DRC/ERC screenshots, but no bench thermal, load, or transient test report. Thermal figures in the design notes are calculations, not measured results. Review the schematic, layout, component ratings, and manufacturing files before using the design.

## Project contents

- `LiIon_3V3_500mA_Regulator.kicad_pro`, `.kicad_sch`, and `.kicad_pcb` — KiCad project, schematic, and board
- `BOM/` — bill of materials
- `Checks/` — DRC/ERC screenshots
- `Datasheets/` — component datasheets
- `Design Notes/` — design notes PDF
- `Drill files/` — drill data and map
- `Gerber files/` — board manufacturing layers
- `Layout/` — layer exports and board renders
- `Pick and place files/` — placement data
- `3D_Models/`, `footprints/`, `symbols/`, and `schematic/` — local design libraries and supporting files
- `sym-lib-table` — KiCad symbol library table

## Tools

KiCad

## License

No license file is included. Do not assume reuse permissions; contact the author for permission.

**Author:** Abboju Nikhil
