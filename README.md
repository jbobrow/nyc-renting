# NYC Renting · Know before you sign

Type any New York City address (and, if you like, an apartment number) and see what the city knows about the building before you sign a lease.

**Live site:** https://nycrent.jonbobrow.com

## What it checks

Each check is marked **Clear**, **Ask about it** or **Concern**, and compared with a random sample of NYC rental buildings where that makes sense.

| Check | Source |
| --- | --- |
| Hazardous violations | HPD Housing Maintenance Code violations |
| Heat and hot water | HPD complaints, by heat season |
| Bedbugs | Owners' annual bedbug filings |
| Evictions | Marshal evictions (DOI) |
| HPD lawsuits | HPD Housing Litigation, including harassment findings |
| City watch lists | Alternative Enforcement Program, vacate orders, Certification of No Harassment list, Speculation Watch List |
| Building safety | DOB complaints, DOB and ECB violations, boiler inspections |
| Noise on the block | 311 noise complaints within 150 m |
| Rats on the block | 311 rodent complaints within 150 m and DOHMH rodent inspections |

It also shows the registered owner and managing agent, an estimate of whether the building is rent stabilized, apartment-level history when you enter a unit, and questions to ask the landlord.

## How it works

It's a single static page, `index.html`, with no build step and no server. The browser queries [NYC Open Data](https://opendata.cityofnewyork.us/) (Socrata) and [NYC Planning GeoSearch](https://geosearch.planninglabs.nyc/) directly. Both allow cross-origin requests and need no API key.

Links to a report look like `#BBL-BIN-APT-STREET`, so they reopen the same building and apartment.

## Caveats

- HPD records mainly cover rental buildings with three or more units. Co-ops, condos and small homes may show little.
- Rent stabilization is an estimate from the building's age, size and type; the state doesn't publish a list.
- The comparison baselines were sampled in October 2026 and are embedded in the page (`BASE`).
- A clean record is a good sign, not a guarantee.

Made by [Jon Bobrow](https://apps.jonbobrow.com).

## Run locally

Open `index.html` in a browser, or serve the folder with any static server, e.g. `python3 -m http.server`.
