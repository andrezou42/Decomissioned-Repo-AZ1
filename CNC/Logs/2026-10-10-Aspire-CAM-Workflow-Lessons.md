# CNC workflow notes — 2026-10-10

Notes from recent AltMill 4×8 / Aspire work. Treat the feeds below as a starting point for this shallow MDF job, not a universal cutter recipe.

## Start with the stock and the datum

- Write down the stock size, measured thickness, units, and axes before drawing: X is width, Y is length, XY zero is the lower-left corner, and Z zero is the material surface.
- Recheck the physical thickness for every new board. Do not reuse 0.50 in when the board measures 0.52 in, or reuse an old project thickness without confirming it.
- For salvage work, identify the two good adjacent edges and keep them as the datum. Translate the requested finished size into exact remaining-edge cuts before opening Aspire. A “12 × 12” salvage panel needs 12 in on both axes; do not accidentally carry forward a 10 in X dimension from another layout.
- Confirm the total geometry with arithmetic before export. Seven strips require six grooves. The corrected 14 in layout has no side margins: 7 × 1.88 + 6 × 0.14 = 14.00 in, leaving seven 1.88 in lands and six 0.14 in grooves.

## Keep geometry, toolpaths, and exports distinct

- A DXF contains vectors only. Importing it does not create Aspire toolpaths. In Aspire, select the intended layer vectors, create and calculate each operation, inspect the preview, save the native .crv3d project, and export with the correct machine and post-processor.
- Keep separate layers for grooves, shallow inlays/recesses, and reference geometry. Use the layer context menu’s **Select Layer Vectors** command to select only the operation’s vectors. Never include the reference perimeter unless the job calls for a perimeter cut.
- For paneling tasks, decide whether dimensions describe part edges or toolpath centerlines. Use cutter radius compensation intentionally. For a through-cut centerline, use **On Vectors** when the line itself is the intended centerline; offset the line by half the cutter diameter when the part edge must land at a measured coordinate.
- After calculation, check that the preview contains only the intended operations and that every path has the right cutter. Remove any default tool left in the operation if Aspire reports it generated an empty toolpath.
- Before emailing a job, verify the native project and the actual machine file exist, and inspect the machine file header for the intended ATC tool number, post-processor, units, spindle, feed, and cut depths.

## Tool identity and shallow MDF settings

- The Aspire library lists SpeTool W03002 as a single-flute upcut O-flute: 0.125 in cutting diameter, 0.25 in shank, and 0.75 in cutting length. The inventory associates the 1/8 in O-flute with T2, but the exact physical SKU remains unverified; check the cutter marking and carousel slot before running.
- For the 14 × 14 in, 0.80 in MDF panel created on 2026-10-10, the job uses a local Aspire tool record assigned to T2 with 0.125 in diameter, one flute, 0.10 in pass depth, 0.05 in stepover, 18,000 RPM, 45 IPM feed, and 20 IPM plunge. This gives a nominal 0.0025 in chip load. The groove pocket is 0.20 in deep in two passes; the 0.08 in aluminum-strip recess is one pass.
- SpeTool’s W03002 page recommends 18,000 RPM. Sienci’s AltMill feeds/speeds reference should guide rate selection, then listen for chatter, inspect chips and finish, and adjust for actual stock and workholding. These values are a measured starting point for a narrow, shallow MDF pocket, not for full-depth profiling.
- Keep tool number and geometry tied to the physical ATC slot. Aspire may offer the correct geometry in its library while the project still needs a local feed/speed/tool-number record. Document the actual cutter identity in the local tool Notes.
- The surface-pocket job ran acceptably with the operator raising work speed to 200%. Record that as a successful observation for shallow surface cuts only; do not transfer it automatically to through-cuts.

## Cut quality, workholding, and sequencing

- A groove or fuzzy edge that appears on only one side can reflect feed direction, grain/fiber behavior, cutter condition, runout, or workholding; compare a short test cut before changing several parameters at once.
- A cutter that sat unused should be inspected for resin/dust buildup, edge damage, and dullness. Clean it only with a suitable cutter cleaner and follow its manufacturer’s instructions; a dirty or dull edge can worsen MDF fuzz and chip-out.
- Secure the sheet and each panel before releasing the surrounding stock. Tape and CA can work for light routing, but verify full contact and add mechanical hold-down or tabs when cuts can free a corner or allow the part to lift.
- With staged tools, make sure score and roughing paths use the intended tool numbers and depths. A shallow scoring pass can protect a visible edge, but extra tool changes add alignment and setup risk.

## Sources

- [SpeTool W03002 O-flute specifications and speed guidance](https://spetools.com/products/spetool-w03002-o-flute-up-cut-router-bit-1-8-dia-1-4-shank)
- [Sienci AltMill feeds and speeds reference](https://resources.sienci.com/view/cnc-feeds-speeds/)
