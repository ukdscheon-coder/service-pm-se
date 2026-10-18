V2.6 Approved UI rebuild
- Rebuilt to match the approved 8-screen mobile UI/UX.
- iPhone SE+ responsive PWA and Windows browser/PWA.
- Product Master restored: DxI 9000, DxI 800, DxI 600, Access 2, DxC 500 AU, DxC 500i, DxC 700 AU, AU 480, AU 680, AU 5800, DxA 5000.
- Existing V1 assets migrate from beckman-pm-cmms-v2/v1 localStorage and remain linked to their model.
- IN/SN/DTS and Account search.
- PM checklist, history, schedule/intelligence UI, service records, camera/files, Share/Email.
- No private cloud sync yet; deploy only after user approval.

V2.11: More Information now always shows the source section '3.1 Performing Preventive Maintenance (PM)' and the exact Figure number/title where the supplied PM manual contains a numbered figure.

V2.12: Figure numbers are now explicitly visible both on the active PM step and inside full-screen More Information as '3.1 Performing Preventive Maintenance (PM) → Figure XX'.

V2.13 FIX
- Root cause found: service-worker cache name was still beckman-service-pm-v26, so an installed PWA could continue serving the older cached app.js/app.css even after V2.11/V2.12 files were replaced.
- Cache version changed to v213, old caches are deleted on activation, and HTML/JS/CSS use network-first update behavior.
- More Information now ALWAYS includes the full PM Manual Figure Index (Figure 45–55), while the current PM step also shows its specific figure reference where applicable.

V2.14: More Information now shows only Figure references relevant to the CURRENT PM step. The global Figure 45–55 index was removed. Reagent Storage (RSM) links only to Figure 50 — Pipetting Nest Cover and Debris (example).
