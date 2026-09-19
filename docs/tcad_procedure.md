# TCAD Simulation Procedure — Silvaco ATLAS

## Step 1: Device Structure (DevEdit)
- Open DevEdit, create new structure
- Define silicon region: 300µm × 2µm
- P-region: left half, doping = 5e18 cm-3 (Boron acceptors)
- N-region: right half, doping = 1e16 cm-3 (Phosphorus donors)
- Anode contact: top-left (nickel)
- Cathode contact: top-right (nickel)
- Mesh: fine near junction, coarser away from it

## Step 2: ATLAS Simulation Deck
```
# Material and model definitions
material silicon
models srh auger bgn
contact name=anode
contact name=cathode

# Bias sweep — forward
solve v_anode = 0 vstep = 0.05 vfinal = 2.0 electrode = anode

# Bias sweep — reverse
solve v_anode = 0 vstep = -0.1 vfinal = -5.0 electrode = anode
```

## Step 3: Extract I-V
- Plot I(anode) vs V(anode)
- Compare with Shockley equation

## Key Observations
- Built-in potential Vbi ≈ 0.83V (from doping asymmetry)
- Turn-on voltage ≈ 0.65–0.7V (below Vbi due to minority carrier injection)
- Reverse leakage ≈ 10⁻¹² A (generation-recombination dominated)
