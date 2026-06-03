# BookTok *Enemies-to-Lovers* Dataset: Literary Tropes as Prescriptive Devices

Dataset of TikTok BookTok content collected to support the observational case study on literary tropes as prescriptive devices reported in the paper below.

## Citation

> Silvia Cappa, Mariangela Giglio, and Anna Sofia Lippolis. **Literary Tropes as Prescriptive Devices: A Case Study from BookTok.** In *Proceedings of AIUCD 2026*. .

## Overview

The dataset contains **100 TikTok videos** from BookTok that explicitly discuss or employ the *enemies to lovers* trope. Data were collected manually in early 2026 via two complementary streams:

- **Query stream** — search query `booktok enemies to lovers` on TikTok (default relevance ranking), first 50 results saved
- **For You Page stream** — 90-minute scrolling session on a freshly created clean account after controlled algorithmic priming (10 likes, 10 follows); first 50 on-topic results saved

Videos with no content type annotation (N/A) were excluded from the released dataset; the 100 entries here correspond to all annotated, content-typed videos.

## Files

| File | Rows | Description |
|------|------|-------------|
| `dataset_tiktok_anonymised.csv` | 100 | Main dataset — fully annotated videos only (no N/A entries). Used for all quantitative analysis in the paper. |


## Columns

| Column | Description |
|--------|-------------|
| `video_id` | TikTok numeric video ID (stable identifier; URL reconstructable as `tiktok.com/video/<id>`) |
| `date` | Upload date (YYYY-MM-DD where parseable, original string otherwise) |
| `likes` | Like count at time of collection |
| `comments` | Comment count at time of collection |
| `saves` | Save/bookmark count at time of collection |
| `caption` | Full video caption including hashtags |
| `text_in_video` | On-screen text transcribed from the video or slideshow (not audio) |
| `content_type` | Primary annotation: `rec` (recommendation) or `int` (interpretation) |
| `subtype` | Secondary annotation — see coding scheme below |
| `discussion_in_comments` | Flags videos where the comment section contains notable trope negotiation |
| `notes` | Free-text annotation notes |

### Coding Scheme

**Content type** reflects primary communicative purpose:

| Value | Meaning |
|-------|---------|
| `rec` | Creator explicitly recommends books using the trope as a selection frame |
| `int` | Trope used primarily to describe, evaluate, or discuss a work; recommendation secondary or absent |

**Subtype** captures recurring platform-specific formats (multiple values possible, newline-separated):

| Value | Description |
|-------|-------------|
| `text` | Slideshow / on-screen text excerpt from a book |
| `normative eval` | Defines or polices what counts as "true" enemies to lovers |
| `structure` | Analyses how the trope is implemented narratively (pacing, arc) |
| `emotional` | Reaction or emotional response to trope content |
| `POV` | POV-format video |
| `self promo` | Creator promoting their own work (fanfiction or published) |
| `wrap up` | Reading wrap-up where trope is discussed among other elements |

## Statistics

### Content Type Distribution (N = 100)

| Content type | Count | % |
|-------------|-------|---|
| Recommendation (`rec`) | 53 | 53% |
| Interpretation (`int`) | 47 | 47% |

### Subtype Distribution (normalised, N = 100)

| Subtype | Count |
|---------|-------|
| Text excerpt | 24 |
| Normative evaluation | 21 |
| Self-promotion | 8 |
| Structure analysis | 5 |
| Emotional reaction | 3 |
| POV format | 1 |

> Some videos carry multiple subtypes. Counts reflect individual subtype occurrences across the corpus.

### Engagement (at time of collection)

| Metric | Min | Median | Mean | Max |
|--------|-----|--------|------|-----|
| Likes | 62 | 15,800 | 77,908 | 973,000 |
| Comments | 0 | — | 740 | 22,200 |
| Saves | 19 | — | 16,637 | 163,900 |

### Top Hashtags (from captions, N = 100)

| Hashtag | Videos |
|---------|--------|
| #booktok | 67 |
| #enemiestolovers | 59 |
| #bookrecs | 30 |
| #bookrecommendations | 27 |
| #fyp | 23 |
| #bookish | 19 |
| #romancebooks | 18 |
| #romantasy | 14 |
| #darkromance | 14 |
| #enemiestoloverstrope | 13 |

### Comment Section Discussions

5 videos were flagged for notable trope-negotiation activity in their comment sections, where users collectively refine definitional boundaries of the trope.

### Collection Period

Videos range from **September 2022 to January 2026**, with the majority concentrated in late 2025 – early 2026, reflecting the period of data collection.

## Anonymisation

> **Disclaimer:** This dataset has been anonymised to the best of our ability prior to public release. We cannot guarantee that no residual identifying information remains, particularly in free-text caption and transcript fields. If you believe a re-identification risk persists, please open an issue.

The following steps were taken:

| What was removed | How |
|-----------------|-----|
| Creator TikTok handle and display name | Entire `creator` column dropped |
| Video URL | Entire `link` column dropped; only the numeric `video_id` is retained |
| `@mentions` of other creators in captions and on-screen text | Replaced with `[CREATOR]` |
| Creator-identifying personal hashtags (e.g. name-derived tags) | Removed from caption text |
| Creator name appearing in their own caption (self-promotion videos) | Creator name replaced with `[CREATOR]` |
| Creator's own book/work title in self-promo captions | Replaced with `[CREATOR WORK]` |

The `video_id` field retains the numeric TikTok video identifier. This allows the original video to be located on the platform but does not directly surface the creator's identity. Creators are treated as discursive instances, not as individuals, following established EU-based digital humanities practice for publicly available social media content collected for non-commercial academic research.

## Ethics and Legal Note

Data were collected manually from publicly available TikTok content. No automated scraping was used (TikTok ToS compliance). The study followed EU fair-use provisions for academic research and criticism. No personal data beyond publicly visible metadata are included.

## License

The dataset and annotations are released under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Caption and text-in-video content reproduces publicly posted material and is included for research purposes only.
