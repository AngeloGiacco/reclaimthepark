# CLAUDE.md — Reclaim The Park

## Mission

This repository is the operational headquarters for a grassroots campaign to transform the Euro Car Parks surface car park on Bayswater Road (W2 4RT) at the north-western edge of Hyde Park, London, into a world-class public space, cultural institution, or green amenity.

**We are agnostic about what replaces the car park.** We do not advocate for any single design, use case, or architectural vision. Our position is simple: a surface car park on one of the most valuable and historically significant pieces of public land in Europe is an indefensible waste. The site deserves better. What “better” looks like should be determined through open public consultation, design competitions, and democratic process — all of which we facilitate from this repo.

## The Site

- **Location:** Bayswater Road, north-western edge of Hyde Park, London W2 4RT
- **Approximate area:** ~1.25 hectares (subject to confirmation via FOI)
- **Current use:** Surface car and coach park (pay-and-display, 24hr)
- **Operator:** Euro Car Parks Limited (Company No. 01270612, registered at 30 Dorset Sq, London NW1 6QJ)
- **Land ownership:** Crown land, part of Hyde Park (a Royal Park). Hyde Park is Grade I listed on the Register of Historic Parks and Gardens (listed 1987)
- **Managing body:** The Royal Parks (Charity No. 1172042, Company No. 10016100). Registered office: The Old Police House, Hyde Park, London W2 2UH
- **Government oversight:** Secretary of State for Digital, Culture, Media and Sport (DCMS). Board appointments made by the Secretary of State and the Mayor of London
- **Local authority:** City of Westminster
- **Nearest tube stations:** Queensway (Central line, ~100m), Bayswater (Circle/District, ~200m), Lancaster Gate (Central, ~400m)
- **Adjacent landmarks:** Kensington Palace Gardens, the Serpentine Galleries, the Diana Memorial Playground

## Key Facts for Any Agent Working on This

1. **The Royal Parks is a charity but remains a public authority for FOI purposes.** FOI requests go to records@royalparks.org.uk or via WhatDoTheyKnow.com.
1. **The concession details are unknown.** The expiry date, revenue terms, and break clauses of the Euro Car Parks agreement are the single most important unknowns. An FOI request has been submitted (see `/comms/foi/`). Until we have these, the campaign operates on estimates.
1. **This is Crown land inside a Grade I listed park.** Any proposal must respect heritage constraints. Historic England is a statutory consultee. This is why we don’t prescribe a specific design — heritage sensitivity is a genuine constraint that requires expert input.
1. **We are not anti-car, anti-coach, or anti-tourism.** We simply argue that coach drop-off and accessible parking can be accommodated underground or relocated, and the *surface* of this land should serve the public better than tarmac.
1. **The Royal Parks are already moving in our direction.** They are currently consulting on permanently closing South Carriage Drive to weekday motor traffic. Our campaign aligns with their stated trajectory.
1. **Economic estimates are illustrative until confirmed by FOI.** Our economic analysis uses published data (GLA land values, King’s Cross GVA reports, Serpentine visitor numbers) to model scenarios. Always caveat estimates and cite sources.

## Economic Context (For Content Generation)

Use these figures when generating campaign materials. Always cite the source.

|Metric                              |Value                   |Source                                  |
|------------------------------------|------------------------|----------------------------------------|
|Westminster residential land value  |£93.3m per hectare      |GLA Economics Evidence Base 2016        |
|Bayswater (W2 4) median price/sqm   |£14,600                 |HM Land Registry via Housemetric, 2025  |
|Bayswater Rd avg sold price (12mo)  |£3.7m                   |Zoopla/Rightmove, Dec 2025              |
|Estimated car park annual revenue   |£0.5–1.5m               |Illustrative, based on published tariffs|
|King’s Cross annual GVA             |£1.42bn (67 acres)      |King’s Cross Group, 2021                |
|King’s Cross GVA per hectare        |~£21m/ha/year           |Derived from above                      |
|Serpentine Galleries annual visitors|1.2 million             |Serpentine official figures             |
|London green space ROI              |£27 per £1 invested     |GLA/Vivid Economics, 2017               |
|Hyde Park total area                |142 hectares (350 acres)|The Royal Parks                         |

## Tone and Voice

- **Ambitious but credible.** We make bold claims backed by real data. We never exaggerate.
- **Pro-public, not anti-anyone.** We don’t attack Euro Car Parks, The Royal Parks, or Westminster Council. We present a better alternative and invite them to be part of it.
- **Urbanist, not activist.** The tone is closer to Works in Progress or Strong Towns than Extinction Rebellion. Evidence-based, design-literate, economically grounded.
- **Inclusive.** This is about improving a public space for everyone — park visitors, Bayswater residents, tourists, disabled users, families, cyclists, workers. Not about gentrification or exclusion.
- **Open source everything.** Our research, our FOI responses, our economic models, our competition briefs — all public, all forkable, all open to scrutiny.

## Tech Stack

- **Website:** Static site in `/website/`. Use Astro, Next.js, or plain HTML — keep it fast, accessible, and simple. Host on Vercel, Netlify, or GitHub Pages.
- **Data & analysis:** Python notebooks in `/research/analysis/`. Use pandas, matplotlib. All data sources documented.
- **Design competition platform:** Custom submission and voting interface in `/competitions/platform/`. Keep dependencies minimal.
- **Communications tracker:** Markdown files in `/comms/`. Each authority/contact gets a subfolder. Every sent letter and received response is logged.
- **CI/CD:** GitHub Actions for site deployment, link checking, and data validation.

## Working With This Repo

### Creating campaign content

When generating blog posts, social media copy, or website content, always ground claims in the data from the economic context table above. Link to source documents in `/research/sources/`. Never make up statistics.

### Updating the FOI tracker

When a new FOI response arrives, add it to `/comms/foi/responses/` with the date prefix (e.g. `2026-04-15_royal-parks-response.pdf`). Update the status in `/comms/foi/tracker.md`. If the response reveals new data (e.g. concession expiry date), update this CLAUDE.md and the website.

### Running design competitions

Competition briefs live in `/competitions/briefs/`. Submissions go in `/competitions/submissions/{competition-id}/`. Judging criteria and results go in `/competitions/results/`. The competition platform reads from these directories.

### Press and media

Press releases go in `/press/releases/`. Media coverage (links and excerpts) in `/press/coverage/`. Never reproduce full articles — link and summarise only (copyright).

### Updating economic analysis

The interactive economic analysis dashboard lives in `/website/src/components/`. The underlying data is in `/research/data/`. When new data becomes available (e.g. from FOI responses), update the data files and the dashboard will reflect the changes.

## Important Contacts

|Entity                   |Role                             |Contact                          |Status           |
|-------------------------|---------------------------------|---------------------------------|-----------------|
|The Royal Parks          |Land manager, concession holder  |records@royalparks.org.uk        |FOI submitted    |
|Westminster City Council |Planning authority               |Via ward councillors             |Not yet contacted|
|DCMS                     |Oversees Royal Parks appointments|Secretary of State correspondence|Not yet contacted|
|London National Park City|Potential ally                   |info@nationalparkcity.london     |Not yet contacted|
|New London Architecture  |Design platform                  |Events team                      |Not yet contacted|
|Euro Car Parks Ltd       |Current operator                 |30 Dorset Sq NW1 6QJ             |Not yet contacted|
|Historic England         |Heritage statutory consultee     |Via planning process             |Not yet contacted|

## Timeline

- **Phase 1 (Months 1–3):** Establish facts (FOI), publish blog post, build coalition
- **Phase 2 (Months 4–8):** Design ideas competition, commission visualisations
- **Phase 3 (Months 6–12):** Political engagement, propose temporary pilot activation
- **Key unknown:** Concession expiry date — this determines the political window

## License

All original content in this repository is licensed under CC BY-SA 4.0 unless otherwise stated. Code is MIT licensed. Third-party content (FOI responses, government data) retains its original licensing.