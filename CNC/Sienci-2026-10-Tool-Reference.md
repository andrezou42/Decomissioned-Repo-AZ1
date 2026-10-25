# Sienci cutters from October 2026 order — Vectric reference

_Last checked: 2026-10-24_

Source: Sienci order #94613, placed October 13 and marked completed October 14, 2026, plus the linked Sienci product pages. The order has three individually listed cutters and one [AltMill Starter Set](https://sienci.com/product/altmill_starter_set/) containing five cutters. **Physical receipt, package markings, measured geometry, and ATC assignments remain unverified.** All dimensions below are manufacturer listings, not measurements of delivered tools.

The machine is an AltMill 4×8 joinery configuration with a 2.2 kW ATC spindle. The figures here describe cutters; they are **not** tested feeds, speeds, or Vectric presets.

| Order line | Cutter and Sienci source | Cutting diameter / form | Shank | Cutting length | Overall length | Flutes | Helix | Edge / coating | Listed applications |
|---|---|---|---|---|---|---:|---|---|---|
| Individual | [Tapered ball nose, 1/4 × 2 × R1/32 in](https://sienci.com/product/1-4_2_r1-32_tapered_ballnose/) | 1/4 in nominal; R1/32 in tip radius | 1/4 in | 2 in | 3-1/2 in | 2 | 30° | DLC | 3D contours and reliefs; Sienci lists wood, plastics, and metal |
| Individual | [Extra-hard compression upcut with chip breaker, 1/4 × 1 in](https://sienci.com/product/1-4_extra-hard-compression-upcut-with-chip-breaker/) | 1/4 in | 1/4 in | 1 in | 3 in | 3 | 30° | DLC | Hardwood, plywood, MDF; edge finishing and profile cuts |
| Individual | [High-helix upcut, 1/4 × 2 in](https://sienci.com/product/1-4_2_high_helix_upcut_end_mill/) | 1/4 in | 1/4 in | 2 in | 3-1/2 in | 2 | 45° | DLC | Hardwood and soft metals; profile/contour finishing |
| Starter Set | [Roughing upcut, 3/8 × 1-1/4 in](https://sienci.com/product/3-8_1-1-4_roughing-upcut-endmill/) | 3/8 in | 3/8 in | 1-1/4 in | 3-1/2 in | 3 | 30° | DLC; serrated rougher | Bulk removal in hardwood, plywood, MDF, and metals including aluminum; leave stock for a finishing pass |
| Starter Set | [Downcut, 1/8 × 3/4 in](https://sienci.com/product/1-8_3-3_downcut_end_mill/) | 1/8 in | 1/4 in | 3/4 in | 2 in | 1 | 30° | DLC | Plywood, veneer, pockets, inlays; clean top edge |
| Starter Set | [Downcut V-bit, 1/4 in, 90°](https://sienci.com/product/1-4_90_degree_vbit/) | 1/4 in maximum; 90° included angle | 1/4 in | Not specified | 2-1/2 in | 3 | Not specified | DLC | V-grooves, chamfers, lettering in wood, MDF, and plastics |
| Starter Set | [Downcut ball nose, 1/4 × 1-3/4 in](https://sienci.com/product/1-4_1-3-4_downcut_ballnose/) | 1/4 in ball nose | 1/4 in | 1-3/4 in | 3 in | **2 per title/table; 1 per summary** | 30° | DLC | Curved 3D surfaces in wood, foam, plastics, and plywood |
| Starter Set | [Surfacing bit, 1-1/2 in](https://sienci.com/product/1-1-2_surfacing_bit/) | 1-1/2 in | 1/4 in | Not specified | 2 in | 4 | Not specified | Brazed carbide; **not DLC** | Flattening spoilboards and slabs, including MDF |

## Vectric entries and vendor questions

- The tapered ball nose's **side taper angle** is absent from the listing. Its stated R1/32 in tip radius alone is insufficient to reproduce the complete tapered profile accurately in Vectric.
- The compression cutter's **upcut/downcut transition length** is not listed. That length matters when placing the compression zone through the workpiece thickness.
- The V-bit's **tip flat diameter** is not listed. Check the delivered cutter or ask Sienci before a precision V-carve entry.
- The downcut ball nose page conflicts on **flute count**: the title and measurement table say two; one summary line says one. Confirm before using flute count for chip-load calculations.
- The 1/8 in downcut has a **1/4 in shank** and is an end mill, not a drill. Its center-cutting/plunge capability is not specified. Do not treat it as the requested 1/8 in drilling tool solely because its cutting diameter is 1/8 in.
- The surfacing bit has a 1/4 in shank despite its 1-1/2 in cutting diameter. Confirm the actual cutter, spindle/toolholder limits, and safe operation before use.

Sienci's [published Vectric tool library page](https://sienci.com/tool-libraries/) links a `.vtdb` download. The previously downloaded copy was a generic LongMill MK2 library and did not identify these eight newer cutters. Ask Sienci for current **Vectric-compatible .vtdb entries** for the AltMill 2.2 kW ATC spindle. Useful per-tool/per-material fields would include RPM, feed, plunge, pass depth, stepover, ramping, chip load, and whether each tool is appropriate for MDF, acrylic, or aluminum. Do not assume every cutter is suitable for every material; the vendor applications above are the limits of the published claims reviewed here.

For the separate 0.8 in MDF circle job, the compression cutter's 1 in cutting length exceeds board thickness on paper; actual stickout, hold-down, cut strategy, and tool-specific feeds remain to be verified before a through cut. This reference does not authorize a machine run.
