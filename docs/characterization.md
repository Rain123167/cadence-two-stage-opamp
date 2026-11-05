# Characterization plan

Use the PDK's documented device symbols, model section, simulator options, and reliability limits. The supplied topology and dimensions are starting points only; first correct the device model mapping and establish a valid bias circuit.

## 1. DC operating point

- Run operating-point analysis at nominal supply and common-mode input.
- Record branch currents, node voltages, device region, and output headroom.
- Check that the output is not railed and that every transistor has the intended operating region.
- Sweep input common-mode and output voltage to find usable ranges.

## 2. Open-loop AC response

- Configure the amplifier in a stable test configuration appropriate to the chosen PDK and simulator.
- Measure low-frequency differential gain, unity-gain frequency (0 dB crossing), and phase at that crossing.
- Compute phase margin from the loop gain with the simulator's loop-stability probe or an equivalent validated setup. Do not infer phase margin from an improperly loaded open-loop transfer plot.
- Sweep compensation capacitor and load. Check gain-bandwidth and phase-margin tradeoffs.

## 3. Transient response

- Test small-signal settling and large-signal positive and negative steps at the intended load.
- Estimate slew rate from the linear portion of each output transition.
- Check settling, overshoot, clipping, and recovery for both polarities.

## 4. Corners and robustness

- Run available process, voltage, and temperature corners; include mismatch/Monte Carlo if licensed and supported.
- Recheck bias, stability, gain, bandwidth, slew rate, and power at each relevant corner.

## 5. Layout and extracted simulation

- Apply matching, symmetry, guard-ring, well, and routing practices required by the PDK.
- Run DRC and LVS with the foundry rule decks.
- Extract parasitics and repeat key DC, AC, and transient checks. Record schematic and extracted results separately.

## Résumé measurement record

Record supply, process corner, temperature, load, common-mode, analysis setup, and measured value for every headline metric. Include units and distinguish pre-layout from post-layout. Save screenshots or ADE outputs for interview discussion, but do not commit restricted PDK data.
