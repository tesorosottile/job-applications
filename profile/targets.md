# Target universe (v2)

Rules for scoring and flags live in `filters.yaml`; this file only says **where to look**.
Five role families, weighted equally (CLAUDE.md §3). Within each family, firms are grouped by
location tier so the sweep spends its effort where the score can be highest: Italy (3) →
UK / Nordics / Spain / France (2) → Germany (1) → elsewhere (0, `offList`).

**URL column.** A URL here was verified by a fetch (v1 sweep 2026-09-28, or 2026-10-09 for new
entries). `resolve` means the firm is real but its careers page has not been verified: search
`<firm> careers` / `<firm> lavora con noi`, use a page on the employer's own domain (or its
ATS), and record the working URL in the sweep summary so it can be copied here. Never guess a
URL. Quirks learned the hard way are in the notes; obey them.

Veto freely. A shorter honest list beats a long aspirational one.

---

## mgmt — generalist management / business consulting

### Italy (location 3; Naples/Bari/Palermo and the rest of the South → `south: true`)

| Firm | Careers URL | Notes |
|---|---|---|
| Bip (Business Integration Partners) | https://www.bip-group.com/job-openings | Milan HQ; hubs in Bari (AI lab) and Palermo. Tech-heavy; pick strategy/business roles only. |
| The European House – Ambrosetti (TEHA) | https://www.ambrosetti.eu/en/work-with-us/ | Consulting + think tank + scenarios. Milan/Rome. Also fits `policy`. |
| Value Partners | resolve | Milan strategy boutique. |
| Strategic Management Partners | resolve | ~250 consultants; Milan, Rome and other Italian cities. |
| Impacta Strategy | resolve (Workable: `apply.workable.com/impactastrategy`) | Milan/Rome. Associate roles ask for prior strategy/M&A experience: check seniority. |
| Intellera Consulting | resolve | Public-sector consulting (ex-PwC PA line, Accenture since 2024). Rome/Milan. Also `policy`. |
| Keyone Consulting | resolve (keyoneconsulting.it) | Strategy and subsidised finance; offices in **Naples** (Centro Direzionale) and **Bari**. |
| Protiviti Italia | resolve | Governance/organisation consulting; has posted Junior Consultant roles in **Bari**. |
| Deloitte NextHub (Bari, Naples) | resolve | Southern hubs. Many roles are IT/cyber: keep only business/strategy ones. |
| KPMG Advisory Italy · EY-Parthenon Italy · PwC Strategy& Italy · Deloitte Monitor Italy | resolve | Big 4 strategy arms; Milan/Rome, some Naples/Bari offices. |
| Bain · BCG · McKinsey · Kearney · Oliver Wyman · Roland Berger · Arthur D. Little (Milan/Rome) | see Germany rows for each board | Same global boards; filter to Milan/Rome. Bain's single Associate Consultant req (jobid=10397) covers Milan/Rome. |

### UK / Nordics / Spain / France (location 2; UK → `visa: true`)

| Firm | Careers URL | Notes |
|---|---|---|
| OC&C Strategy Consultants | https://careers.occstrategy.com/vacancies/ | Real closing dates. London Associate Consultant intakes: no language requirement, March start. One stream per applicant. |
| L.E.K. Consulting (London) | https://lek.tal.net/vx/lang-en-GB/mobile-0/appcentre-1/brand-2/candidate/jobboard/vacancy/1/adv/ | Short opp URLs hit a CAPTCHA; the long `xf-` form loads. |
| Baringa | https://www.baringa.com/en/careers/ | Also strong `energy`. Open roles at `/en/careers/experienced/#jobs`; early careers at `/en/careers/early-careers/`. |
| Implement Consulting Group | resolve | Copenhagen/Nordics mid-size management consultancy. |
| Management Solutions | resolve | Madrid-HQ consultancy (strategy, risk, regulation); large graduate intake. |
| Sia Partners · Kea & Partners · Eight Advisory · Advancy | resolve | Paris mid-size consultancies. Usually French required: flag in `why`. |
| Oliver Wyman · Kearney · Simon-Kucher (London, Madrid, Paris, Nordics) | see Germany rows | Same boards. |

### Germany (location 1)

| Firm | Careers URL | Notes |
|---|---|---|
| Bain | https://www.bain.com/careers/find-a-role/ | One global AC requisition (jobid=10397), ~53 offices; language per office, not stated. |
| BCG | https://careers.bcg.com/ | Munich entry route was filled on 2026-09-28. |
| McKinsey | https://www.mckinsey.com/careers/search-jobs | Client-rendered SPA: every job URL renders the landing page, so no McKinsey posting can be link-verified by fetching. Add only with `why` saying "verify in browser". |
| Kearney | https://kearney.taleo.net/careersection/2/jobsearch.ftl | Taleo, JS-only. |
| Oliver Wyman | https://careers.marsh.com/global/en/oliverwyman-search | JS-only. |
| Roland Berger | https://careers.smartrecruiters.com/RolandBerger | |
| Strategy& | https://jobs.strategyand.pwc.de/de/en/search-results | |
| Simon-Kucher | https://simon-kucher.csod.com/ux/ats/careersite/1/home | JS-only; own /careers/jobs 404s. |
| zeb | https://career.zeb-consulting.com/jobs | Real posting dates. Amsterdam roles English-only; German-located roles require C1 German. |
| Stern Stewart | https://www.sternstewart.com/karriere/ | German postings; apply URLs use `-f<id>.html` where the posting uses `-j<id>.html`. |
| Horváth | https://horvath.wd3.myworkdayjobs.com/en-US/Horvath_Careers | |
| Fortlane Partners (ex-goetzpartners) | https://join.fortlane.com/ | Category pages only, no individual vacancies. |
| Arthur D. Little | https://careers-adlittle.icims.com/jobs/search | `?in_iframe=1` REQUIRED on job URLs. Bodies show only the intro blurb. |
| Alvarez & Marsal | https://careers.alvarezandmarsal.com/jobs | Germany filter broken; bodies don't render. |
| EY-Parthenon | https://careers.ey.com/ey/search/ | Real posting dates. German roles require C1 German. |
| Monitor Deloitte | https://jobs.deloitte.de/search/ | |
| Accenture Strategy | https://accenture.wd103.myworkdayjobs.com/AccentureCareers | JS-only listing; individual pages verify fine. |

---

## energy — energy / climate / energy-transition consulting or analysis

### Italy

| Firm | Careers URL | Notes |
|---|---|---|
| Aurora Energy Research (Rome) | https://careers.auroraer.com/ | No posting dates (use sitemap lastmod). Requirements sit in a JD PDF, so language lines aren't in page text → `german: "unverified"` unless the PDF is read. |
| REF-E | resolve (ref-e.com) | Milan energy-market research and advisory; part of the MBS/Cerved group. |
| Elemens | resolve (elemens.it) | Small Milan energy-market consultancy. |
| Althesys | resolve | Energy/utilities strategy and economic research (TEHA group). |
| Agici Finanza d'Impresa | resolve | Milan; renewables, utilities, infrastructure research and consulting. |
| Fichtner Management Consulting Italia | resolve | Milan, <50 staff; strategy for energy players. |
| RSE – Ricerca sul Sistema Energetico | resolve | Milan; public energy research. Hires by *bando*. Also `policy`. |
| CMCC Foundation | resolve | Euro-Mediterranean Center on Climate Change, HQ **Lecce** (`south: true`). Many posts are research/PhD: check seniority. Also `policy`. |
| Enel · Eni · Terna · Edison · A2A · Snam (strategy / scenarios / regulatory teams) | resolve | Corporate strategy and market analysis roles only. |
| Baringa · AFRY · Compass Lexecon energy (Italian offices) | see other rows | |

### UK / Nordics / Spain / France

| Firm | Careers URL | Notes |
|---|---|---|
| Aurora Energy Research (Oxford, London, Madrid, Paris, Stockholm) | https://careers.auroraer.com/ | See above. |
| Baringa | https://www.baringa.com/en/careers/ | |
| Cornwall Insight | resolve | Norwich/London; energy market analysis. |
| Cambridge Econometrics | resolve | Cambridge; energy/climate economic modelling. Also `econ`. |
| LCP Delta | resolve | Energy-transition research and consulting. |
| Ember | resolve | Energy think tank; often remote-friendly. Also `policy`. |
| AFRY Management Consulting | https://afry.com/en/join-us/available-jobs | REF URLs rot fast; use the `fi-fi/smart-recruiters-job/<id>` form. |
| Ea Energy Analyses | https://www.ea-energianalyse.dk/en/we-are-hiring/ | JS-only widget; Jobindex company page is the fallback. |
| THEMA Consulting Group | resolve | Oslo; energy-market consulting. |
| Rystad Energy | resolve | Oslo; energy analytics. Also `analytics`. |
| Gaia Consulting | resolve | Helsinki; energy/climate consulting. |
| E-CUBE Strategy Consultants | resolve | Paris; energy strategy boutique. French likely required. |
| Artelys · Enerdata | resolve | Paris / Grenoble; energy modelling. |
| AleaSoft | resolve | Barcelona; energy-market forecasting. Also `analytics`. |

### Germany

| Firm | Careers URL | Notes |
|---|---|---|
| Guidehouse | https://guidehouse.wd1.myworkdayjobs.com/en-US/External | Workday API 403s; needs a browser pass. Best domain fit seen in v1. |
| Prognos | https://jobs.prognos.com/index | English needs `?persisted_lang=en` or `/en/job.html`. Job pages stay reachable after delisting: ALWAYS cross-check against the index. |
| Energy Brainpool | https://energybrainpool.com/en/jobs | robots-blocked. |
| Consentec | https://consentec.de/en/careers/ | No board; speculative only. |
| r2b energy consulting | https://www.r2b-energy.com/karriere/ | |
| Enervis | https://enervis.de/jobs-liste | |
| Compass Lexecon energy practice | https://fticonsulting.wd108.myworkdayjobs.com/CompassLexeconCareers/ | Old Lever board is stale; use Workday. |
| Agora Think Tanks | https://agora-thinktanks.jobs.personio.com/ | Personio XML gives exact dates. Postings often English-only. Also `policy`. |

---

## econ — economic consulting (competition, regulatory)

### Italy

| Firm | Careers URL | Notes |
|---|---|---|
| Lear (Laboratorio di Economia, Antitrust, Regolamentazione) | https://www.learlab.com/careers/ | Rome competition-economics boutique. Posts vacancies as news items (e.g. "Lear is looking for an Economist", 2026-07-09). Fluent Italian + English. |
| Compass Lexecon (Milan, Rome) | https://fticonsulting.wd108.myworkdayjobs.com/CompassLexeconCareers/ | Milan since 2021, Rome since 2025. Analyst intake runs on cycles (responses Nov / Apr). |
| The Brattle Group (Rome) | https://job-boards.greenhouse.io/thebrattlegroup | Greenhouse. Rome often only has a talent-network form, which isn't a posting. |
| NERA (Rome) | https://careers.marsh.com/global/en/nera-search | JS-only Marsh portal. |
| Prometeia | resolve (prometeia.com/en/careers redirects to `/en/careers/our-tribe`, which renders empty to a fetcher) | Bologna/Milan/Rome. Economic research, forecasting, risk analytics. Also `analytics`. |
| Nomisma | resolve | Bologna economic research and consulting. |
| Openeconomics | resolve | Rome; economic impact assessment. |

### UK / Nordics / Spain / France

| Firm | Careers URL | Notes |
|---|---|---|
| Charles River Associates | https://job-boards.greenhouse.io/charlesriverassociates | Best-yielding board in v1. Watch cohort-gated "20XX graduates" reqs. |
| Analysis Group | https://analystcareers-analysisgroup.icims.com/jobs/search | Job bodies need `?in_iframe=1`. |
| RBB Economics | https://www.rbbecon.com/careers/ | One Cezanne URL for all offices; portal 403s to bots. |
| Oxera | https://careers.oxera.com/jobs | |
| Frontier Economics | https://frontiereconomics.wd3.myworkdayjobs.com/Frontier_Economics_Careers | Office-language fluency required EXCEPT Brussels. London/Madrid also worth checking. |
| Cornerstone Research | https://www.cornerstone.com/careers/ | iCIMS portals robots-blocked; needs a browser pass. |
| Copenhagen Economics | https://copenhagen-economics.jobs.personio.de/ | Often only "Unsolicited application". Ignore the stale /careers/vacancies page. |
| Economic Insight | https://www.economic-insight.com/careers/ | |
| Europe Economics · Cebr · Grant Thornton Economics (London) | resolve | |
| Menon Economics · Oslo Economics | resolve | Norway. |
| Afi – Analistas Financieros Internacionales | resolve | Madrid economic and financial consulting. |
| Compass Lexecon · NERA · Brattle (Madrid, Paris) | see rows above | |

### Germany

| Firm | Careers URL | Notes |
|---|---|---|
| DIW Econ | https://diw-econ.de/en/career/ | Senior categories need very good German. Apply by email. |
| E.CA Economics | https://e-ca.jobs.personio.de/ | |
| Keystone Strategy | https://job-boards.greenhouse.io/keystonestrategy | |
| Deloitte (Economic Advisory / Transfer Pricing) | https://jobs.deloitte.de/search/ | Deloitte UK Economic Advisory: https://apply.deloitte.co.uk/UKCareers/ (robots-blocked; "Economic Masters Graduate" req 21367 seen in v1, needs a browser check). |
| KPMG Economics · PwC Strategy & Economics · EY Economic Advisory | resolve | v1 found no working German boards. |

---

## policy — think tanks, EU institutions, international organisations

### Italy

| Organisation | Careers URL | Notes |
|---|---|---|
| SRM – Studi e Ricerche per il Mezzogiorno | none (no careers page; sr-m.it) | **Naples** (`south: true`), Intesa Sanpaolo research centre on the Southern economy, maritime, energy & Med. No vacancy page. Track for news/"Meets4Future" only; rows only if a real posting appears. |
| SVIMEZ | resolve (svimez.info redirects to `lnx.svimez.info/svimez/`) | Rome; Southern-Italy development think tank. |
| Banca d'Italia | resolve | Rome; hires by public competition (*concorso*); economist entry grades. |
| Cassa Depositi e Prestiti (CDP) – research/strategy | resolve | Rome. |
| ISTAT · Invitalia · ARERA (energy regulator) · AGCM (competition authority) | resolve | Rome/Milan; mostly *concorsi*. AGCM also fits `econ`, ARERA fits `energy`. |
| FEEM – Fondazione Eni Enrico Mattei · EIEE (RFF-CMCC) | resolve | Milan; energy/climate economics. Research posts: check seniority. |
| ISPI · IAI (Istituto Affari Internazionali) | resolve | Milan / Rome. |
| European Commission JRC Ispra | https://recruitment.jrc.ec.europa.eu/ | See JRC below; Ispra is in Italy (location 3). |
| The European House – Ambrosetti · Intellera | see `mgmt` | |

### UK / Nordics / Spain / France

| Organisation | Careers URL | Notes |
|---|---|---|
| European Commission JRC (Seville) | https://recruitment.jrc.ec.europa.eu/ | JSON API with exact dates; English-only C1 roles. Needs prior EPSO CAST FG IV / JRC call registration: that's the real lead time. |
| EBRD (London) | https://jobs.ebrd.com/ | International organisation; arranges immigration itself → London roles are `visa: false`. |
| OECD · IEA (Paris) | https://careers.smartrecruiters.com/OECD · https://careers.smartrecruiters.com/OECD/iea | Every OECD post requires English + good French: flag in `why`. |
| Fedea · Elcano Royal Institute · EsadeEcPol | resolve | Spain. |
| I4CE · IDDRI · Institut Montaigne | resolve | Paris; climate economics / policy. French usually needed. |
| Resolution Foundation · IFS · Institute for Government · NIESR · E3G · Carbon Trust | resolve | London. |
| Nordic Energy Research · Nordic Council of Ministers | resolve | Oslo / Copenhagen. |

### Germany

| Organisation | Careers URL | Notes |
|---|---|---|
| Agora Think Tanks | https://agora-thinktanks.jobs.personio.com/ | English-only postings are common. |
| ifo Institut | https://www.ifo.de/en/career-ifo | Researcher posts are PhD/postdoc: usually seniority 0. |
| ZEW Mannheim | https://www.zew.de/en/career/job-offers | JS-only. |
| DIW Berlin | https://www.diw.de/en/diw_01.c.618535.en/careers/job_offers.html | |
| IW Köln | https://www.iwkoeln.de/institut/karriere.html | German-only. |
| RWI Essen | https://www.rwi-essen.de/en/rwi/career/jobs | |
| Öko-Institut | https://www.oeko.de/das-institut/stellenangebote/ | Softgarden board carries a dead Lorem-ipsum listing: ignore it. |
| Fraunhofer ISI | https://jobs.fraunhofer.de/ | |

### Elsewhere (location 0, `offList`; Brussels and Luxembourg land here under current rules)

| Organisation | Careers URL | Notes |
|---|---|---|
| EU Careers / EPSO (DG COMP, DG ENER, …) | https://eu-careers.europa.eu/en/job-opportunities | DG COMP Case Handler AD5 is the genuine entry grade. Blue Book traineeship next ~March 2027. |
| ACER (Ljubljana) | https://www.acer.europa.eu/the-agency/careers | Standing Graduate Programme (no deadline), EU energy regulation, English. |
| EIB / EIF (Luxembourg) | https://erecruitment.eib.org/ | Cookie wall; JS-only. |
| Bruegel (Brussels) | https://www.bruegel.org/careers | |
| IRENA · World Bank | https://eexh.fa.em3.oraclecloud.com/hcmUI/CandidateExperience/en/sites/CX_1/jobs · https://worldbankgroup.csod.com/ | Structurally low yield; check monthly at most. |

---

## analytics — data / analytics / economist roles in industry

### Italy

| Firm | Careers URL | Notes |
|---|---|---|
| Prometeia | see `econ` | |
| CRIF | resolve | Bologna; credit and economic analytics. |
| Cerved | resolve | Milan/Rome; data and analytics, ratings. |
| Intesa Sanpaolo Research Department · UniCredit Economics | resolve | Milan (Intesa also Naples via SRM). |
| Generali (Trieste) · Moltiply · Octopus Energy Italy (energy markets analyst) | resolve | Analyst/economist roles only. |
| Bip / Deloitte / Accenture data & analytics hubs (Naples, Bari) | see `mgmt` | Keep business-analytics roles; drop pure engineering. |

### UK / Nordics / Spain / France

| Firm | Careers URL | Notes |
|---|---|---|
| QuantCo (London) | https://jobs.lever.co/quantco- | Trailing hyphen in the slug. English-only, names causal inference, no PhD needed. |
| Booking.com (Amsterdam = offList) | https://jobs.booking.com/booking/jobs | Client-side. |
| Amazon EU Economics | https://www.amazon.jobs/en/job_categories/economics | Posts in bursts; was US-only on 2026-09-28. |
| Rystad Energy · AleaSoft | see `energy` | |

### Germany

| Firm | Careers URL | Notes |
|---|---|---|
| QuantCo (Munich, Berlin) | https://jobs.lever.co/quantco- | |
| Capgemini Invent | https://job-boards.eu.greenhouse.io/capgeminideutschlandgmbh | Board-wide "German and English C1" clause. |
| Zalando | https://jobs.zalando.com/en/jobs/ | |
| Delivery Hero | https://careers.deliveryhero.com/ | /jobs robots-blocked; individual `/job/<slug>-jid-<n>` pages fetch. Watch for a repost of the in-house consulting analyst role. |
| Lufthansa Industry Solutions | https://lufthansagroup.careers/en/lufthansa-industry-solutions | Use apply.lufthansagroup.careers for individual jobs. |
| Allianz · Munich Re · Siemens · BMW Group · Everllence (ex-MAN Energy Solutions) · Stadtwerke München | see v1 notes in `archive/profile/targets-resolved.yaml` | Mostly JS-only; economic research / strategy roles only. |

---

## Aggregators (supplementary; company pages stay primary)

| Source | URL | Notes |
|---|---|---|
| EuroBrussels | https://www.eurobrussels.com/ | Most productive aggregator in v1. Feeds: Economist, Energy, Consultancy, 0-2 Years. |
| INOMICS | https://inomics.com/jobs | Search ignores the query for fetchers; page manually. Mostly academic. |
| EconJobMarket | https://econjobmarket.org/positions | Mostly academic. |
| Indeed Italia | https://it.indeed.com/ | Queries such as "junior consultant Napoli", "analista energia Milano". Rate-limits quickly. |
| Bocconi Job Gate · Politecnico di Milano career service | resolve | Italian energy and consulting firms post graduate roles here. May need login: skip if so. |
| ACER Graduate Programme | see `policy` | Rolling route, not a weekly item. |

Zero coverage in v1 (robots/proxy-blocked): Stepstone, Absolventa, LinkedIn. LinkedIn postings
come in only via **+ Posting** on the dashboard.

Dropped from v1 as dead ends (not for being German): Vivid Economics (absorbed into McKinsey),
Positive Agenda Advisory (no careers page), Lexonomics (firm unconfirmed), Trinomics (stale
board, open CVs only), RES vacancies (not a job board), EURAXESS (doctoral only, unfilterable),
UnternehmerTUM (no analyst roles).
