# PM Suite inventory

Checked 05/11/2026 against the live Vercel team `daeseong-cheons-projects`. This is milestone 1 of merging
DxI 9000 PM Guide, Service PM and PM Navigator Global into one codebase (this repository is the home repo).

## What is actually deployed

| Module | Vercel project | Source | Latest production | Protection | Finding |
|---|---|---|---|---|---|
| Service PM | `service-pm-se` | this repo, `main` | 23/10/2026, V2.23 | Vercel Authentication on | Live copy |
| Service PM (duplicate) | `service-pm-se-eo65` | this repo, `main` | 23/10/2026, same commit, built the same minute | Vercel Authentication on | Identical build of the same commit. Not a second version. |
| DxI 9000 PM Guide | `dxi9000-pm-guide` | none | never deployed | — | Empty project |
| PM Navigator Global | `pm-navigator-global` | Vercel CLI upload only (`index.html`, `vercel.json`) | 26/10/2026 | **Public** (no protection) | The page title is "DxI 9000 PM Guide": this is the live DxI 9000 PM Guide. It has no country or instrument classification. |

So there are two apps, not three:

1. **Service PM** (this repo): multi-model service PM tool (11 models in the product master), instrument records, PM checklist, history.
2. **DxI 9000 PM Guide** (deployed as `pm-navigator-global`): a single-file PM-A / PM-B step guide for DxI 9000.

## Procedure version and source

Both apps carry the same DxI 9000 PM step text, citing "3.1 Performing Preventive Maintenance (PM)" and
Figures 45–55 of the supplied PM manual. The text is duplicated in two places, so a correction made in one
does not reach the other.

## Defect found in both apps (fixed here in V2.24)

The Reagent Storage step is titled `Reagent Storage (RSM)`, but the detail and manual-reference lookups used the
key `Reagent Storage Module (RSM)`. The step therefore showed only its short summary and never the five detailed
instructions or Figure 50. Fixed in this repo; the same defect exists in the `pm-navigator-global` copy.

## Data held in the app

`data.js` seeds instrument records with customer site contacts (names and e-mail addresses) and instrument
serial numbers. Both Service PM deployments are behind Vercel Authentication. Check this is acceptable under
your employer's data rules before the merged app is made public.

## Proposed structure

- One codebase, one Vercel project (`service-pm-se`); remove the `service-pm-se-eo65` duplicate when convenient.
- Shared procedure data: each step carries `model`, `procedure_version`, `source` (manual section and figure) and
  `valid_from`. Service PM and the DxI 9000 guide read the same data, so a fix lands once.
- Sections: `/service-pm` (records and scheduling) and `/dxi9000-guide` (step guide). A navigator by country and
  instrument is built only if that requirement is confirmed.
- Point `pm-navigator-global.vercel.app` at the merged guide section once it exists.
