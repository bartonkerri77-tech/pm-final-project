# Feature Roadmap, Module 4 · StreamLine Spotlight

**Team:** 2 engineers + 1 designer

## Strategic anchors
- **Persona:** The Wanderer
- **Primary metric:** Decrease the Month 0 → Month 6 drop (only 16% of people stay in the app after 6 months)
- **Moment of misery:** The user is currently forced to... endlessly scroll through our massive 15,000-title library without finding what they want, often abandoning the app
- **Guardrail:** The Month 0  → Month 6 drop cannot increase

## Scoring
| Feature | Value | Effort | Quadrant | Decision | Rationale |
|---|---|---|---|---|---|
| A1 Spotlight Curated Rail | 5 | 2 | Quick Win | Now | Directly bypasses the exact friction — "endless scroll" — with no algorithm to build; ships in a 3-week sprint as a rail + manual curation feed. |
| A2 'Why You'll Love This' Label | 4 | 5 | Major Project | Later | Attacks decision paralysis directly, but per-title AI rationale generation isn't buildable by 2 engineers in 3 weeks — sequence after the Rail proves the model. |
| A3 Hidden Gem Badge | 2 | 2 | Fill-In | Later | Cheap to ship, but a badge only helps once a user is already looking at a title — it doesn't solve the scroll/discovery problem itself. |
| A4 Mood-Based Entry Point | 4 | 4 | Major Project | Next | Cuts the 15,000-title wall at first touch, but tagging the catalog by mood is a real content-ops lift, not a UI-only change. |
| A5 Personalized Spotlight Queue | 5 | 5 | Major Project | Later | Wait for the Rail and Label to validate the curation thesis before committing to a full recommendation-system build. |
| A6 Spotlight Digest Email | 5 | 2 | Quick Win | Now | Recreates the competitor's exact winning behavior (2 hand-picked films/week) inside our own channel, pulling lapsing Wanderers back before Month 6. |
| A7 Curator Profiles | 2 | 4 | Time Sinker | Later | Needs an established curator roster from A1 first; revisit once that roster exists. |
| A8 Watch Party (Spotlight) | 1 | 5 | Time Sinker | Cut | No connection to discovery friction or the primary metric; the infra cost isn't justified this cycle. |
| A9 Advanced Filter Engine | 2 | 3 | Time Sinker | Later | Backlog item for power users — not tied to the Wanderer's actual friction or the primary metric. |
| A10 Offline Download (Spotlight) | 2 | 5 | Time Sinker | Cut | Heavy DRM/storage build with no path to moving Month 0→6 retention; not worth the team's capacity. |

## Roadmap
### NOW, 3-week sprint
- **A1 Spotlight Curated Rail**, Directly bypasses the exact friction — "endless scroll" — with no algorithm to build; ships in a 3-week sprint as a rail + manual curation feed.
- **A6 Spotlight Digest Email**, Recreates the competitor's exact winning behavior (2 hand-picked films/week) inside our own channel, pulling lapsing Wanderers back before Month 6.

### NEXT, following 1-2 sprints
- **A4 Mood-Based Entry Point**, Cuts the 15,000-title wall at first touch, but tagging the catalog by mood is a real content-ops lift, not a UI-only change.

### LATER, backlog
- **A2 'Why You'll Love This' Label**, Attacks decision paralysis directly, but per-title AI rationale generation isn't buildable by 2 engineers in 3 weeks — sequence after the Rail proves the model.
- **A3 Hidden Gem Badge**, Cheap to ship, but a badge only helps once a user is already looking at a title — it doesn't solve the scroll/discovery problem itself.
- **A5 Personalized Spotlight Queue**, Wait for the Rail and Label to validate the curation thesis before committing to a full recommendation-system build.
- **A7 Curator Profiles**, Needs an established curator roster from A1 first; revisit once that roster exists.
- **A9 Advanced Filter Engine**, Backlog item for power users — not tied to the Wanderer's actual friction or the primary metric.

### ✂ Cut List
- **A8 Watch Party (Spotlight)**, No connection to discovery friction or the primary metric; the infra cost isn't justified this cycle.
- **A10 Offline Download (Spotlight)**, Heavy DRM/storage build with no path to moving Month 0→6 retention; not worth the team's capacity.

### WIREFRAME OF PROTOTUPE
<img width="1087" height="884" alt="image" src="https://github.com/user-attachments/assets/4ab53d0a-8941-4f87-8edd-ef87405ff406" />
