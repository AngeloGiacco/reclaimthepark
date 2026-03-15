# Research

All data, analysis, and source documents underpinning the campaign's economic and planning arguments.

## Principles

1. **Every claim must have a source.** No made-up statistics. If a number is an estimate, label it clearly.
2. **All analysis is reproducible.** Python notebooks with documented data sources. Anyone can re-run and verify.
3. **Conservative by default.** When modelling scenarios, use the low end of ranges. Our case is strong enough without optimistic assumptions.

## Structure

```
data/              # Raw and processed datasets (CSV, JSON)
  land-values.csv          # Westminster/Bayswater land value data
  carpark-revenue-est.csv  # Revenue estimates with methodology
  comparables.csv          # GVA, jobs, visitors for comparable sites
  timeline.json            # Key dates and milestones

analysis/          # Jupyter notebooks
  01-land-value.ipynb      # Land value opportunity cost calculation
  02-scenario-modelling.ipynb  # GVA projections for different use cases
  03-job-creation.ipynb    # Employment estimates by scenario
  04-property-uplift.ipynb # Surrounding property value impact

sources/           # PDFs, reports, and links to authoritative data
  gla-economics-2016.md    # Link + key extracts from GLA Evidence Base
  kings-cross-regeneris.md # Link + key figures from Regeneris report
  royal-parks-annual.md    # Links to Royal Parks annual reports
  land-registry/           # HM Land Registry extracts for W2 postcodes

comparables/       # Profiles of comparable sites
  kings-cross.md
  serpentine-galleries.md
  coal-drops-yard.md
  borough-market.md
  thames-barrier-park.md
```

## Key Data Sources

| Source | What | URL |
|---|---|---|
| GLA Economics Evidence Base 2016 | Westminster land values | london.gov.uk |
| Regeneris 2017 | King's Cross economic impact | kingscross.co.uk |
| HM Land Registry | W2 property transactions | landregistry.data.gov.uk |
| The Royal Parks Annual Reports | Park income and expenditure | royalparks.org.uk |
| Vivid Economics 2017 | London green space valuation | london.gov.uk |
| Companies House | Euro Car Parks Ltd accounts | companieshouse.gov.uk |
