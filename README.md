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
