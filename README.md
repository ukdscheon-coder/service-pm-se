# DxI 9000 PM Guide (PM-A / PM-B)

Live at https://service-pm-se.vercel.app since 05/11/2026.

- `index.html`: the guide. Based on the final DxI 9000 PM Guide deployed to `pm-navigator-global` on 26/10/2026
  (source copied byte-for-byte, SHA-1 2f139e2d…), plus: the PM order (6 phases) on the start screen and on every
  step, Back, required Work Order and Total Test Numbers, a completion check before a PM can be confirmed,
  status Verified / Recheck required / In progress / Not yet checked, dates as DD/MM/YYYY, and the RSM step fix.
- `service-worker.js`: offline cache for the guide; removes the old Service PM V2.x caches on installed iPhones.
- `legacy/service-pm-v2.24/`: the previous Service PM app (records, schedule). Kept in the repository, not deployed
  (`.vercelignore`). The same version is on branch `backup/service-pm-v2.24`.
- Records stay on the device (browser storage). Old Service PM records already on a phone are not deleted.
- `instruments.js`: 44 DxI 9000 instruments (18 sites) imported 05/11/2026 from Contact_emails_05_Nov.xlsx — IN, SN,
  SW, APF, install date, PM history (6M = PM-A, 12M = PM-B), MODs and service work. Keyed by IN. The sign-in line at
  the top of the spreadsheet is deliberately not imported.

## Change record
| Date | Change |
|---|---|
| 06/11/2026 | Step order v2 (DS): RSM work grouped while the console is paused, before power off. Step 2 is now *Bypass interlock, pause and unload reagent packs* (remove the **RSM reagent storage door**, then unload). Step 3 checks the cooling fans with the door already removed. New steps 4–6: RSM nests and storage; RSM top guide shaft and red bushing (D0518); RSM gripper check (Z-axis gap at the top guide red bushing → suspect bent bottom Z-axis torque tube; X-axis belt and torque tube barrier alignment). Step 7 *Power off and disconnect* no longer pauses again. The later separate *Reagent Storage (RSM)* step is removed. PM-A 31 → 33 steps, PM-B 32 → 34. PMs started before this change keep the v1 list (`pmWorkflowV1`). |
| 06/11/2026 | Step order v3 (DS): rear-cover sequence after the Fluidics Drawer — **Sample Wheel** (open the rear cover; clean plate and jumper pins with DI water; remove water from the sample storage; check the drain tube) → **Incubate Wheel** (plate and jumper pins, DI water) → **Wash Wheel & Pumps** (replace aspirate probes; inspect mixer, spindle and eject plate detent pin; clean; PM-B tubing and 12-month lubrication unchanged) → **Pick and Place** → **Reagent Shuttles** (reaction build carriers, DI water) → new **Fluid path** inspection. PM-A 33 → 34 steps, PM-B 34 → 35. PMs started on v1 or v2 keep their own list. |
| 06/11/2026 | Names and part number (DS): *RSM top guide shaft* → **Reagent Storage Upper Guide Shaft**; *red bushing (D0518)* → **Guide Shaft Bushing (5018A)**, in the step title, step text and detailed instructions (v2 and v3 lists). |
