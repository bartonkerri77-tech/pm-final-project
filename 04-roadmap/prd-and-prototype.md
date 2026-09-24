# PRD & Prototype Sprint (Module 4)

## Pick & scope with MoSCoW
- **The “Now” feature I’m scoping (name + one-line core description):** Spotlight Curated Rail

Directly bypasses the exact friction — "endless scroll" — with no algorithm to build; ships in a 3-week sprint as a rail + manual curation feed.
- **My finalized Must-Haves (after overriding the AI):** A hand-curated Spotlight rail visible immediately on the home screen, positioned above the algorithmic rows — interrupts the scroll-and-abandon pattern at the very first screen, where it actually starts.
A minimum curated set of ~15-20 titles, refreshed through a lightweight, non-engineering content feed (spreadsheet/CSV an editor can update) — without an actual curated list there's no human-led curation for the Wanderer to land on; it's the entire mechanism of the bet.
Functional click-through from a rail title straight into playback/detail — a curated rail the user can't act on doesn't stop the abandonment behavior; the see → pick → watch loop has to complete in one flow.
- **What I demoted from Must → Should/Won’t, and why:** I demoted this to Should Have because it can ship without an extra visualization as long as the core content is there: Clear "hand-picked" visual differentiation ton the rail (distinct label/styling from other rows) — the misery isn't just volume, it's mistrust of the algorithm; an undifferentiated rail just reads as one more algorithmic row to scroll past.

The remaining items look like this. 
SHOULD HAVE

Clear "hand-picked" visual differentiation on the rail (distinct label/styling from other rows) — reinforces that this isn't algorithmic, which matters for trust, but the rail can ship and still interrupt the scroll pattern without it; worth the design polish if capacity allows.
Basic impression/click-through tracking on the rail — needed to prove the primary metric and catch a guardrail breach, but tracking itself doesn't stop anyone from abandoning the app.
A documented content-refresh cadence so curation keeps happening weekly without pulling in engineering.
A short one-line "why this pick" caption per title, if the designer has spare capacity — reinforces trust without needing A2's AI build.

COULD HAVE

Light personalization of which curated titles surface first by cohort (Wanderer vs. others), short of true AI personalization.
Editorial theming/rotation ("This Week's Picks," seasonal collections) to keep the rail feeling alive.
A "save to list" or "remind me" action directly on the rail card.
Hover previews or trailer snippets.

WON'T HAVE (NOW)

Any AI/ML-driven personalization of rail content — that's A5, already staged for Later.
Per-title "why this matches you" rationale text — that's A2, already sequenced for Later.
Mood-based filtering into the rail — that's A4, already sequenced for Next.
Curator profiles or "follow this curator" — that's A7, already Later.
Any change to or removal of existing algorithmic rows — the Rail is additive only; touching existing rows risks tripping the Month 0→6 guardrail.

## Generate your Simplified PRD
- **One thing my PRD makes explicit that a vague brief would have missed:** The press release portion provides clear business context and explaination

## Prompt-to-prototype sprint
- **Where did the prototype reveal a gap in my PRD logic? (what I had to update):** My PRD logic failed to talk about how the new feature differentiates from current carousels
- **My prototype, as a link or a screenshot (publish or share from your tool; in Lovable that is Share → Share Preview, in Bolt Publish → Web. No share URL? Screenshot the working flow):

Example from Loveable 
https://rapid-user-path.lovable.app

Example from Claude prompting
<img width="1368" height="787" alt="image" src="https://github.com/user-attachments/assets/1ad6e579-c7f6-4e97-9e59-665a07ee9108" />

<img width="1421" height="753" alt="image" src="https://github.com/user-attachments/assets/2483f1cc-dfab-4f3b-8118-8edb9f50ea43" />

<img width="1356" height="916" alt="image" src="https://github.com/user-attachments/assets/aa044fe0-9375-4e2b-8c0e-95e63c702a61" />

