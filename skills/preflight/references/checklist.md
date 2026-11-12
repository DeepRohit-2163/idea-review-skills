# Preflight checklist

Questions per constraint category, each concrete enough to answer yes / no / a number / unknown.
Record per answer: evidence label (verified / secondary / assumption), as-of date, hard or soft,
owner lens. Sources below were collected 2026-10-13. "primary" below means a primary-source URL that has not been re-fetched
for this preflight — fetch it before labelling the claim `verified`. Re-check any legal date
before it drives a decision.

## Contents
1. Desirability / customer
2. Market and timing
3. Technical feasibility
4. Data
5. Regulatory and legal (jurisdiction × sector screen)
6. Financial viability and unit economics
7. Operational
8. Team and founder-personal
9. Ethical and reputational
10. Dependencies and platform risk
- Outside view base rates
- Evidence ladder
- Decision hygiene

---

## 1. Desirability / customer
Owner: `/product-manager` (value risk) · `/product-designer` (usability) · `/design-partner` if B2B pilots
- Can the problem be stated in the buyer's words, from a specific past instance (not "they would")?
- Who is the user, who is the payer, who signs? Are they the same person?
- What does the buyer do about it today — tool, consultant, headcount, spreadsheet, nothing?
- **Existing budget line:** do they already pay for something that does this job, even badly?
  From which budget, at what amount, and what did they spend last year?
- How many people with this problem have you spoken to? Griffin & Hauser (1993): about 20–30
  interviews in a segment surface about 90% of needs; stop when nothing new appears
  ([RePEc](https://ideas.repec.org/a/inm/ormksc/v12y1993i1p1-27.html), secondary — paper figure not verified).
- Highest rung reached on the evidence ladder (below)? Say-level evidence caps at weak.
- Is the idea tech-first ("we have a capability, find a use")? RAND names this a root cause.

## 2. Market and timing
Owner: `/ceo` (thesis, why now) · `/commercial-lead` (ICP, channel)
- **Bottom-up size:** reachable accounts × price you have *evidence* for. Show the working.
  Top-down analyst figures are a cross-check only
  ([TechCrunch 2023](https://techcrunch.com/2023/10/06/how-founders-should-approach-tam-when-venture-capital-is-scarce), secondary).
- Name the first 10 accounts. If you cannot, the market is not yet real to you.
- **Why now:** the single dated change (technology, regulation, cost curve, behaviour) that makes
  this newly possible or urgent. What happens if it reverses?
- Who else sees the same change? Timing risk is everyone seeing it at once.
- Bad timing / macro conditions was a cause in 29% of 2023–2026 VC-backed shutdowns
  ([CB Insights, Mar 2026](https://www.cbinsights.com/research/report/startup-failure-reasons-top/), secondary).
- Is there a schlep (tedious work) that deters competitors — a moat — or that will deter you?
- Five forces: who holds buyer power, supplier power, substitutes?

## 3. Technical feasibility
Owner: `/cto` · `/ai-lead` if models are involved
- Can a working version be built with available skills, time and tech? What is the hardest part,
  and has anyone (including you) built it before?
- Which components are commodity (buy) vs genuinely new (build)?
- For AI: is the problem within what models can do reliably, measured as consistency across
  repeated runs, not a single success? RAND root cause: applying AI to problems too hard for it.
- Cost per completed task at target scale — is it below what the buyer will pay per task?
- What would a two-week spike prove or disprove? Spikes are throwaway.

## 4. Data
Owner: `/cto` (architecture) · `/data-analytics` · `/legal-regulatory-compliance` (lawful basis) · `/security-lead`
- What data does the product need? Do you have it, or can you **legally** obtain it?
  (RAND root cause #2: inadequate data.)
- Does it contain personal, special-category, health, financial or children's data?
- Where will it be stored and processed (residency)? Cross-border transfers?
- Any append-only or immutable store holding personal data? That collides with erasure rights —
  a write-path decision that cannot be retrofitted.
- Is there training-data or scraping exposure (copyright, terms of service)?

## 5. Regulatory and legal (jurisdiction × sector screen)
Owner: `/legal-regulatory-compliance`. Not legal advice — a screen for what needs counsel.
For each target **jurisdiction** × **sector**, mark: applies / may apply / n/a, with the date.

**EU** (as of 2026-10-13)
- AI Act: prohibitions since Feb 2025; GPAI obligations since 2 Aug 2025; Art 50 transparency
  (tell people they are dealing with AI) since 2 Aug 2026. Digital Omnibus on AI moved Annex III
  high-risk obligations to **2 Dec 2027** and Annex I to **2 Aug 2028**
  ([Gibson Dunn](https://www.gibsondunn.com/eu-ai-act-omnibus-agreement-postponed-high-risk-deadlines-and-other-key-changes/), secondary;
  regulation number reported as 2026/1744 by a vendor source — verify on EUR-Lex). Is the use case in Annex III
  (recruitment, credit scoring, education, life/health insurance pricing, …)?
- GDPR: unchanged. The GDPR part of the Digital Omnibus is a **proposal** with no Council mandate
  as of Sept 2026 ([Acompli](https://acompli.ie/news/digital-omnibus-gdpr-cookies-status-september-2026/), secondary).
- Cyber Resilience Act: reporting of exploited vulnerabilities and severe incidents live since
  **11 Sept 2026**; main obligations from 11 Dec 2027
  ([European Commission](https://digital-strategy.ec.europa.eu/en/policies/cra-reporting), primary). Does it ship software (SDK, on-prem agent)?
- EU–US transfers: DPF stands; appeal C-703/25 P pending
  ([DataGuidance](https://www.dataguidance.com/news/eu-cjeu-admits-microsoft-intervener-appeal-concerning), secondary). Keep SCCs as fallback.

**US** (as of 2026-10-13)
- CCPA ADMT obligations from **1 Jan 2027** ([MoFo](https://www.mofo.com/resources/insights/251007-ccpa-regulations-on-cybersecurity-risk-assessments), secondary).
- Colorado AI Act repealed and replaced by SB 26-189 (ADMT transparency), effective **1 Jan 2027**
  ([DWT](https://www.dwt.com/blogs/privacy--security-law-blog/2026/05/colorado-ai-act-repeal-new-transparency-law), secondary).
- Texas TRAIGA effective 1 Jan 2026 ([Latham](https://lw.com/en/insights/texas-signs-responsible-ai-governance-act-into-law), secondary).
- About 19–20 states have comprehensive privacy laws in effect in 2026
  ([IAPP](https://iapp.org/news/a/new-year-new-rules-us-state-privacy-requirements-coming-online-as-2026-begins), secondary).
- Federal preemption of state AI law: executive order plus a **proposal** to Congress, not enacted
  ([Ropes & Gray](https://www.ropesgray.com/en/insights/alerts/2026/03/the-white-house-legislative-recommendations-national-policy-framework-for-artificial-intelligence-an), secondary).
- FTC still pursues false or unsubstantiated AI-capability claims — check your own marketing
  ([Skadden](https://www.skadden.com/insights/publications/2026/02/the-ftc-enters-new-chapter-in-its-approach-to-artificial-intelligence-and-enforcement), secondary).
- COPPA amended rule: full compliance required since 22 Apr 2026
  ([Davis Polk](https://www.davispolk.com/insights/client-update/ftc-prioritizes-coppa-enforcement-new-compliance-obligations-take-effect), secondary).

**UK** — DUAA 2025: new automated-decision regime (Arts 22A–D) since 5 Feb 2026; complaints-handling
duty since 19 June 2026 ([Kennedys](https://www.kennedyslaw.com/en/thought-leadership/article/2026/the-data-use-and-access-act-2025-commencement-dates-and-planned-guidance-for-2026/), secondary).

**India** — DPDP Rules core duties from about May 2027 ([PIB](https://static.pib.gov.in/WriteReadData/specificdocs/documents/2025/nov/doc20251117695301.pdf), primary).
**China** — AI-content labelling rules since 1 Sept 2025 ([White & Case](https://www.whitecase.com/insight-our-thinking/ai-watch-global-regulatory-tracker-china), secondary).

**Sector triggers** — does the idea touch:
- Insurance: NAIC AI Model Bulletin adopted by 25 states plus DC as of 31 Aug 2026; insurers must
  govern third-party AI vendors ([InsureAIWire](https://insureaiwire.com/states/), secondary).
- Financial services, health (HIPAA / medical-device software), employment (bias audits, EU
  Annex III recruitment), children — all `assumption` in the notes; research before relying.

**IP and formation**
- Purely AI-generated work is not copyrightable in the US (*Thaler v. Perlmutter*, cert denied
  2 Mar 2026, [Mayer Brown](https://www.mayerbrown.com/en/insights/publications/2026/03/supreme-court-denies-review-in-ai-authorship-case), secondary). Record human contribution.
- Name: trademark knockout search before public use. Open-source licences (AGPL in SaaS).

## 6. Financial viability and unit economics
Owner: `/finance-lead` · `/ceo` for pricing with `/cpo`
- Price per unit with evidence (a buyer quoted or paid it), not hope.
- Gross margin per unit including inference, hosting, human review and support.
- Customer acquisition cost and payback months, even as a range.
- Cash needed to reach the gate, against the appetite. Unsustainable unit economics was a cause in
  19% of shutdowns; running out of capital the final cause in 70%
  ([CB Insights, Mar 2026](https://www.cbinsights.com/research/report/startup-failure-reasons-top/), secondary).
- Funding route (bootstrap, revenue, angel, VC) — and is taking it a one-way door?

## 7. Operational
Owner: `/coo` · `/devops-platform` · `/customer-success`
- What has to run every day once a customer exists (support, review queues, on-call)? Who does it?
- Any human-in-the-loop step that does not scale? At what volume does it break?
- Required certifications, insurance (professional indemnity), contracts (DPA, MSA)?
- Delivery lead times from suppliers, partners or regulators that set the schedule?

## 8. Team and founder-personal
Owner: `/ceo` (why us, team) · `/legal-regulatory-compliance` (employment contract) · `/finance-lead` (runway)
Check these **before any work on the idea** — several are one-way doors.
- Months of personal runway at zero income. Opportunity cost: salary forgone × expected duration.
- **Current employment contract:** IP-assignment scope (does it cover inventions outside work
  hours, or anything "related to the business"?), moonlighting clause, confidentiality,
  non-solicit, non-compete.
- Has any employer time, device, account or data touched the idea? If yes, stop and get advice.
- **Non-compete law is state / country law.** The FTC's nationwide rule is dead: vacated by a
  Texas court in Aug 2024, and the FTC withdrew its appeals on 5 Sept 2025, moving to case-by-case
  enforcement ([Morgan Lewis](https://www.morganlewis.com/pubs/2025/09/ftc-rule-abandoned-ftc-to-pursue-individual-enforcement-actions), secondary).
  California Labor Code §2870 limits employer claims on own-time inventions unrelated to the
  employer's business ([leginfo](https://leginfo.legislature.ca.gov/faces/codes_displaySection.xhtml?lawCode=LAB&sectionNum=2870), not fetched — verify).
  UK, EU and Indian rules differ. Recommend a one-hour employment-lawyer review.
- Visa status — does it restrict self-employment?
- Spouse / dependants' agreement to the appetite.
- **Why you:** unfair access, insight or credibility in this market. Missing skills and who fills them.

## 9. Ethical and reputational
Owner: `/ceo` · `/legal-regulatory-compliance` · `/security-lead` for misuse
- Who could be harmed if it works as designed? If it fails? If it is misused?
- Does it make decisions about people (credit, insurance, hiring, benefits)? Contestability?
- Would you be comfortable with the product's worst plausible headline?
- Any claim in the pitch that could not be substantiated if a regulator asked?
- Conflicts of interest — commercial relationships that could bias the product's output?

## 10. Dependencies and platform risk
Owner: `/cto` · `/commercial-lead` for channel dependency
- Which single vendor, model provider, API, app store or marketplace is load-bearing? What if it
  changes price, terms or access, or ships the feature itself?
- Is distribution through one channel a platform can switch off?
- Key-person dependencies — one SME, one partner, one customer?
- Pending regulatory or litigation outcomes the plan silently assumes (e.g. a transfer framework, a preemption bill)?

---

## Outside view base rates
Use as directional priors, not precise numbers. Label each exactly as below.

| Source | Finding | Label |
|---|---|---|
| [CB Insights, Mar 2026](https://www.cbinsights.com/research/report/startup-failure-reasons-top/) — 431 VC-backed shutdowns since 2023, reasons for 385, multiple allowed | Ran out of capital 70% (usually the final, not root, cause); poor product-market fit 43%; bad timing / macro 29%; unsustainable unit economics 19% | Observed; strongest of the set |
| [RAND, Aug 2024](https://gradientflow.com/rand-ai-survey/) (summary; primary rand.org RRA2680-1 not fetched) — interviews with 65 data scientists and engineers | More than 80% of AI projects fail, about twice non-AI IT. Root causes: misunderstood problem (most common), inadequate data, tech-first focus, weak infrastructure, problem too hard for AI | Estimate from interviews |
| [Gartner, 25 June 2025](https://www.gartner.com/en/newsroom/press-releases/2025-06-25-gartner-predicts-over-40-percent-of-agentic-ai-projects-will-be-canceled-by-end-of-2027) | Over 40% of agentic AI projects will be cancelled by end-2027 (cost, unclear value, weak risk controls) | **Prediction**, not an observed rate |
| [MIT NANDA, July 2025](https://letsdatascience.com/news/mit-report-documents-genai-pilot-roi-gap-e0924d7d) (preliminary) | About 95% of organisations saw no measurable P&L return from GenAI pilots | **Contested** — narrow failure definition (about 6 months), thin sample ([critique](https://neonvagabond.xyz/mirrors/mit-report-lacks-evidence.html)) |
| [Flyvbjerg](https://blog.ssrn.com/2026/02/09/meet-the-author-bent-flyvbjerg) — database of 16,000+ projects in 136 countries | Most project types, IT included, have fat-tailed outcomes; the mean is a poor forecast | Secondary |

## Evidence ladder
Weakest to strongest. Rungs 1–3 are *say*; 4–9 are *do* (Strategyzer say/do; Mom Test —
[Unusual Ventures](https://www.unusual.vc/rob-fitzpatricks-mom-test/), [Strategyzer](https://strategyzer.com/library/how-strong-is-your-innovation-evidence)).
1. Opinion or compliment — worthless
2. Stated past pain with specifics
3. Evidence of an existing workaround or spend
4. Time commitment (follow-up meeting, beta)
5. Reputation commitment (intro to a decision-maker)
6. Fake-door or landing-page click with an email
7. Concierge or Wizard-of-Oz usage repeated over time
8. LOI, paid pilot or deposit
9. Real sale at the target price

Fluff to discard: generic ("I usually"), future ("I would"), hypothetical ("I might"). Anchor it
by asking for the last specific time it happened. Test choice: fake door retires desirability;
concierge retires value and outcome viability; Wizard of Oz retires usability before feasibility.

## Decision hygiene
- One named decider. A day-0 decision-journal entry with probability estimates.
- Reference class and base rate named. Appetite fixed. Kill criteria dated, review date on the calendar.
- Pre-mortem prospective hindsight raises the *number* of reasons generated by about 30%
  (Mitchell, Russo & Pennington 1989, via [PHF](https://archive.phf.org/resourcestools/Documents/Pre_Mortem_Analysis.pdf), secondary) — volume, not proven accuracy.
- Doors: Type 1 (irreversible) gets slow deliberation; Type 2 gets made fast
  ([Farnam Street on the Bezos 2015 letter](https://fs.blog/reversible-irreversible-decisions/), secondary).
- Kill criteria pre-committed counter sunk cost and identity bias
  ([Annie Duke, Lenny's Newsletter](https://www.lennysnewsletter.com/p/making-better-decisions-annie-duke), secondary).
