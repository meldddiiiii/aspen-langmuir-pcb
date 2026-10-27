# Single Langmuir Probe PCB

KiCad redesign of the USC ASPEN single Langmuir probe sweep board, for the Fall 2026 ASPEN PCB competition.

![Board](board.png)

An OPA454 high-voltage op-amp amplifies a triangle-wave sweep to about ±35 V to bias the probe. Probe current is measured across a 100 Ω shunt by an INA149 high-common-mode difference amplifier, which outputs a ground-referenced signal safe for an NI USB-6211 DAQ.

## Key changes from the original

- Feedback resistors scaled to 2 kΩ / 5.1 kΩ (same 3.55 gain, 5 mA instead of 5 A)
- 100 pF feedback capacitor for bandwidth limiting and stability
- Correct OPA454 symbol, enable pull-up, and thermal pad tied to V−
- Decoupling and bulk capacitors on every supply
- INA149 current sense, powered by an on-board ±12 V zener supply
- Solid ground plane, V− thermal island, HV net class with 0.6 mm clearance

Full reasoning and math: [DESIGN_NOTES.md](DESIGN_NOTES.md)

## Files

- `LangmuirProbePCB_v2_opa454.kicad_pro` — open this in KiCad 10
- `.kicad_sch` / `.kicad_pcb` — schematic and board
- Custom symbol and footprint libraries are in this folder

Designed by Melodie Peng.
