# Candela Bench

Single-file web app that builds computed photometry and exports **IES LM-63-2002** files.

- **Start from** a fixture type, a spec sheet (paste text), or an existing IES file.
- **Models:** beam-angle profiles (Gaussian, cosine power, batwing, tilt, cut-off), LED optics (reflector, TIR, bare LED with étendue limit and recess shielding), and decorative lamp shades (revolved profile, translucent walls, tube or point source, downlight module).
- **Checks:** polar curve, 3D fixture and light solid, illuminance map, throw and glare tables, LM-63 validator, spec check.
- **Room calculation:** DIALux-style 3D room, work-plane lux grid, uniformity, W/m², direct light plus average interreflection.
- **Export:** IES text, OBJ of the fixture and light solid.

Open `index.html` in a browser, no build step.

## Limits
- Output is mathematically generated, not LM-79 measured. Use for concept and feasibility work.
- Room calculation is not full radiosity and has no obstructions.
- Outside Claude, the Save buttons are hidden (use Copy text) and reading spec screenshots is unavailable; pasted spec text still works.

`examples/D1_Pendant_Bespoke.ies` was generated from a pendant spec sheet (1250 lm, 25 W, 3000 K, Ø300 × 565 mm).

## Lamp mode: ray-traced shade

The decorative-lamp model now traces rays inside the shade (diffuse and clear transmission, diffuse and mirror reflection, perforation, ribs, inside finishes) and reports the shade LOR with an uncertainty range. A material library sets transmittance and reflectance, and two calibration buttons match the model to a measured luminaire lumen value or a lux reading at one point.
