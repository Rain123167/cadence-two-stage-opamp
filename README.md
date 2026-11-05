# Two-Stage CMOS Operational Amplifier (Cadence Virtuoso)

A learning project scaffold for designing and characterizing a two-stage CMOS op-amp with Cadence Virtuoso and Spectre. It contains a transistor-level starting netlist, a unity-gain testbench, a measurement checklist, and a results template.

> **Status:** starter project. The design has not been run against a PDK, laid out, or verified. Replace the model include and device dimensions for your process, run the listed checks, and report only measured results in a résumé.

## Project goals

- Build a differential-input first stage and common-source second stage.
- Add Miller compensation and establish a valid DC operating point.
- Measure open-loop gain, unity-gain bandwidth, phase margin, slew rate, and power.
- Complete layout, DRC, LVS, and post-layout characterization when a PDK is available.

## Files

- `netlist/two_stage_opamp.scs` — parameterized transistor-level core. Device sizes and bias are initial guesses, not a verified design.
- `netlist/tb_unity_gain.scs` — unity-gain follower testbench template.
- `docs/characterization.md` — suggested Virtuoso ADE analyses and acceptance checks.
- `results/results-template.csv` — blank table for recording actual measurements.

## Requirements

- Cadence Virtuoso with Spectre, plus a foundry or educational PDK and its model files.
- An analog CMOS process with compatible NMOS/PMOS model names. Update the model section and instance parameters for the selected PDK.

No PDK, proprietary model, or fabricated measurement is included.

## Getting started

1. Create a Virtuoso library attached to your PDK's technology library.
2. Build the schematic from `netlist/two_stage_opamp.scs` or import/adapt the netlist in your local flow.
3. Replace the model include and model names with the PDK's documented values. Set `VDD`, bias current, device dimensions, and compensation capacitor for the process and load.
4. Run a DC operating-point analysis first. Check that all intended devices are in the required operating region and that the output has headroom.
5. Run the analyses in `docs/characterization.md`. Save plots, ADE state, and simulator logs locally; do not commit foundry-restricted material.
6. Iterate sizing and compensation. Record only reproducible results in `results/results-template.csv`.
7. Draw layout, run DRC/LVS, then repeat characterization with extracted parasitics.

## Résumé use

Use this only after completing and checking the work. Replace the bracketed values with measured data, for example:

> Designed and verified a two-stage CMOS op-amp in Cadence Virtuoso using [PDK/process]; tuned Miller compensation and device sizing to achieve [measured gain], [measured GBW], and [measured phase margin] at [load]; completed [actual DRC/LVS/post-layout status].

If only schematic simulation is complete, say so explicitly. Do not claim layout, DRC/LVS, or post-layout results unless you have completed them.
