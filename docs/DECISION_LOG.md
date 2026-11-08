# Decision Log — The Investment Challenge · Round 1
_Updated 2026-11-05 (photographic Home and layout QA). Status: Implemented / Tested / Blocked._

## D-01 · Brand: Goodnight Inn (unchanged)
Revenue +$8.9M, operating profit −$2.6M (2023→25). OTA share 32% → 49% at 18% fee; rates unchanged, mix shift = $2.05M of cost. See FINANCIAL_AUDIT §5.

## D-03 (revised) · Portfolio: GI-01 + GI-10 + GI-02, $9.4M
Highest NPV of 456 compliant plans in every scenario. $50.6M held in reserve. Low-case NPV −$5.2M disclosed on page.

## D-06 · Phase-2 design decisions
Decision-first investment page; Deneb decision-space map with native twin; NPV-ranked table; distribution split into volume vs mix.

## D-07 · Phase-3 progressive disclosure
- Each page shows one message by default; detail opens in states (groups switched by bookmarks) or modal panels. No third page.
- Bookmarks carry no data (suppressData) and target only their groups, so filters are preserved; only Reset changes filters.
- Panels chosen for the questions a judge asks first: why profit fell, how NPV was computed, what the Low case means. "Why was this project rejected?" is answered in the project tooltip (Project Rationale) rather than a panel.
- Combo chart moved from the overview into the Why panel; option bar moved into the Scenario explorer; ≥4 native visuals stay visible by default (waterfall, stacked column, funded table, profit line).
- Home overlay is the default view when the file opens.
- No hotel photograph was used in the Phase-3 Home.

## D-08 · Home asset and focus order (2026-11-05)
- Rejected `Resort de Luxo ao Entardecer home.png` for the Home. Its luxury resort setting could misrepresent Goodnight Inn; the current official logo on navy communicates the brand without implying a specific property. The image was assessed, not inserted, so no photo/text contrast claim is made.
- The Home overlay now precedes covered objects in tab order. Its decorative shape, image and footer are excluded; the heading and Enter button remain. Verified in the Desktop Selection pane after reopening the PBIP.
- Low scenario was walked through the decision, comparison, timeline, scenario explorer, NPV method and downside panel. The financial engine and recommendation remain unchanged.

## D-09 · User-directed photographic Home and landing layouts (2026-11-05)
- The user explicitly selected the twilight resort photograph after D-08. It is now an illustrative Home background, with a navy reading panel, the undistorted official logo and an on-page note that it is not a Goodnight Inn property. The original photo file was not edited.
- Figma contains three editable layout frames: Home overlay, Brand Overview and The Decision. PBIP still has two visible pages; the Home remains a bookmark overlay on page 1.
- `UX Hero Review` and `UX Hero Decision` received CSS card styling; the decision hero now states the computed $50.6M reserve via `_rem`. No finance measure, portfolio selection or dataset value changed.
- Native waterfall, stacked column, funded-projects table and profit line remain visible in the default analytical states. Page 2's main CTA was shortened after an exported-page review found truncation.
