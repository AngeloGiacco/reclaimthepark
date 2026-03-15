# CLAUDE.md — Frontend / Website

## Overview

Build the campaign website for **Reclaim The Park** — a grassroots campaign to transform a car park at the edge of Hyde Park into something extraordinary for London. The site should be data-driven, emotionally compelling, and make it effortless for visitors to take action.

**Live URL target:** reclaimthepark.org (or similar)

---

## Aesthetic Direction

### The Feeling

The site should feel like walking into a beautifully designed exhibition at the Serpentine Gallery or a KPF project presentation — confident, warm, editorial, and human. NOT like a charity petition page. NOT like a tech startup. NOT like an activist campaign with angry red typography.

Think: **Dezeen meets the Financial Times meets the Serpentine Pavilion programme booklet.**

### Visual Language

**Light mode, not dark.** The campaign is about openness, parks, public space — dark themes contradict the message. Use a warm, light foundation.

**Colour Palette:**
```
--bg-primary:      #FAFAF7    /* warm off-white, like quality paper */
--bg-secondary:    #F0EDE6    /* warm stone, like Portland limestone */
--bg-accent:       #E8E3D8    /* slightly darker stone for cards */
--text-primary:    #1A1A18    /* near-black, warm */
--text-secondary:  #5C5A52    /* warm grey for secondary text */
--text-tertiary:   #8A8780    /* muted for captions */
--accent-green:    #2D6A4F    /* deep park green — the primary accent */
--accent-gold:     #B8860B    /* warm gold for highlights, CTAs */
--accent-red:      #C0392B    /* sparingly, for the "current waste" stats */
--border:          #D4D0C8    /* subtle warm borders */
--surface-glass:   rgba(255,255,255,0.85)  /* for floating elements */
```

**Typography:**
- **Headlines:** A serif with character. Use `Playfair Display` or `Libre Baskerville` — editorial, serious, beautiful. Never Inter, never sans-serif for headlines.
- **Body:** `Source Serif 4` or `Lora` — readable, warm, bookish. 18px base size, 1.7 line-height.
- **Data/stats:** `JetBrains Mono` or `IBM Plex Mono` — for economic figures, giving them credibility and weight.
- **UI/navigation:** `IBM Plex Sans` — clean, professional, doesn't compete with the serif.

**Layout Principles:**
- Generous whitespace. Let content breathe. Minimum 80px between sections.
- Max content width: 720px for prose (like a well-typeset book). Full-width for hero images, data visualisations, and proposal galleries.
- Asymmetric layouts welcome — editorial magazine style, not rigid grid.
- Images bleed to edges. Text stays centred and narrow.

**Motion:**
- Subtle. Content fades up on scroll (staggered, 100ms delay between elements).
- Stats count up when they scroll into view.
- Parallax on hero images (very gentle, 0.1 ratio).
- No flashy transitions, no loading animations. Confidence, not performance.

**Photography & Renders:**
- The four AI-generated renders are the hero images. Display them large, edge-to-edge.
- Use a subtle warm filter/overlay on all images to unify the aesthetic.
- Captions below renders: italic, smaller text, always credit "Concept render — not a formal proposal."

---

## Tech Stack

- **Framework:** Next.js (App Router) or Astro — static export, deployed to Vercel
- **Styling:** Tailwind CSS with the custom palette above as CSS variables
- **Animations:** Framer Motion (React) or CSS-only (Astro)
- **Data viz:** Recharts or D3 for the economic comparison charts
- **Forms:** Formspree or Netlify Forms for petition sign-up and email capture
- **CMS:** Markdown files in the repo. No external CMS.
- **Analytics:** Plausible (privacy-respecting, no cookies)

---

## Site Structure

```
/                          → Landing page (the main event)
/memo                      → The full economic and planning memo with citations
/proposals                 → Gallery of three proposals with renders
/proposals/tower           → The Hyde Park Tower (skyscraper)
/proposals/school          → The London School of Making (timber)
/proposals/cultural-dock   → The Hyde Park Cultural Dock (brick/bronze)
/act                       → Take action: email MP, sign petition, share
/about                     → About the campaign, team, contact
/faq                       → Common objections answered
/status                    → Live campaign status tracker (FOIs, milestones)
```

---

## Page Specifications

### 1. Landing Page (`/`)

The landing page is the entire campaign in one scroll. It must take a visitor from "what is this?" to "I need to act" in under 3 minutes.

**Structure (top to bottom):**

#### Hero Section
- Full-viewport-height hero with the dusk tower render (Serpentine shot) as background
- Overlaid: the campaign title in large serif type
- Headline: **"Where there was a car park, there could be this."**
- Subhead: "A 4,385 sqm car park sits on Crown land at the edge of Hyde Park. It employs 5 people. We think London deserves better."
- Two CTAs: `Sign the petition` (primary, gold) and `Read the case` (secondary, outlined)
- Subtle scroll indicator at bottom

#### The Problem (emotional)
- Side-by-side: actual Google Street View photo of the car park vs. one of the concept renders
- Caption: "This is 150 Bayswater Road today. This is what it could be."
- Two short paragraphs explaining the waste — keep it emotional, not wonky
- Key stat displayed large in monospace: **"£78–165 million in lost economic value over the next decade"**

#### The Numbers (data)
- Three large stat cards in a row:
  - `£41–64m` — "Opportunity cost of this land" 
  - `217×` — "The economic uplift from the best alternative" 
  - `2,800` — "Jobs that could exist here"
- Below: an interactive comparison bar chart — car park vs. three proposals — showing GVA, jobs, and visitors side by side
- Source citations inline, small text, linked to the memo page

#### Three Proposals (visual)
- Horizontal scroll gallery (mobile) or three-column grid (desktop)
- Each card: full-bleed render, proposal title, one-sentence description, key stat (jobs or GVA), and a "Learn more →" link
- The three proposals:
  1. **The Hyde Park Tower** — "London's first free public skyscraper. 2,800 jobs. £217m annual GVA. Free entry." (Use the glass tower street-level render)
  2. **The London School of Making** — "A 4-storey timber workshop, design school, and public maker space." (Use the timber colonnade render)
  3. **The Hyde Park Cultural Dock** — "Gallery, workshops, market, and studios — a cultural village at the park gates." (Use the brick split-building render with the view through)

#### The Precedent
- A brief section with logos/images of King's Cross, Serpentine Galleries, Coal Drops Yard, Tate Modern
- One sentence each explaining how these were once wastelands/car parks/derelict sites and are now beloved London destinations
- Moral: "Every great public space was once someone's bad idea to improve."

#### Campaign Status
- A minimal timeline/roadmap component showing:
  - ✅ Research complete
  - ✅ FOI submitted
  - 🔄 Building coalition
  - ○ Design competition
  - ○ Political engagement
  - ○ Pilot proposal
- "Last updated: [date]"

#### Call to Action (the close)
- Full-width warm green background section
- Headline: **"This car park won't transform itself."**
- Three action buttons:
  1. `Email your MP` — opens pre-filled email (see below)
  2. `Sign the petition` — inline form (name + email + postcode)
  3. `Share the campaign` — Twitter/X, LinkedIn, copy link
- Below: "Join [X] people who've signed" (live count from form submissions)

#### Footer
- Links to all pages
- "An open-source campaign. [View on GitHub →]"
- "We are not affiliated with The Royal Parks, Westminster City Council, or any political party."
- CC BY-SA 4.0 notice

---

### 2. The Memo (`/memo`)

This is the LessWrong-style evidence page — every claim cited, every number sourced. Long-form, single-column, designed for credibility.

**Design:**
- 720px max-width prose column
- Left margin: a floating mini-table-of-contents that highlights as you scroll (like LessWrong/Substack)
- Citations in the text as superscript numbers: "Westminster residential land is valued at £93.3m per hectare¹." 
- Footnotes at the bottom of each section (not end of page) — expandable inline
- Key statistics pulled out as large-format callout blocks with monospace numbers
- Charts embedded inline where they support the argument

**Sections:**
1. Executive Summary (3 paragraphs)
2. The Site (location, ownership, governance, constraints)
3. The Concession (what we know, what we don't, FOI status)
4. Land Value Analysis (Westminster data, W2 comparables, opportunity cost)
5. Scenario Modelling (car park vs. three alternatives, GVA per hectare methodology)
6. Employment Impact (direct, indirect, induced — by scenario)
7. Comparable Sites (King's Cross, Serpentine, Coal Drops Yard, Tate Modern — each with data)
8. The Free Entry Model (how London's free institutions fund themselves)
9. Heritage & Planning Constraints (Grade I listing, what's permissible)
10. Recommendations (transparency, consultation, pilot)
11. Sources & Methodology

**Citation format:**
```
¹ GLA Economics, "Economic Evidence Base for London 2016," Chapter 4: Land. 
  Westminster residential land value estimated at £93.3m per hectare. 
  https://london.gov.uk/sites/default/files/chapter4-economic-evidence-base-2016.pdf
```

Every factual claim must have a citation. If a number is estimated/modelled, it must say "Estimated:" and explain the methodology. This page is the campaign's credibility backbone.

---

### 3. Proposals (`/proposals` + individual pages)

**Gallery page (`/proposals`):** 
Three cards, each with a hero render, title, one-paragraph description, and key stats. Clean grid.

**Individual proposal pages (`/proposals/[slug]`):**

Each page follows the same template:

1. **Hero render** — full-width, edge-to-edge
2. **Title + one-line description**
3. **"What is this?"** — 2-3 paragraphs describing the concept
4. **Stats grid** — 4 cards: Annual GVA, Direct Jobs, Annual Visitors, Green Space Created
5. **How it works** — the programme/floor plan described in prose, with an illustrated cross-section diagram if possible
6. **The economic case** — revenue model, funding model, comparables
7. **Render gallery** — 2-4 renders (street-level, aerial, interior if available)
8. **"What KPF would say"** — a short section on the design philosophy, referencing real KPF projects
9. **CTA** — "This is one possibility. [View all proposals →] or [Sign the petition →]"

Always include the caveat: *"This is a concept illustration, not a formal architectural proposal. The campaign is agnostic about the final design — we believe any well-designed alternative would vastly outperform the current car park."*

**The three proposals:**

**A. The Hyde Park Tower** (slug: `tower`)
- The provocation. Frame it as the boldest possible vision.
- Include the Crystal Palace precedent section.
- Free entry economic model front and centre.
- Key stats: 2,800 jobs, £217m GVA, 2.5m visitors, 86% of site returned to park.
- Renders: street-level glass tower, dusk Serpentine shot.

**B. The London School of Making** (slug: `school`)
- The crowd-pleaser. Timber, craft, education, visible making.
- Frame as "London's answer to the Bauhaus."
- Key stats: 150-220 direct jobs, 800-1,200 annual graduates, £20-35m GVA.
- Renders: the timber colonnade image (image 1 from uploads).

**C. The Hyde Park Cultural Dock** (slug: `cultural-dock`)
- The most buildable. Brick, bronze, KPF Covent Garden DNA.
- The view through to the park is the hero moment.
- Key stats: 250-350 direct jobs, £30-55m GVA, gallery + workshops + market.
- Renders: the brick split-building image (image 4 from uploads).

---

### 4. Take Action (`/act`)

The most important page after the landing page. Three clear actions:

**Email Your MP:**
- Postcode lookup (use TheyWorkForYou API or similar) that auto-detects the visitor's MP
- Pre-filled email template that the user can edit before sending
- "Send" button opens the user's default email client with the template filled in (mailto: link)
- Template should be brief, personal, and reference the economic case

**Sign the Petition:**
- Simple form: Name, Email, Postcode (optional), "I support the campaign" checkbox
- Store submissions (Formspree, Airtable, or Supabase)
- Show live count: "Join [X] supporters"
- After signing: share buttons (Twitter/X, LinkedIn, WhatsApp, copy link)

**Share the Campaign:**
- Pre-written social posts for Twitter/X and LinkedIn
- One-click copy buttons
- Open Graph meta tags must be perfect — the dusk tower render as the OG image, the headline as the OG title

---

### 5. Campaign Status (`/status`)

A live tracker showing where things stand. Simple, honest, updated manually via markdown.

- Timeline component (vertical on mobile, horizontal on desktop)
- Each milestone: title, description, date, status (complete/in-progress/upcoming)
- Link to relevant documents (FOI requests, responses, letters sent)
- "Last updated" timestamp prominently displayed

---

### 6. FAQ (`/faq`)

Accordion-style Q&A addressing common objections:

- "Isn't this a Grade I listed park? You can't build there."
- "Where would the coaches park?"
- "Who would pay for this?"
- "Isn't this just gentrification?"
- "Do you have planning permission?"
- "Why don't you just extend the park?"
- "A skyscraper next to Hyde Park? That's insane."
- "Who are you? What gives you the right?"

Each answer: factual, concise, cited where possible. Tone: respectful, not defensive.

---

## Component Library

Build these reusable components:

### `<StatCard>`
Large monospace number + label + source link. Used everywhere.
```
Props: value (string), label (string), source (string), accent (boolean)
```

### `<ComparisonChart>` 
Horizontal bar chart comparing car park vs. proposals on a given metric (GVA, jobs, visitors). Animated on scroll-in.

### `<ProposalCard>`
Render image + title + description + key stat + link. Used on landing page and proposals gallery.

### `<Timeline>`
Vertical timeline with status indicators. Reads from a JSON/markdown data source.

### `<CitedText>`
Wraps text content with superscript citation numbers. Clicking the number scrolls to/expands the footnote.

### `<ActionBlock>`
Full-width CTA section with headline, description, and 1-3 action buttons.

### `<RenderGallery>`
Lightbox-enabled image gallery for architectural renders. Always includes the "concept render" caveat.

### `<PetitionForm>`
Name + email + postcode form with live submission count. Validates, submits, shows confirmation + share buttons.

### `<MPLookup>`
Postcode input → looks up MP → generates pre-filled email → opens mailto link.

---

## Data Sources

All data lives in `/data/` as JSON files:

```
/data/site.json          — site measurements, address, identifiers
/data/economics.json     — all economic figures with sources
/data/proposals.json     — three proposals with stats, descriptions, render paths
/data/comparables.json   — King's Cross, Serpentine, Tate Modern data
/data/timeline.json      — campaign milestones and status
/data/faq.json           — questions and answers
```

Every number in every JSON file must have a `source` field with a URL or citation.

---

## SEO & Social

**Title:** "Reclaim The Park — Transform Hyde Park's Worst-Kept Secret"
**Description:** "A 4,385 sqm car park sits on Crown land at the edge of Hyde Park. It employs 5 people. London deserves better."
**OG Image:** The dusk tower render from the Serpentine (1200×630, cropped for social)
**Twitter Card:** Large image card
**Canonical URL:** https://reclaimthepark.org

---

## Performance Targets

- Lighthouse score: 95+ on all metrics
- LCP: < 2.5s on 3G
- CLS: < 0.1
- Total page weight: < 1MB (excluding render images, which should be lazy-loaded and served as WebP)
- Accessible: WCAG 2.1 AA minimum. All images have alt text. All interactive elements keyboard-navigable. Colour contrast ratios met.

---

## Content Tone Reminders

- **Never say "we demand."** Say "we believe" or "we propose" or "we ask."
- **Never attack anyone.** The Royal Parks, Euro Car Parks, and Westminster Council are potential partners.
- **Always cite.** Every economic claim links to a source.
- **Use "could" not "will"** for projections. "This site could generate £217m in annual GVA" not "will generate."
- **The campaign is agnostic about the solution.** We show proposals to provoke imagination, not to prescribe. Always include the caveat.
- **Emotional hooks are about people, not numbers.** "800 people could work here" hits harder than "£46m revenue." Lead with the human, follow with the data.

---

## Image Assets

Place all render images in `/public/renders/`:
```
tower-street.png          — Glass tower from Bayswater Road
tower-serpentine.png       — Dusk shot from Serpentine (THE hero image)
tower-aerial.png           — Aerial drone view
school-street.png          — Timber School of Making from Bayswater Road
cultural-dock-street.png   — Brick Cultural Dock with view through to park
carpark-current.png        — Current Google Street View of the car park
carpark-map.png            — Google Maps showing the location
```

Serve all images as WebP with JPEG fallback. Lazy load everything below the fold.

---

## Deployment

- Deploy to Vercel or Netlify from the GitHub repo
- Custom domain: reclaimthepark.org
- SSL: automatic via platform
- Branch previews: enabled for PRs
- Environment variables: form submission endpoints, analytics keys

---

## First Build Priority

Build in this order:
1. Landing page (this IS the campaign — everything else is secondary)
2. The memo page (credibility backbone)
3. Three proposal pages (with the renders we have)
4. Take action page (email MP + petition)
5. FAQ
6. Status page
7. About page

The landing page alone, if well-executed, is enough to launch the campaign. Everything else can follow in subsequent PRs.
