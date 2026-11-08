# Project Status — 2026-11-08 (GitHub release preparation)

## 2026-11-08 · GitHub release preparation
- The PBIX saved on 2026-11-08 contained a newer report layout and two additional registered landing-page images. Opened that PBIX in Power BI Desktop and saved it over the existing `The Investment Challenge.pbip`, keeping the same project entry point and folders. The PBIX remains the final binary deliverable.
- Exported the current report twice from Desktop: once with Brand Overview active and once with the Home overlay active. Replaced the two analytical screenshots in `submission/` and added `Screenshot_Home.jpg`. Reviewed all three rendered images.
- Added a public-facing README and narrowed `.gitignore` to keep Power BI local cache and internal reference material out of the GitHub package.

### Tests actually executed (2026-11-08)
| Test | Result |
|---|---|
| Latest PBIX opened in Power BI Desktop with the redesigned Home visible and no load error | Pass |
| PBIP saved from that PBIX, then reopened in Desktop; Home rendered and no load error appeared | Pass |
| PDF export with Brand Overview active contained 2 pages; both analytical screenshots rendered and were visually reviewed | Pass |
| PDF export with Home active produced a Home screenshot; it was visually reviewed | Pass |
| `.pbip` entry point and `.Report` / `.SemanticModel` files received 2026-11-08 save timestamps; only one `.pbip` exists in the project folder | Pass (structural check) |

## 2026-11-05 hero card alignment
- Moved the existing contextual text beside the large value in all six cards shown in the Brand Overview and The Decision screenshots: three in `UX Hero Review` and three in `UX Hero Decision`. Retained all existing wording, values, formulas and colors. `UX Operational Impact` is the separate table on The Decision page and was not changed.
- Saved `The Investment Challenge.pbip` with the Home bookmark active and overwrote the existing `The Investment Challenge - Goodnight Inn.pbix` through Desktop Save As.

## Tests executed for hero card alignment (2026-11-05)
| Test | Result |
|---|---|
| PBIP reopened in Power BI Desktop after the TMDL edit without a load error | Pass |
| Brand Overview: all three hero cards rendered with contextual text beside the values | Pass (visual inspection in Desktop) |
| The Decision: all three hero cards rendered with contextual text beside the values | Pass (visual inspection in Desktop) |
| Home bookmark restored; PBIP saved with Home displayed | Pass |
| Existing PBIX overwritten and displayed the Home; file timestamp updated to 2026-11-05 16:12 local | Pass |

## 2026-11-05 contextual tooltip update
- Added seven hidden report tooltip pages: Profit bridge, Channel economics, Operating pulse, Regional margin, Profit path, Cash flow and Portfolio stress test. Bound them to nine native charts/tables across the two analytical pages. The existing Hotel and Project report tooltips remain bound to their charts/tables; the two Deneb visuals retain their in-chart tooltip definitions.
- Added seven UX-only DAX measures in `Board Metrics.tmdl`. They reuse the existing actuals, channel, portfolio and scenario measures. No project choice, financial-engine measure or source data was changed.
- Saved the existing PBIP with the Home active and overwrote `The Investment Challenge - Goodnight Inn.pbix` in Desktop.

## Tests executed for contextual tooltips (2026-11-05)
| Test | Result |
|---|---|
| PBIP opened in Power BI Desktop after the final TMDL edit without a load error | Pass |
| All seven new tooltip pages opened and rendered their cards in Desktop before the no-year refinement; Profit path and Cash flow no-year prompts rendered after the refinement | Pass |
| The Decision page and Home rendered in Desktop; the PBIX displayed the Home after Save As | Pass |
| PBIR JSON references resolve to existing tooltip pages; exactly 2 pages are visible and 9 tooltip pages are marked hidden | Pass (structural check) |
| Existing PBIX overwritten in Desktop; file timestamp updated on 2026-11-05 at 15:23 local | Pass |

The hover interaction on each bound chart point was not verified in Desktop. The current computer-use API can click and drag but does not provide a pointer-hover action; clicking and dragging selects or moves report objects in edit mode. The tooltip-page render and PBIR bindings were checked separately.

## 2026-11-05 layout update
- Built three editable Figma frames for the Home overlay and the two analytical pages: https://www.figma.com/design/lIrkyaZ2xOwvvA6lQuJFaB . The Power BI report still has exactly two visible pages.
- Used `Resort de Luxo ao Entardecer home.png` as an unmodified Home background. A 92%-opaque navy reading panel protects legibility; the official P&K logo keeps its 3:1 aspect ratio. The Home states that the image is illustrative and is not a Goodnight Inn property. This supersedes the earlier rejection below after the user's explicit design direction.
- Reworked the Home headline, supporting copy, CTA and provenance footer; added the photo to the Home/Brand Overview/Hotel Explorer bookmark visibility states. Restyled the two analytical hero KPI rows as cards, gave native charts clearer panels, tightened page 1's vertical rhythm and shortened page 2's primary CTA after the first PDF export exposed truncation. Only UX text/CSS in `Board Metrics.tmdl` changed; the financial calculations and recommended portfolio did not.
- Saved `The Investment Challenge.pbip` with the Home active, overwrote `The Investment Challenge - Goodnight Inn.pbix`, and replaced both screenshots in `submission/` from the final two-page Desktop PDF export.

## Tests executed for the layout update (2026-11-05)
| Test | Result |
|---|---|
| PBIP reopened twice in Power BI Desktop after external PBIR/TMDL edits; no load error; Home photo, logo and text render | Pass |
| Brand Overview bookmark hides the Home image and overlay; Home bookmark restores them | Pass |
| Both analytical pages render; the final page 1 KPI/chart spacing and full page 2 CTA label were visually checked in Desktop and in the final PDF export | Pass |
| Desktop Selection pane tab order: Home overlay first, then its text and action button; decorative photo/logo/footer excluded from focus | Pass |
| PBIP saved with Home active; existing PBIX overwritten through Desktop Save As; PBIX displayed the Home | Pass |
| Final Desktop PDF export has two pages; rendered JPGs were visually reviewed and replaced in `submission/` | Pass |
| PBIR syntax: 123 JSON files parse; 2 pages visible; original photo and registered resource have matching SHA-256 hashes | Pass (structural check) |
| Theoretical WCAG contrast over the 92%-opaque panel, assuming an all-white image underneath: ivory 14.47:1, gold 7.65:1, secondary 10.87:1; CTA text on gold 8.92:1 | Pass (static calculation, not an assistive-technology test) |

## Remaining validation
- Keyboard-only navigation in reading view / Power BI Service and screen-reader pass.
- Runtime en-US locale review (Desktop tested in pt-BR).
- Submission post by the participant.

## 2026-11-05 update
- Evaluated `Resort de Luxo ao Entardecer home.png` against the existing Home. Rejected it: the luxury resort and pool would imply a property/positioning unsupported for Goodnight Inn. The official P&K logo remains undistorted on the solid navy Home. No report screenshot changed.
- Calculated WCAG contrast for the Home text colors against its solid `#020C2A` background: ivory 17.19:1, gold 9.09:1, secondary text 12.91:1, footer 8.74:1. This is a static color calculation, not a screen-reader test.
- Reordered the Home overlay ahead of covered page objects in the tab sequence. Removed its background shape, logo image and footer text from keyboard focus (`tabOrder` excluded); retained the main heading and `ENTER THE DECISION` button. No semantic-model or financial calculation changed.
- Saved the existing PBIP in Power BI Desktop and overwrote `The Investment Challenge - Goodnight Inn.pbix` through Save As. The resulting PBIX displayed the Home in Desktop.

## Tests executed in Power BI Desktop (2026-11-05)
| Test | Result |
|---|---|
| PBIP reloads after the Home tab-order edit, without load errors; Home is displayed | Pass |
| Selection pane tab order: Home first; main text then Enter; background, logo and footer excluded | Pass |
| Scenario = Low in investment comparison, project timeline and scenario explorer; Low selection persists across bookmarks and return to The Decision | Pass |
| Low-case NPV method panel: total present value = −$5,153,001 | Pass |
| Low-case risk panel: negative NPV and no capital recovery by 2032 shown | Pass |
| Reset on page 2 restores Recommended / Expected | Pass |
| PBIP saved; existing PBIX overwritten with Save As and Home rendered in Desktop | Pass |
| PBIR JSON parses after save (122 JSON files); 2 public pages and 2 tooltip pages marked `HiddenInViewMode` | Pass (structural check) |

## Still pending
- Keyboard-only navigation in reading view / Power BI Service and screen-reader pass.
- Runtime en-US locale review (Desktop tested in pt-BR).
- Submission post by the participant.

## Relevant changes
- Concept: one screen, one decision; deeper analysis on demand. Still exactly 2 visible pages (+2 hidden tooltip pages).
- Page 1 **Brand Overview**: headline + 3 KPIs, profit waterfall, channel mix, "So what" line. On demand: **Hotel Explorer** state (scatter, hotels-by-NPS table, margin by region, proposal facts) and a **Why did profit fall?** panel (driver table + revenue/margin combo).
- Page 2 **The Decision**: recommendation hero (capital, Expected NPV, Low-case risk), operational impact, Deneb decision map, funded-projects table, profit path, board decision. On demand: **Explore Investment Strategy** state with three tabs (comparison of all ten projects with full names, all-project Deneb timeline + cumulative cash, scenario explorer) and two panels (**How was NPV calculated?** with yearly cash flows; **What happens in the Low case?**).
- Bookmarks are display-only and target only the groups they change (17 bookmarks), so slicer selections survive state changes; Reset bookmarks clear filters without changing the state.
- Status rails: page 1 lists only active filters and distinguishes visual selections; page 2 states that projections are brand-wide.
- Model: +38 measures (209), column `Hotels[Hotel Short]`. Financial engine and results unchanged.
- Fixed during test: PV total row (was 2032 factor × total), duplicated measure name, heading contradicting the filter, unverified claim in the Low panel replaced by a computed one.

## Tests executed in Power BI Desktop (2026-11-04)
| Test | Result |
|---|---|
| Model loads without errors | Pass (after removing a duplicated measure) |
| File opens on Home; Enter → Brand Overview | Pass |
| Explore Hotel Performance → Back to Brand Overview | Pass |
| Why did profit fall? panel open / close | Pass |
| Filter drawer open / close; Region = Europe kept across Overview → Hotel Explorer; rail shows REGION: EUROPE · HOTELS 29/50 | Pass |
| Reset (page 1) clears filter, keeps current state | Pass |
| Hotel tooltip on scatter | Pass |
| Explore Investment Strategy; tabs comparison / timeline / scenarios; Back to The Decision | Pass |
| NPV panel: PV total = NPV on page ($3,251,487) | Pass (after fix) |
| Low-case panel open / close | Pass |
| Portfolio = Big bets → Reset → Recommended / Expected, state kept | Pass |
| Project tooltip on comparison table | Pass |
| Home from page 2 | Pass |
| Buttons under closed panels remain clickable | Pass (observed while testing) |
| PBIP saved; PBIX overwritten via Save As and rendering in Desktop | Pass |

## 2026-11-04 pending list (historical)
The items above supersede the earlier pending list; only tests explicitly recorded as executed on 2026-11-05 have been closed.
