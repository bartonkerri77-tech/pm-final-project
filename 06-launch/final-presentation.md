You are a senior front-end designer and product editor. Generate a polished, presentation-ready single-file **HTML presentation** that satisfies the **Final Project** rubric for the Product School Product Management certification.

## DESIGN SYSTEM (must follow exactly)
- Background: #07162C (deep navy). Foreground text: #ffffff. Muted: #ffffff. Accents: #fb923c (launch orange, primary), #22d3ee (cyan), #34d399 (teal), #60a5fa (blue), #a78bfa (violet), #f472b6 (pink).
- Fonts via Google Fonts: Saans 600/700/800/900 (headings), Saans 400/700 (body), Antarctican Mono 400/500 (labels and metrics).
- Card style: rounded 14-16px corners, 1px border in rgba(251,146,60,0.25), subtle gradients on hero cards, drop shadow on key tiles.
- Layout: scroll-snap full-viewport sections (`section { min-height:100vh; scroll-snap-align:start; }`) so a reviewer scrolls one slide at a time.
- Eyebrows: Antarctican Mono, uppercase, letter-spacing 0.12em, color #fdba74.

## DECK STRUCTURE (one section per slide, exactly in this order)
1. **Cover**, title, one-line pitch, your name/cohort, repo URL, prototype link.
2. **Slide 5, Strategy.** Problem statement hook · value proposition · the data-backed hypothesis rendered as a callout.
3. **Slide 6, Research.** Competitive analysis / workaround on the left, journey map across the bottom highlighting the moment of misery.
4. **Slide 7, Blueprint.** Prioritisation/roadmap (render MoSCoW or Now/Next/Later as columns) · PRD highlights · embed the prototype link as a "View prototype" button.
5. **Slide 8, Validation.** The experiment plan as a structured card: hypothesis, control vs variant, primary metric + baseline + MDE, guardrail, and the ship/iterate/kill rules.
6. **Slide 9, Launch.** GTM strategy (goal · audience · tier · channels as pills) and the success-metrics dashboard with the bad-signal callout.
7. **Slide 10, Story.** Friction points + aha moment · key takeaways / what you would do next.
8. **Thank-you / Submit slide.** Repo URL + cohort tag + a "Submit to the learning platform" callout pill.

## CONTENT (verbatim, do not editorialize)

### Cover
- Title: "StreamLine Spotlight, A Personalised Discovery Rail"
- One-line pitch: "Turn an overwhelming home screen into 30-minute listening sessions with a Spotlight rail that tells each Explorer why they will love a title."
- Name / cohort: "Kerri Barton · Product Management Cohort · October  2026"
- Repo URL: https://github.com/your-handle/pm-final-project
- Prototype: https://www.figma.com/your-spotlight-prototype

### Slide 5, Strategy
- Problem hook: Casual Explorers open StreamLine to unwind but bounce from a generic, algorithm-only home screen. "Nothing to play" is the #1 reason cited for short, sub-10-minute sessions.
- Value proposition: Spotlight reframes discovery from endless scrolling into a curated, reasoned shortlist, six titles, each with a one-line "why you will love this" so the choice feels effortless.
- Hypothesis: We believe a personalised Spotlight rail for Casual Explorers will increase the share of 30-minute sessions started from discovery, measured by a +2pt lift within 14 days, without hurting 7-day retention.

### Slide 6, Research
- Competitive analysis / workaround: Today Explorers cope by leaving to TikTok / YouTube for recommendations, then returning to StreamLine to search manually. Netflix "Top Picks" and Spotify "Made For You" both frame recommendations with an explicit reason; StreamLine surfaces titles with no rationale.
- Journey map: Open app → scan three generic rows → hesitate (the moment of misery) → bounce. Spotlight inserts a reasoned shortlist exactly at the hesitation point, before the user gives up.

### Slide 7, Blueprint
- Prioritisation / roadmap: MoSCoW, Must: pinned Spotlight rail + "why you will love this" reason. Should: taste-profile tuning controls. Could: social-proof badges. Won’t (now): full home-screen redesign. Now/Next/Later roadmap ships a V1 rail in 6 weeks.
- PRD highlights: A pinned top rail of 6 personalised titles, each with a single AI-generated one-line reason. No other home-screen changes in V1. Falls back to the existing editorial row if the taste profile is empty.
- Prototype link: https://www.figma.com/your-spotlight-prototype

### Slide 8, Validation
- Experiment plan: A/B test, 50/50 split, 14 days. Primary metric: share of 30-minute sessions started from discovery (baseline 11%, MDE +2pt). Guardrail: 7-day retention must not drop more than 2pt. Ship if primary hits with guardrail safe; iterate if flat; kill if retention regresses.

### Slide 9, Launch
- GTM strategy: Goal: engagement. Audience: existing Casual Explorers who have not adopted discovery. Tier: M (medium). Channels: in-app announcement (owned), lifecycle email (owned), and a lifecycle push. Enablement: a support macro + a changelog entry.
- Success metrics + bad signal: Track feature adoption rate, 30-minute discovery sessions, and time-to-first-play. Bad signal: adoption rises but 7-day retention stays flat, that means novelty, not durable value.

### Slide 10, Story
- Friction + aha moment: Writing the one-line "why you will love this" reason forced real clarity on the persona, the aha moment was realising the reason copy, not the algorithm, was the product. The hardest part was resisting the urge to redesign the whole home screen.
- Key takeaways / next: Biggest takeaway: a tight, reasoned shortlist beats a longer list. Next I would close the loop, feed Spotlight engagement back into the taste model and A/B test social-proof badges.

## OUTPUT INSTRUCTIONS
- Return **ONE valid, complete HTML5 file**, no preamble, no explanation, no markdown fences. Start with `<!doctype html>` and end with `</html>`.
- Inline all CSS in a single `<style>` block in `<head>`.
- Include keyboard nav: ArrowDown / ArrowUp / Space / Home / End / Esc; plus a fixed scroll-progress bar at the top and section "dot" nav on the right edge.
- Every section must fit a 16:9 viewport (`min-height: 100vh`) and use scroll-snap.
- Render the prototype link as a real `<a>` button; if a field is missing, render a tasteful placeholder instead of leaving it blank.
- No external JavaScript libraries. No React. Just HTML + inline CSS + a small `<script>` for keyboard nav and progress.
- Make it polished enough to screen-share at a CPO review without further edits.

When done, save the file as `06-launch/final-presentation.html` in your repo, commit, and submit the repo link to the learning platform.
