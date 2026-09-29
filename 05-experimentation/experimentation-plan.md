# A/B Experiment Brief, StreamLine (B2C)

## Parameters
| Parameter | Decision |
|---|---|
| Feature under test | StreamLine Spotlight |
| Persona | The Wanderer |
| Expected outcome | Expect wanderers to play content from the curated spotlight rail |
| Primary success metric | Time to first play of any title |
| Baseline rate | 2 mins |
| Guardrail metric | Sessions reaching 30+ min |
| Guardrail boundary | Must not drop below 9% |
| Second guardrail | Viewing minutes per user per week |
| Minimum Detectable Effect | 30 seconds faster |
| Sample size per arm | 1,683 |
| Traffic split | 50/50 |
| Test duration | 28 days |
| Significance threshold | p <.05 (95%) |

## Control vs. Variant
- **Control (A):** Wanderers open the home screen and see the current layout: global navigation, Continue Watching, then algorithmically ranked rows such as "Because you watched…", Trending Now and New on StreamLine. No hand-picked row exists. To find something, they scroll the rows or search the full 15,000-title catalog.
- **Variant (B):** One new row, titled "Spotlight," is added as the first row on the home screen. It shows 15–20 titles picked by the StreamLine editors. Every Wanderer in Variant sees the same list, in the same order, for the whole day. Tapping a Spotlight tile opens the title's detail page, exactly as tapping any other tile does. If the feed has fewer than 15 valid titles or fails to load, the row doesn't appear and the user sees Control. Count those sessions in Variant anyway (intent-to-treat).
- **Held constant (isolation check):** Global navigation, menus and search
Continue Watching: its contents and how it works
Every algorithmic row: its titles, order and ranking logic
The detail page, the player and the tap-to-detail flow
No new rows beyond Spotlight, and no branding, artwork or copy changes elsewhere
Pricing, notifications, emails and onboarding

## Hypothesis
> I believe that StreamLine Spotlight for The Wanderer will result in Expect wanderers to play content from the curated spotlight rail, as measured by a 30 seconds faster change in Time to first play of any title within 28 days. We will protect Sessions reaching 30+ min throughout the test.

## Shipping criteria
> We will **ship** if Time to first play of any title improves by ≥ 30 seconds faster at p <.05 (95%) and Sessions reaching 30+ min does not reach Must not drop below 9% after 28 days.
> We will **iterate** if direction is positive but lift is below the MDE.
> We will **kill** if the primary metric shows no improvement or moves negatively.
> The read date is fixed at the end of 28 days, no results reviewed before this date.
