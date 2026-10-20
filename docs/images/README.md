# Image plan

Use a curated set of images rather than uploading every PCB screenshot.

## Recommended filenames and README order

1. `p1_revB_fusion_hero_iso.png`
   - Hero image directly below the opening project description.
   - Best view: isometric Fusion integration with PCB + 1.69-inch display.
   - Caption: `Conceptual integration of the Rev B PCB and 1.69-inch IPS display in Autodesk Fusion. Final enclosure still in development.`

2. `p1_revB_fusion_top.png`
   - Mechanical-integration section.
   - Caption: `Top-view mechanical integration study: compact PCB, display, and accessible connectors.`

3. `p1_revB_fusion_opposite_iso.png`
   - Mechanical-integration section.
   - Caption: `Opposite isometric view used to review volume, access points, and component distribution.`

4. `p1_revB_layer2_gnd_plane.png`
   - Four-layer PCB section.
   - Caption: `L2 dedicated ground plane for current return and signal integrity.`

5. `p1_revB_layer3_power_distribution.png`
   - Four-layer PCB section.
   - Caption: `L3 used primarily for VDD_LOGIC / secondary power distribution.`

## Optional EasyEDA view

The current optional EasyEDA 3D screenshot is intentionally **not included in this public milestone** because it contains visible product-brand text that is being withheld for now. A neutral PCB-only render can be added later if needed.

## What not to prioritize

- Do not upload all four routing-layer screenshots to the README.
- L2 and L3 tell the four-layer architecture story better than noisy top/bottom screenshots.
- Avoid near-duplicate Fusion views.
- One EasyEDA 3D view is enough if Fusion already communicates the product integration clearly.
- Do not use generic screenshot filenames such as `Captura de pantalla...`.

## Image truthfulness

Every Fusion image must be described as an integration study until the enclosure is physically printed and assembled.

Every EasyEDA 3D image is a CAD/render view, not evidence of fabricated hardware.
