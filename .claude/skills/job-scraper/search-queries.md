# Search Queries for Job Scraper

## Search Sites

Primary (job portals with installed CLIs in `.agents/skills/`):
- **jobindex.dk**, **jobnet.dk**, **jobbank** (Akademikernes Jobbank), **jobdanmark.dk** - Denmark
- **linkedin.com/jobs** - global via `linkedin-search` CLI, filter by explicit location string (Denmark, India, Belgium, Netherlands, Finland, Sweden as relevant)
- **freehire.dev** - multi-market tech aggregator via `freehire-search` CLI (region/country facets)

India note: no dedicated India job-board CLI is installed yet. `linkedin-search` and `freehire-search` both work for Indian cities out of the box (e.g. `-l "Bengaluru, Karnataka, India"`). If coverage feels thin, run `/add-portal` to scaffold a dedicated CLI for Naukri.com, Indeed India, or Foundit (Monster India).

Secondary (company career pages via Google):
- Direct Google searches with `site:` filters for known target companies (see Priority 1 target companies below)

## Query Categories

Queries are grouped by priority. Each query should be combined with the relevant location terms below where the site supports it - use only the specific city/country relevant to a given search pass, not the full relocation list.

### Priority 1: DSP / Signal Processing Engineering (audio & hearing tech)

Strongest and most desired career direction.

```
site:jobindex.dk "DSP Engineer" OR "Signal Processing Engineer" Copenhagen
"Algorithm Developer" "signal processing" Denmark
"Speech Enhancement" OR "Audio Researcher" Denmark
site:linkedin.com/jobs "DSP Engineer" Denmark
site:linkedin.com/jobs "signal processing engineer" Bengaluru OR Bangalore India
site:linkedin.com/jobs "DSP engineer" OR "audio algorithm" Belgium OR Netherlands OR Finland OR Sweden
```

Target companies to monitor: Demant/Oticon, GN/Jabra, Sonova/Phonak, WSAudiology, Qualcomm (Speech & Audio Research), Goodix, TrackMan

### Priority 2: Audio & Speech Machine Learning

Domain expertise: combining classical DSP with deep learning for audio.

```
"adaptive beamforming" OR "multi-microphone noise reduction" Denmark OR India
"speech enhancement" machine learning Denmark
site:linkedin.com/jobs "audio machine learning" OR "acoustic ML" Denmark OR Bengaluru India
"mask estimation" OR "spatial audio" research engineer
```

### Priority 3: Adjacent Signal Processing / Sensor Fusion

Roles that transfer the estimation/detection/optimization skillset outside audio specifically.

```
"sensor fusion engineer" "signal processing" Denmark OR India
"radar signal processing" OR "sonar signal processing" Denmark OR Netherlands OR Sweden
"applied research scientist" acoustics OR "signal processing" Denmark OR India
```

### Priority 4: Broader ML / Research Engineering

Wider net, general net-casting roles that still touch signal processing or applied ML.

```
"machine learning engineer" audio OR acoustic Denmark OR India OR Belgium OR Netherlands OR Finland OR Sweden
"research engineer" "signal processing" OR "deep learning" Denmark OR India
site:linkedin.com/jobs "algorithm engineer" Denmark OR India
```

## Location Filter

Candidate is currently based in Copenhagen, Denmark, and is open to relocation. Define acceptable areas:
- **Ideal:** Copenhagen / Smørum area, Denmark (current base, no relocation needed)
- **Acceptable (relocation):** Bengaluru/Bangalore, India; other cities in Belgium, Netherlands, Finland, Sweden
- **Too far:** Any country outside Denmark, India, Belgium, Netherlands, Finland, Sweden

Work-mode preference: hybrid or partly-hybrid/onsite roles preferred over fully remote-only roles.

## Date Filter

Only include jobs posted within the last 14 days, or with an application deadline that has not yet passed. If a posting date cannot be determined, include it but flag as "date unknown".

## Adapting Queries

If the user specifies a focus area, select queries from the matching category and also generate 2-3 custom queries for that focus. For example:
- "/scrape [focus_area]" -> relevant category queries + custom focus-specific queries
- "/scrape india" -> Priority 1-2 queries filtered to India locations only
- "/scrape denmark" -> Priority 1-2 queries filtered to Denmark locations only
