# ESProbeScope3300

A KiCad PCB design created for ETEC 3300. The board is built around the **ESP32-S2FN4R2** and combines USB-C connectivity, 2.4 GHz Wi-Fi (via an on-board chip antenna), a battery charging circuit, an LDO power rail, an audio amplifier, an LCD interface, RGB status LEDs, and a multi-button probe input — all in a single compact design.

---

## Project structure

```
kicad-probe-scope/
├── ESProbeScope3300.kicad_pcb   # PCB layout
├── ESProbeScope3300.kicad_sch   # Schematic
├── ESProbeScope3300.kicad_pro   # Project file
├── sym-lib-table                # Project-scoped symbol library table
│
├── libs/
│   ├── PartsLibrary3300.kicad_sym       # Symbol library
│   └── PartsLibrary3300.pretty/         # Footprint library
│       └── *.kicad_mod
│
├── fab/
│   ├── gerbers/                 # Copper, mask, silkscreen, edge cuts
│   ├── ESProbeScope3300-PTH.drl
│   ├── ESProbeScope3300-NPTH.drl
│   └── ESProbeScope3300-job.gbrjob
│
└── doc/
    ├── schematic.pdf
    └── bom.xlsx
```

---

## Schematic

A PDF export of the schematic is available at [doc/schematic.pdf](doc/schematic.pdf) for viewing without KiCad.

---

## Key components

| Ref | Part | Function |
|-----|------|----------|
| U1 | ESP32-S2FN4R2 | Main MCU with integrated 2.4 GHz Wi-Fi |
| ANT1 | Johanson 2450AT42B100E | 2.4 GHz chip antenna |
| J1 | GCT USB4110-GF-A | USB 2.0 Type-C connector |
| IC3 | MPS MP2664GG | Li-ion battery charger |
| IC1, IC2 | XC8110AA01MR-G | LDO voltage regulators |
| VR1 | ON Semi NCP114ASN330T1G | 3.3 V LDO |
| IC4 | PAM8301 | Class-D audio amplifier |
| LCD1 | Molex 527450897 | LCD flex connector |
| XTAL1 | EXS00A-CS14526 | Crystal oscillator |
| LED1, LED2 | B38G3RGB-10D0003H2U1930 | RGB status LEDs |
| S1–S8 | Alps SKRPABE010 | Tactile pushbuttons |
| SW1 | C&K JS102011SAQN | Slide power switch |
| X3 | — | Probe input header |

---

## Footprint and symbol libraries

All symbols and footprints are in `libs/PartsLibrary3300.kicad_sym` and `libs/PartsLibrary3300.pretty/`. Both are linked via `${KIPRJMOD}` in `sym-lib-table` and the project footprint library table, so they resolve automatically when the project is opened in KiCad regardless of where it is cloned.

Footprints originate from the KiCad standard library, SnapEDA, and manufacturer-published CAD data (Johanson Technology, Walsin, Molex, GCT). Attribution is noted in the footprint description fields within the library files themselves.

---

## License

MIT — see [LICENSE](LICENSE).

---

## Acknowledgements

- [KiCad EDA](https://www.kicad.org/) and the KiCad Libraries contributors
- [SnapEDA](https://www.snapeda.com) for component models
- Johanson Technology, Walsin Technology, Molex, GCT, and other component manufacturers for publishing CAD data