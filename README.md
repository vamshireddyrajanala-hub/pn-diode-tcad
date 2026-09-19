# Planar PN Junction Diode — TCAD Device Simulation

First-principles device simulation of a planar PN junction diode using Silvaco ATLAS/DevEdit.

## Simulation Tool
- **Silvaco ATLAS** — numerical device simulator
- **DevEdit** — device structure editor

## Device Specifications
| Parameter | Value |
|---|---|
| Structure | Planar silicon PN junction |
| Width | ~300 µm |
| Depth | ~2 µm |
| P-type doping | 5×10¹⁸ cm⁻³ |
| N-type doping | 1×10¹⁶ cm⁻³ |
| Contacts | Nickel |

## Simulation Workflow
1. Define device geometry and mesh in DevEdit
2. Assign doping profiles (P and N regions)
3. Apply material properties (silicon, nickel contacts)
4. Sweep anode bias (0V → 2V forward, 0V → -5V reverse)
5. Solve carrier transport equations (Poisson + drift-diffusion)
6. Extract I-V characteristic

## Results
- Flat leakage below ~0.6V (reverse bias / subthreshold)
- Exponential turn-on at ~0.65–0.7V (forward bias)
- ~6µA at 1V forward bias
- Matched theoretical Shockley diode equation within 5%

## Physics
The simulation validates the ideal diode equation:
```
I = I₀(e^(qV/nkT) - 1)
```
where I₀ is reverse saturation current, n ≈ 1 (ideal), kT/q ≈ 26mV at 300K.

## Portfolio
[vamshireddyrajanala-hub.github.io/portfolio](https://vamshireddyrajanala-hub.github.io/portfolio/)
