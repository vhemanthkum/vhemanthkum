# Part B – Scaling to 1000 Companies

---

## The actual problem with scaling this

When I did 25 companies for Hyderabad, the work for each company looked like:
- Go to their website and actually read it
- Check if the revenue number someone cites is from an actual MCA filing or just someone estimating
- Verify the founder is still running the company and has a technical background
- Find one specific recent detail worth mentioning in outreach

That took meaningful time per company. If I need to do 1000 companies across 12 cities, I can't just do that 40 times over — the quality will collapse somewhere in the middle. So the answer isn't 40x effort, it's building a system where the effort doesn't scale linearly.

Here's how I'd approach it.

---

## Three-layer structure

**Layer 1: Build a raw universe of 3000+ companies**  
Before any human looks at a company, pull the raw data. The best sources:

- **MCA (Ministry of Corporate Affairs)**: Every registered company in India has a CIN, NIC industry code, state, and incorporation date. Filter to relevant NIC codes for our four segments + Telangana state + incorporated before 2020 → gives you ~3000-4000 companies to start with

  NIC codes that matter:
  - Specialty Biotech → 2111, 2112, 2120
  - Diagnostics → 2660, 3250
  - Custom synthesis/API → 2100, 2109
  - Performance chemicals → 2019, 2011, 2029

- **CPHI India exhibitor lists**: Companies that paid to show up at the largest pharma trade show are almost always real manufacturers. Archive goes back several years, free.

- **DGFT export data**: Companies that actually exported from India in the last 24 months. Strong signal that they're active and making something.

- **Telangana Life Sciences / T-Hub directories**: The state government maintains its own list.

- **ICRA/CRISIL-rated companies list**: If a company has gone for a bank rating, they're almost certainly above Rs.50Cr and operationally serious. Public documents.

**Layer 2: Auto-disqualify without human review**  
Apply hard rules to cut from 3000 to ~1000:

| Rule | How to check |
|------|-------------|
| Revenue <Rs.30Cr or >Rs.600Cr | MCA paid-up capital proxy or Tofler |
| Incorporated after 2020 | MCA incorporation date |
| "Trading" or "Import" in company name | String filter |
| NCLT proceedings | NCLT.gov.in search |
| PE firm as promoter (>30%) | MCA shareholding filings |
| No website or single-page site | Automated URL check |

Expected: 3000 → 800-1000 after this layer. No human time spent on companies that fail hard filters.

**Layer 3: Human research on the shortlist**  
For each of the ~1000 remaining companies, apply the 6-point research card (same criteria as Hyderabad):

```
C1 – Manufacturer (facility, GMP cert, not a services company)
C2 – Right geography (actual operations in that city)
C3 – Differentiated product (niche, not commodity)
C4 – Technical founder/MD (PhD, engineering background, still active)
C5 – Growing sector (PLI, China+1, Make-in-India, export markets)
C6 – Active signal in last 12 months (hiring, expansion, news, updated website)
```

---

## What AI can do vs. what needs a human

| Task | AI/automation | Human |
|------|--------------|-------|
| Pull NIC-filtered MCA data | Yes | — |
| Auto-apply hard disqualification rules | Yes | — |
| Scrape websites for facility mention + certification | Yes | — |
| Estimate revenue range from paid-up capital | Yes | — |
| Verify a financial figure is from ICRA vs. speculation | — | Yes |
| Decide if a PE stake is controlling or minority | — | Yes |
| Write the personalization hook | AI draft | Human edits |
| Borderline calls | — | Yes |

For a team doing this: one research lead handling borderline decisions and quality checks, 3-4 analysts running the 6-point card. At 8-10 companies per analyst per day, 1000 companies takes about 12-15 weeks.

---

## Extending to 12 cities

Same architecture, just run for each city. The segment emphasis changes by city:

| City | Strong segments | Key industrial zones |
|------|----------------|----------------------|
| Hyderabad | Specialty Biotech, Custom Synthesis, Diagnostics | Genome Valley, Bollaram, Pashamylaram |
| Pune | Custom Synthesis, Performance Chemicals | Chakan, MIDC Ambad |
| Ahmedabad | Performance Chemicals, Agro-Chem | GIDC Ankleshwar, Vatva |
| Chennai | Specialty Biotech, Diagnostics | Sholinganallur, Sriperumbudur |
| Bengaluru | Specialty Biotech, Custom Synthesis | Peenya, Electronics City |
| Mumbai | Performance Chemicals, Diagnostics | MIDC Mahape, Tarapur |
| Coimbatore | Performance Chemicals | SIDCO, Mettupalayam |
| Indore | Custom Synthesis, API | MPIDC industrial areas |
| Nagpur | Performance Chemicals, Agro-Chem | MIHAN, Butibori |
| Visakhapatnam | Specialty Biotech, Custom Synthesis | VSEZ, Bheemunipatnam |
| Vadodara | Performance Chemicals, Custom Synthesis | GIDC Waghodia |
| Kolkata | Custom Synthesis, Performance Chemicals | Durgapur, Haldia |

---

## Main things that go wrong at scale

**Revenue inflation** — AI and researchers alike will pick the highest number they find. Rule: two independent sources to confirm any revenue figure. If only one source, mark "unverified."

**Same-name confusion** — At 1000 companies across 12 cities, you'll hit name collisions. Solution: always track CIN (Corporate Identification Number) as the unique ID, not company name.

**Stale data** — A company active in 2021 may have gone quiet. Require at least one signal from the last 12 months for C6 to pass. Job posting, press release, regulatory filing, website update — any of these counts.

**Standards drifting across analysts** — Four researchers won't score "differentiated" the same way. Build a shared reference document with 50 example decisions before the team starts.

---

## What the 1000-company database actually looks like when done

Not just a flat list — a structured prospect database you can slice by:

- Segment (biotech vs. chemicals vs. diagnostics)
- Revenue tier (Rs.50-100Cr, Rs.100-300Cr, Rs.300-500Cr)
- City
- Confidence level (Strong Fit / Fit / Borderline)
- Growth signal age (active <6 months vs. 6-12 months vs. stale)
- PE clean / PE minority / PE-controlled

That database becomes the foundation for prioritizing outreach — you reach the Strong Fits first, in the segments where your pitch is sharpest, in cities where your team has capacity.
