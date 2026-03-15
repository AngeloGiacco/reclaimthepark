# CLAUDE.md — Reclaim the Park

## Project Overview

**Reclaim the Park** is a civic campaign to reimagine and improve public access to London's Royal Parks. The project combines research, community organising, design competitions, FOI requests, and a public-facing website to build the case for change.

## Repository Structure

```
reclaim-the-park/
├── website/          — Campaign website (static site)
├── research/         — Data, analysis notebooks, source documents
├── comms/            — FOI requests, authority correspondence, ally outreach
├── competitions/     — Design competition briefs, submissions, judging
├── press/            — Press releases, media coverage log, media kit
├── plans/            — Strategy, pilot proposals, legal research
├── community/        — Petition, events, supporter coordination
└── .github/workflows — CI/CD for site deployment
```

## Key Conventions

- **Markdown first**: all prose content is Markdown (`.md`)
- **Data**: CSVs and JSON in `research/data/`, never Excel
- **FOI tracking**: `comms/foi/tracker.md` is the single source of truth for all FOI requests
- **Strategy timeline**: `plans/strategy/timeline.md` is the master campaign checklist
- **Stakeholder map**: `plans/strategy/stakeholder-map.md` tracks all stakeholders

## Tech Stack

- **Website**: Static site (HTML/CSS/JS) in `website/`
- **Analysis**: Jupyter notebooks in `research/analysis/`
- **CI/CD**: GitHub Actions in `.github/workflows/`

## Coding Standards

- Keep the website lightweight and accessible — no heavy frameworks
- All public-facing content should be clear, factual, and well-sourced
- FOI requests and formal letters use templates in `comms/templates/`
- Competition entries go in `competitions/submissions/` organised by competition name

## Licence

- Code: MIT
- Content (text, images, research): CC BY-SA 4.0
