# Financial Audit — Phase 2 (2026-11-04)
Independent method: Python engine on `PillowKey_Dataset.xlsx` (monthly cash flows, same official rules), compared with DAX in Power BI Desktop.

## 1. Finding: the Phase-1 portfolio was the wrong decision
Phase 1 selected projects by run-rate yield (annual profit ÷ CAPEX ≥ 8%). That rule only makes sense if cash flows after 2032 are valued — i.e. an implicit terminal value, which the challenge horizon and our own policy exclude. Inside the official horizon (impact to Dec 2032, 8% discount rate from FinanceParameters) the correct criterion is **NPV**.

| Portfolio | CAPEX $M | NPV Low | **NPV Expected** | NPV High | Net cash 2027–32 (E) | Profit/yr 2032 (E) |
|---|---:|---:|---:|---:|---:|---:|
| **Recommended (new): GI-01 + GI-10 + GI-02** | **9.40** | **−5.15** | **+3.25** | **+12.33** | **+6.82** (payback 2031) | 3.53 |
| Digital + F&B (+GI-09) | 13.65 | −7.64 | +2.22 | +12.26 | +6.52 | 4.37 |
| Growth mix (old "Lean") | 26.05 | −15.16 | −4.57 | +5.82 | +0.50 | 6.08 |
| Yield list (old Recommended) | 41.05 | −27.86 | −15.64 | −3.64 | −10.31 | 7.86 |
| Big bets | 59.25 | −48.9 | −39.1 | −29.6 | −37.7 | 6.70 |

"Lean" recovered cash by 2032 but still destroys value at 8% (NPV −$4.6M): cash ≠ value.

## 2. Exhaustive search
All 1,024 combinations of the ten Goodnight Inn proposals: **456** meet the rules (budget ≤ $60M, ≥ 3 projects, ≥ 1 growth, DependsOn GI-02→GI-01, no ExclusiveWith conflict — none exist for this brand). **7** have NPV > 0 (Expected); **0** have NPV > 0 in the Low case. GI-01+GI-02+GI-10 is #1 in Low, Expected and High, and is also the cheapest compliant plan; correlation CAPEX vs NPV across compliant plans = −0.93. Full list: `AUDIT_all_valid_portfolios.csv`. The same universe is rebuilt in DAX (`Portfolio Universe`) and matches: 1,024 / 456 / 7 / rank 1 / NPV 3,251,487.

Why: project NPVs are additive (no shared cash flows). Only GI-01 (+3.29) and GI-10 (+0.54) are positive; the 3-project rule then forces the least-negative third project, GI-02 (−0.57).

Standalone NPV to 2032, $M (Low / Expected / High): GI-01 −2.59/+3.29/+9.20 · GI-10 −1.38/+0.54/+3.09 · GI-02 −1.18/−0.57/+0.03 · GI-09 −2.49/−1.03/−0.06 · GI-05 −3.75/−3.28/−3.07 · GI-04 −3.78/−3.51/−3.38 · GI-06 −5.37/−3.70/−3.59 · GI-03 −12.69/−11.07/−9.45 · GI-08 −18.28/−17.46/−16.97 · GI-07 −28.03/−24.95/−21.83.

## 3. Recommended plan, risk profile
IRR to 2032 (annual flows, no terminal value): Low −19%, Expected 21%, High 54%. Break-even needs **73%** of the Expected impact (old plan needed 164%, i.e. more than the High case delivers). Downside accepted: NPV −$5.2M in the Low case. The dataset gives no scenario probabilities, so no expected value across scenarios is computed.

## 4. Assumption checks
| Item | Check | Result |
|---|---|---|
| Running costs | Reconstructed GI-01 profit = rev×(1−11.28%) + 1.2pts×$200.7M − $0.6M | 2.343M vs dataset 2.350M → impact already **net**; not subtracted again |
| GI-02 opex effect | 0.8% × $51.4M opex of its 20 hotels | 411,086 vs 411,000 ✓ |
| Overlaps on same hotels | GI-10 ADR uplift × GI-01 distribution saving | ≈ $14k/yr → ignored (documented) |
| CAPEX phasing / ramp | Even over duration; 50/85/100% from month after completion | DAX = Python monthly |
| Disruption | OOS% × 2025 same-month room revenue, net of hotel distribution rate | Not relevant to the Recommended plan (no rooms out of service) |
| Timing | Earliest start; GI-02 after GI-01 completes | Later starts only lower NPV for positive projects |
| Discount rate | 8% (dataset); sensitivity 6% / 10% | NPV 3.99 / 2.59 — still #1 |
| Baseline | 2025 actual held flat, 2025 USD | Incremental NPV independent of baseline level |

Not provided by the dataset (our assumptions): no terminal value; costs continue during works; additive project effects; annual discounting to 2026.

## 5. Distribution cost decomposition (Brand Review)
2023→2025 distribution +$2.91M = volume +$0.86M + channel mix +$2.05M + rate $0.00 (commission rates identical in every channel and year). 2021→2025: +$10.06M = volume 5.26 + mix 4.81 + rate 0. Mix alone ≈ 80% of the 2023→2025 profit decline. Mathematical decomposition, not a causal claim: the dataset does not say why guests moved to OTAs.
