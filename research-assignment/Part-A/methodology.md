# Research Methodology – How I Approached This

## Picking Hyderabad + Basket A

I picked Hyderabad because I know the biotech and pharma cluster there is one of the strongest in India. Genome Valley has a lot of specialty manufacturers that most people don't look at closely — they're not public companies, they don't show up in typical lists, but if you dig, there's a lot there. Basket A (specialty biotech, diagnostics, custom synthesis, performance chemicals) felt like a natural fit for this geography — it's what Hyderabad is actually strong in, not just on paper.

---

## How I Started Building the List

I didn't start with a single source. I spread across:

- Company websites from **Genome Valley directory** and **CPHI India exhibitor archive** (pharma trade show — companies that paid to exhibit are usually active, not stale)
- **DSIR-recognized R&D units** filtered for Hyderabad — these are companies that actually have an in-house R&D facility, which is a decent proxy for technical orientation
- **ICRA/CRISIL rating reports** — any pharma/chemicals company in Hyderabad that went for a bank credit rating appears in these public reports with their revenue clearly stated
- **Tofler and Zauba Corp** — for MCA-based financial data (most reliable for private companies)
- **Tracxn** — I used this as a starting point but never trusted it alone, especially for revenue

My initial pool was around 80-85 companies that I actually looked at.

---

## The 6-Criteria Check

For each company I went through these six questions:

**C1 – Do they actually make something?**  
I got burned early by companies that say "manufacturer" but are really just trading houses or labs that do testing/analysis. So I started checking: do they mention a physical plant, facility location, production capacity, GMP certification? If the answer is "they provide services," I stopped there.

**C2 – Is the real operation in Hyderabad?**  
Some companies have their registered office in Hyderabad but manufacture in Andhra Pradesh or Gujarat. I flagged those and checked if their actual R&D or main manufacturing is here.

**C3 – Is what they make actually niche?**  
Not "chemicals" but what specifically. n-Butyl lithium is not the same as general industrial chemicals. Equine antivenom is not the same as generic biologics. I looked for things like: regulatory certifications (USFDA, TGA, WHO-GMP), proprietary strains, trademarked products, specific chemistry capabilities.

**C4 – Who's running the company?**  
I checked LinkedIn, company bios, and Zauba Corp director listings. I was looking for: PhD, engineering degree, hands-on founder still active. Where I found just an MBA or a second-gen who inherited the company with no technical background, I downgraded.

**C5 – Is the sector going anywhere?**  
China+1, PLI scheme, Make-in-India for APIs, diagnostics manufacturing push after COVID — I cross-checked whether each company's specific segment had any of these tailwinds working for them.

**C6 – Is there any sign of life?**  
Website updated recently? Hiring for technical roles? Press coverage from 2024-2026? New product launches? If the last news was 2019 and the website copyright says 2022, I moved on.

---

## Where I Auto-Disqualified (Red Lines)

A few things I made hard rules on and did not spend more time researching once I found them:

- **PE/VC majority control** — If a fund holds more than 30-35% and clearly has board control, the company is no longer founder-run by the ICP definition. I caught Suven Pharma here (Advent International, 50.1%, Dec 2022) and Novopor (Bain Capital, June 2023). Both had good products and revenue but failed this check.

- **NCLT proceedings or CRISIL "Issuer Not Cooperating"** — If a company is in creditor trouble, I can't include it no matter how good the technology is. Lazuline Biotech had both NCLT proceedings and a bank auction notice on Canara Bank's website. Removed.

- **Revenue under ~Rs.30Cr** — Several diagnostics companies I found were good on paper but really small. Pariksha Biotech (Rs.9.5Cr), VGS Synthesis (Rs.11.2Cr), Clonz Biotech (Rs.24.4 lakh). The ICP is Rs.50-500Cr, so these don't qualify regardless of technical quality.

- **Founded after 2021** — Not enough track record. Sawin Biomedicals was incorporated January 2023. No.

- **Pure CRO or testing lab** — The assignment specifically warns about this trap. Companies like Vimta Labs (Rs.348Cr revenue, looks big) are actually testing/CRO businesses, not manufacturers. I didn't include them.

---

## Where I Caught AI Hallucinations

I used AI heavily for initial research, but I verified everything that went into the final list. A few cases where the AI got it wrong:

**1. Synergene vs Syngene**  
These names are very similar. Synergene Active Ingredients (Hyderabad, Rs.323Cr, specialty APIs) and Syngene International (Bengaluru, Rs.3,642Cr, large CRO, Biocon subsidiary). I caught the confusion early and kept them clearly separate.

**2. Suven Pharma — described as "founder-run CRAMS company"**  
Technically true until 2022. But Advent International acquired 50.1% in December 2022. The company is no longer promoter-controlled. AI kept presenting it as if Venkateswarlu Jasti still runs it operationally. He doesn't have a controlling stake anymore.

**3. Revenue inflation**  
For private companies, AI tends to pick the highest number from any source. I required at least two independent sources to confirm any revenue figure — Tofler/MCA + ICRA/CRISIL, or tracxn citing MCA + the company's own press. If only one source had a number and it seemed high, I marked it as "estimated" in the CSV.

**4. Lazuline Biotech — presented as "innovative biotech"**  
The technology (recombinant human serum albumin using Pichia pastoris) is genuinely interesting. But CRISIL marked the company as "Issuer Not Cooperating," Canara Bank put up a bank auction notice, and there are NCLT proceedings. Removed.

---

## What I Couldn't Fully Verify

Being honest about the borderline ones:

- **Chembricks Laboratories** — founded 2019, has a Houston US office, works on heterocyclic chemistry. Good signs. But I couldn't find revenue data publicly.
- **Lextro Bio Solutions** — operates from Genome Valley, does recombinant protein work. Website looks serious. But I couldn't confirm the leadership team from public sources.
- **Yapan Bio** — Piramal Pharma holds 27.78%. I included this as borderline because founders still hold majority and Piramal's stake is a strategic partnership, not a PE fund control. Judgment call.

I flagged all of these as "Borderline" in the CSV with specific notes on what I couldn't confirm.

---

## Final Count

80+ companies investigated. ~30% yield as the assignment predicted.
- 8 Strong Fit / Fit with revenue confirmed
- 8 more Fit/Borderline with verified profiles but some uncertainty
- 8 explicitly disqualified with documented reasons

I kept the disqualified companies in the CSV to show the research trail, not just the final list.
