# A/B Experiment Brief, StreamLine (B2C)

## Parameters
| Parameter | Decision |
|---|---|
| Feature under test | StreamLine Spotlight |
| Persona | The Wanderer |
| Expected outcome | Expect wanderers to spend more time with curated content and stay with the platform longer - this should significantly change the churn improvement |
| Primary success metric | Viewing metrics |
| Baseline rate | 24 mins per session |
| Guardrail metric | Sessions reaching 30+ min |
| Guardrail boundary | Must not drop below 9% |
| Second guardrail | Content searched then played, 34% |
| Minimum Detectable Effect | 4 minutes |
| Sample size per arm | 1,683 |
| Traffic split | 50/50 |
| Test duration | 31 days |
| Significance threshold | p <.05 (95%) |

## Control vs. Variant
- **Control (A):** The user is currently forced to... endlessly scroll through our massive 15,000-title library without finding what they want, often abandoning the app
- **Variant (B):** A hand-curated Spotlight rail visible immediately on the home screen, positioned above the algorithmic rows — interrupts the scroll-and-abandon pattern at the very first screen, where it actually starts. A minimum curated set of ~15-20 titles, refreshed through a lightweight, non-engineering content feed (spreadsheet/CSV an editor can update) — without an actual curated list there's no human-led curation for the Wanderer to land on; it's the entire mechanism of the bet. Functional click-through from a rail title straight into playback/detail — a curated rail the user can't act on doesn't stop the abandonment behavior; the see → pick → watch loop has to complete in one flow.
- **Held constant (isolation check):** Menus stay the same , Continue Watching Stays the Same, No change to algorithm, no introduction of new carousels, no branding changes.

## Hypothesis
> I believe that StreamLine Spotlight for The Wanderer will result in Expect wanderers to spend more time with curated content and stay with the platform longer - this should significantly change the churn improvement, as measured by a 4 minutes change in Viewing metrics within 31 days. We will protect Sessions reaching 30+ min throughout the test.

## Shipping criteria
> We will **ship** if Viewing metrics improves by ≥ 4 minutes at p <.05 (95%) and Sessions reaching 30+ min does not reach Must not drop below 9% after 31 days.
> We will **iterate** if direction is positive but lift is below the MDE.
> We will **kill** if the primary metric shows no improvement or moves negatively.
> The read date is fixed at the end of 31 days, no results reviewed before this date.
