# Spotlight Rail Prototype

*StreamLine · Spotlight Curated Rail · working prototype of the PRD*

A clickable prototype of the Spotlight Curated Rail. It shows the Wanderer's core flow (**see → pick → watch**) on mobile and TV, a curator-edited CSV feed, the safety guard, every edge case from the PRD, and live pass/fail checks against the seven functional requirements.

- **Source file:** `04-roadmap/Spotlight_Rail_Prototype.html` (single file, no external libraries)
- **PRD:** Spotlight Curated Rail — PRD (Kerri Barton)

---

## 1. Layout

The page has two parts:

- **Device preview (left):** the StreamLine app inside a phone or TV frame, with a toolbar:
  - **Mobile / TV** toggle
  - **Reopen app**, which starts a new session and picks up any published feed update
  - **+1 hour**, which advances the simulated clock so a published update goes live
  - A session counter and clock
- **Control panel (right):** three tabs, **Scenarios**, **Curator feed** and **Checks & evals**.

---

## 2. Core flow (the user scenario)

1. **Home.** The global navigation is unchanged. **Spotlight** is the first row, labeled "✦ Curated especially for you," and shows 15–20 hand-picked titles. Below it, the existing algorithmic rows are unchanged:
   - Continue Watching (with progress bars)
   - Because you watched Fast X
   - Trending Now
   - New on StreamLine
2. **Pick.** Tapping any tile opens its title detail page in one tap, the same for Spotlight and every other row.
3. **Detail.** Backdrop art, title, year · runtime · genre, director, synopsis and a **Play** button. Titles opened from Spotlight also show **"Why our editors picked it,"** a one-line editor's note. **Back** returns to home at the same scroll position.
4. **Watch.** Playback starts straight away, with no confirmation step. A progress bar and pause control are shown. A `playback_start` event is logged in the background with no visible UI.

**TV mode:** a 16:9 frame with top navigation. Arrow keys move between tiles and rows, Enter selects and Esc goes back, like a remote.

---

## 3. Curator feed

A plain CSV the curation team edits. Each row is one title, in rail order, and reordering means moving lines. No deploy is needed.

```csv
title_id,title_name
SL-1001,Past Lives
SL-1004,Perfect Days
SL-1002,Aftersun
SL-1003,Portrait of a Lady on Fire
SL-1013,Honeyland
SL-1005,The Holdovers
SL-1014,The Worst Person in the World
SL-1008,Minari
SL-1010,Drive My Car
SL-1016,Hunt for the Wilderpeople
SL-1021,Roma
SL-1009,The Farewell
SL-1012,My Octopus Teacher
SL-1019,Fallen Leaves
SL-1015,Petite Maman
SL-1O17,Arrival
SL-1006,Paterson
SL-1011,Shoplifters
SL-1001,Past Lives
SL-1020,Anatomy of a Fall
```

**Editor features**

- A live row-by-row preview for the chosen viewer region, showing which titles will appear and which are dropped
- A row counter ("20 / 20 rows")
- **Publish feed**, which is blocked below 15 or above 20 rows with a clear message ("Remove 3 before publishing")
- **Revert to live**
- A catalog reference list with an **Add** button for each title

**Publishing:** an update goes live on the next app open or within one hour, whichever comes first. Use **Reopen app** or **+1 hour** to see it.

**Same-day stability:** reopening the app without a new publish shows the same list. It never reshuffles mid-day.

---

## 4. Safety guard

Each feed row is checked before it can appear on the rail:

| Status | Rule | Example in the default feed |
|---|---|---|
| Shows | Valid, unique, licensed in the viewer's region | 17 titles |
| Duplicate · dropped | Only the first occurrence is kept, and a curator warning is logged | Past Lives (row 19) |
| Unknown ID · dropped | The ID doesn't exist in the catalog (typo or bad entry) | `SL-1O17` (letter O instead of zero) |
| Delisted · dropped | Rights have expired | Roma |
| Region-locked · hidden | Not licensed where the viewer is | Minari, for UK viewers |

If fewer than 15 valid titles remain, or the feed fails to load, the rail **does not render**. There's no empty or broken row, and home looks exactly as it does today. The recommendation algorithm never fills the gaps.

---

## 5. Scenarios

Each scenario reopens the app so you see what a Wanderer would see.

| Scenario | What happens |
|---|---|
| **Healthy feed** | 20 picks. 3 are dropped by the guard (Past Lives duplicate, Arrival typo, Roma delisted). 17 show. |
| **Only 12 titles in the feed** | Below the 15-title minimum, so the rail hides. |
| **Heavy filtering (UK viewer)** | 15 rows, 4 bad (duplicate, unknown ID, Roma, Minari). 11 remain, so the rail hides. |
| **Feed empty at launch** | The editor hasn't filled it in yet. No rail, no empty row. |
| **Feed fails to load** | The request times out and the rail is left out silently. |

**Other controls**

- **Viewer region (US / UK):** Minari isn't licensed in the UK.
- **Show "Hand-picked" label:** the Should Have from the decision log. Off by default.

---

## 6. Checks & evals

**Functional requirements (live pass/fail)**

| ID | Requirement | How it's checked |
|---|---|---|
| FR1 | Spotlight is the first row on home | The first rendered row is Spotlight whenever the rail shows |
| FR2 | 15–20 titles, from the feed only, no backfill | Tile count, and every tile ID is in the live feed |
| FR3 | Curators edit without a deploy | CSV publish, with pending and live status |
| FR4 | Tile opens detail in one tap, the same as other rows | The same tap → detail path for every row |
| FR5 | Fewer than 15 valid titles, or a load failure, hides the rail | No Spotlight row is in the page when suppressed |
| FR6 | Same content and function on mobile and TV | Passes once both devices have been viewed |
| FR7 | Algorithmic rows unchanged | Rendered row order and contents match the baseline |

**Evals**

- **Median time to first pick**, with the rail shown vs hidden
- **Broken, delisted or locked tiles shown** (target: 0)
- **Feed rows dropped by the guard**, flagged when above 2% ("flag curation team")
- **Session table:** session number, device, whether the rail showed, time to first pick, and where the pick came from (Spotlight or an algorithmic row)
- **Event log:** `app_open`, `feed_load`, `rail_rendered` / `rail_suppressed`, guard and curator warnings, `tile_select`, `detail_view`, `playback_start`

---

## 7. Example catalog

These are real films with accurate year, runtime, genre and director. The synopses and editor's notes were written for the prototype. Poster art is generated color art matched to each title's genre, not the films' real posters.

**Spotlight picks (curated)**

| ID | Title | Year | Runtime | Genre | Director | Note |
|---|---|---|---|---|---|---|
| SL-1001 | Past Lives | 2023 | 1h 46m | Drama · Romance | Celine Song | |
| SL-1002 | Aftersun | 2022 | 1h 42m | Drama | Charlotte Wells | |
| SL-1003 | Portrait of a Lady on Fire | 2019 | 2h 2m | Drama · Romance · French | Céline Sciamma | |
| SL-1004 | Perfect Days | 2023 | 2h 4m | Drama · Japanese | Wim Wenders | |
| SL-1005 | The Holdovers | 2023 | 2h 13m | Comedy-Drama | Alexander Payne | |
| SL-1006 | Paterson | 2016 | 1h 58m | Drama | Jim Jarmusch | |
| SL-1007 | Columbus | 2017 | 1h 44m | Drama | Kogonada | |
| SL-1008 | Minari | 2020 | 1h 55m | Drama | Lee Isaac Chung | Not licensed in the UK |
| SL-1009 | The Farewell | 2019 | 1h 40m | Comedy-Drama | Lulu Wang | |
| SL-1010 | Drive My Car | 2021 | 2h 59m | Drama · Japanese | Ryusuke Hamaguchi | |
| SL-1011 | Shoplifters | 2018 | 2h 1m | Drama · Japanese | Hirokazu Kore-eda | |
| SL-1012 | My Octopus Teacher | 2020 | 1h 25m | Documentary | Pippa Ehrlich, James Reed | |
| SL-1013 | Honeyland | 2019 | 1h 26m | Documentary | Tamara Kotevska, Ljubomir Stefanov | |
| SL-1014 | The Worst Person in the World | 2021 | 2h 8m | Comedy-Drama · Norwegian | Joachim Trier | |
| SL-1015 | Petite Maman | 2021 | 1h 12m | Drama · French | Céline Sciamma | |
| SL-1016 | Hunt for the Wilderpeople | 2016 | 1h 41m | Adventure · Comedy | Taika Waititi | |
| SL-1017 | Arrival | 2016 | 1h 56m | Sci-Fi | Denis Villeneuve | |
| SL-1018 | Paddington 2 | 2017 | 1h 43m | Family · Comedy | Paul King | |
| SL-1019 | Fallen Leaves | 2023 | 1h 21m | Comedy · Romance · Finnish | Aki Kaurismäki | |
| SL-1020 | Anatomy of a Fall | 2023 | 2h 31m | Legal Thriller · French | Justine Triet | |
| SL-1021 | Roma | 2018 | 2h 15m | Drama · Spanish | Alfonso Cuarón | Delisted (rights expired) |
| SL-1022 | Moonrise Kingdom | 2012 | 1h 34m | Comedy · Romance | Wes Anderson | |

**Existing algorithmic rows (unchanged by Spotlight)**

- **Continue Watching:** The Bear (S2), Severance (S1), Oppenheimer, Planet Earth II
- **Because you watched Fast X:** F9, Furious 7, The Fate of the Furious, Hobbs & Shaw, Fast Five
- **Trending Now:** Dune: Part Two, Oppenheimer, Barbie, Top Gun: Maverick, John Wick: Chapter 4, Everything Everywhere All at Once
- **New on StreamLine:** Dune: Part Two, Ted Lasso (S3), John Wick: Chapter 4, Severance (S1), Barbie, Top Gun: Maverick

---

## 8. Build constraints honored

These follow the PRD's "what not to build" list:

- **No external APIs or libraries:** the feed is a flat CSV, and the whole prototype is a single HTML file.
- **No login or personalization:** every viewer in a region sees the same list.
- **Plain local state only:** no global store or persistence layer.
- **No backend service:** the feed is read directly.
- **No change to recommendation logic:** Spotlight only adds UI and a data feed.
