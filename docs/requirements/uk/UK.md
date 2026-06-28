# United Kingdom Critical Systems and Crown Jewels Requirements for Post-Quantum Cryptography Migration — Authoritative Source Reference

## TL;DR
- **The UK's PQC migration is anchored by the NCSC guidance "Timelines for migration to post-quantum cryptography" (published 20 March 2025, v1.0), which sets three hard milestones — by 2028 (define goals, complete a full discovery exercise, build an initial plan); by 2031 (complete highest-priority migrations, refine the roadmap); and by 2035 (complete migration of all systems, services and products).** NCSC endorses the NIST standards ML-KEM (FIPS 203), ML-DSA (FIPS 204) and SLH-DSA (FIPS 205), specifically recommends **ML-KEM-768 and ML-DSA-65** for most use cases, and treats hybrid PQ/T schemes as an *interim measure only*.
- **The UK deliberately runs NO centrally-designated "high value asset" list like the US.** It uses an outcomes-based, risk-based model built on the NCSC Cyber Assessment Framework (CAF v4.0), the Network and Information Systems Regulations 2018 (being reformed/expanded by the Cyber Security and Resilience Bill, introduced to Parliament 12 November 2025), and the NPSA's 13 Critical National Infrastructure sectors.
- **"Crown jewels"/critical assets is an official NCSC concept** used in supply-chain and board governance guidance for asset prioritisation; it is the UK functional analogue of the US OMB High Value Asset program (M-19-03) and conceptually parallels EU NIS2's "essential" vs "important" entities — but in the UK, prioritisation is devolved to organisations and Lead Government Departments rather than a central registry.

Every URL below points to a specific official publication. Non-official sources are explicitly flagged.

---

## Key Findings

### 1. NCSC Post-Quantum Cryptography Guidance

**1a. Preparing for Quantum-Safe Cryptography (white paper)**
- **Publisher / date:** NCSC; originally published 2020.
- **URL:** https://www.ncsc.gov.uk/whitepaper/preparing-for-quantum-safe-cryptography (PDF: https://www.ncsc.gov.uk/pdfs/whitepaper/preparing-for-quantum-safe-cryptography.pdf)
- **Key content:** Sets out the NCSC position on mitigating the threat to cryptography posed by developments in quantum computing, to help technical policymakers prepare for quantum-safe cryptography. States the best mitigation against the quantum threat to traditional public-key cryptography (PKC) is post-quantum cryptography (PQC). It replaces the earlier NCSC white paper on quantum-safe cryptography.

**1b. Next steps in preparing for post-quantum cryptography (white paper)**
- **Publisher / date / version:** NCSC; originally published November 2023; updated 14 August 2024 to **Version 2.0** to reflect NIST's publication of three algorithm standards.
- **URL:** https://www.ncsc.gov.uk/whitepaper/next-steps-preparing-for-post-quantum-cryptography (alternate canonical: https://www.ncsc.gov.uk/paper/next-steps-in-preparing-for-post-quantum-cryptography; PDF: https://www.ncsc.gov.uk/sites/default/files/pdfs/publication/next-steps-preparing-for-post-quantum-cryptography.pdf)
- **Recommended algorithms (verbatim table content):** ML-KEM (NIST FIPS 203) for key establishment; ML-DSA (NIST FIPS 204) for general-purpose digital signatures; SLH-DSA (NIST FIPS 205), LMS and XMSS (NIST SP 800-208) for use cases "such as signing firmware and software."
- **Parameter-set recommendation (verbatim):** "ML-KEM and ML-DSA are algorithms suitable for general purpose use. The NCSC recommends ML-KEM-768 and ML-DSA-65 as providing appropriate levels of security and efficiency for most use cases." All proposed parameter sets "provide an acceptable level of security for personal, enterprise and OFFICIAL-tier government information." Smaller parameter sets may be used in constrained devices; the highest security level may suit long-lived/highly sensitive keys.
- **Hybrid (PQ/T) position (verbatim):** "If a PQ/T hybrid scheme is chosen, the NCSC recommends it is used as an interim measure, and it should be used within a flexible framework that enables a straightforward migration to PQC-only in the future." For PKI: "This additional complexity and the difficulty in migrating PKIs mean that a single migration to a fully post-quantum PKI is preferred to adopting an intermediate PQ/T hybrid PKI." The only valid reasons NCSC gives for hybrid are interoperability, implementation security, and protocol/system constraints. NCSC also notes there is "not yet guidance or a consensus" on hybrid schemes for authentication.

**1c. Timelines for migration to post-quantum cryptography (guidance) — the canonical milestone source**
- **Publisher / date / version:** NCSC; published and reviewed **20 March 2025**, Version 1.0.
- **URL:** https://www.ncsc.gov.uk/guidance/pqc-migration-timelines (PDF: https://www.ncsc.gov.uk/sites/default/files/pdfs/publication/pqc-migration-timelines.pdf; timeline infographic: https://www.ncsc.gov.uk/sites/default/files/documents/NCSC-PQC-timeline.pdf)
- **Exact milestones (verbatim from the page):**
  - **By 2028** — "Define your migration goals; Carry out a full discovery exercise (assessing your estate to understand which services and infrastructure that depend on cryptography need to be upgraded to PQC); Build an initial plan for migration." (Activities table: "Complete the discovery and assessment phase. Create an initial migration plan… Communicate your needs to your suppliers.")
  - **By 2031** — "Carry out your early, highest-priority PQC migration activities; Refine your plan so that you have a thorough roadmap for completing migration." (Activities table: "Complete your highest priority migration activities to protect your most critical assets. Ready your infrastructure to support a PQC future…")
  - **By 2035** — "Complete migration to PQC of all your systems, services and products." (Activities table: "…taking the opportunity to build more robust general cyber resilience into your systems.")
- **Rationale for the 2035 endpoint (verbatim):** "The NCSC believes that 10 years is a sufficient period for a rich set of PQC standards to appear, for an ecosystem of products that uses them to be developed, and for uptake to become widespread… This leads to a target date of 2035 for completing migration to post-quantum cryptography."
- **Audience:** "primarily aimed at technical decision-makers and risk owners of large organisations, operators of critical national infrastructure (CNI) systems including industrial control systems (ICS), and companies that have bespoke IT."
- **Crypto-agility (verbatim):** "you should therefore seek solutions that offer cryptographic agility; that is, the ability to readily support alternative suites of cryptographic algorithms."
- **Standards maturity (verbatim):** "During 2025, we expect to see the first cryptographic modules validated to FIPS 140-3 under the NIST's Cryptographic Module Validation Program." (This was realised in 2025 — e.g., Amazon's AWS-LC FIPS 3.0 became the first open-source cryptographic module to provide post-quantum (ML-KEM) support within the FIPS boundary, per the AWS Security Blog — a *non-government* corroborating source.) TLS standardisation within the IETF is expected "around 2027"; SDO standards for TPMs, X.509 PKI certificates, UEFI Secure Boot and 6G "by 2028."
- **Named spokesperson (for context, from the NCSC press release https://www.ncsc.gov.uk/news/pqc-migration-roadmap-unveiled):** NCSC Chief Technical Officer Ollie Whitehouse: "Quantum computing is set to revolutionise technology, but it also poses significant risks to current encryption methods… As quantum technology advances, upgrading our collective security is not just important – it's essential."
- **Companion blog:** "Setting direction for the UK's migration to post-quantum cryptography" (20 March 2025): https://www.ncsc.gov.uk/blog-post/setting-direction-uk-migration-to-pqc

**1d. Quantum security technologies (white paper)**
- **URL:** https://www.ncsc.gov.uk/whitepaper/quantum-security-technologies — sets out NCSC's position on Quantum Key Distribution (QKD) and Quantum Random Number Generation; NCSC does not endorse QKD for any government or military applications.

---

### 2. UK Cyber Assessment Framework (CAF)

- **Publisher:** NCSC. **Collection:** https://www.ncsc.gov.uk/collection/cyber-assessment-framework | **Introduction:** https://www.ncsc.gov.uk/collection/cyber-assessment-framework/introduction-to-caf
- **Current version:** **CAF v4.0** (PDF: https://www.ncsc.gov.uk/files/NCSC-Cyber-Assessment-Framework-4.0.pdf). All versions are on the Changelog page within the collection.
- **Four objectives and 14 principles:**
  - **Objective A — Managing security risk:** A1 Governance, A2 Risk management, A3 Asset management, A4 Supply chain.
  - **Objective B — Protecting against cyber attack:** B1 Service protection policies, processes and procedures; B2 Identity and access control; B3 Data security; B4 System security; B5 Resilient networks and systems; B6 Staff awareness and training.
  - **Objective C — Detecting cyber security events:** C1 Security monitoring; C2 Threat hunting / proactive event discovery.
  - **Objective D — Minimising the impact of cyber security incidents:** D1 Response and recovery planning; D2 Lessons learned.
- **Structure:** objectives → principles → contributing outcomes → Indicators of Good Practice (IGPs). Written "in terms of outcomes, i.e. specification of what needs to be achieved rather than a checklist of what needs to be done."
- **"Essential function":** CAF is "aimed at helping an organisation achieve and demonstrate an appropriate level of cyber resilience in relation to certain specified vitally important functions… functions that are at risk of disruption as a result of a serious cyber incident." Asset identification/prioritisation runs primarily through Objective A (A3 Asset Management).
- **CAF Profiles:** A CAF Profile is "a target level for cyber security and resilience in response to threat actors with a particular level of attack capability." Two types — **Basic** (all sectors, common attacks) and **Enhanced** (sector-specific; for higher-threat contexts such as government CNI, large PII datasets and national-security functions).
- **GovAssure / central government use:** CAF is the assurance framework for government, with government-specific CAF profiles agreed by the Government Security Group, NCSC and CDDO; access to the two GovAssure CAF profiles is via signed-in access at security.gov.uk. Official overview: https://www.security.gov.uk/policy-and-guidance/introduction-to-the-cyber-assessment-framework-caf/

---

### 3. UK NIS Regulations and Successor Legislation

**3a. Network and Information Systems Regulations 2018**
- **Legislation:** https://www.legislation.gov.uk/uksi/2018/506 (SI 2018/506). Laid 20 April 2018; in force **10 May 2018**. GOV.UK collection: https://www.gov.uk/government/collections/nis-directive-and-nis-regulations-2018
- **Definitions / roles (from the legislation text):** "OES" = operator of an essential service (deemed/designated under regulation 8). "RDSP" = relevant digital service provider (regulation 1(3)(e)) — online search engines, online marketplaces, cloud computing services (micro/small enterprises generally exempt). Essential-service sectors: transport, energy, drinking water, health, digital infrastructure. **Competent authorities** enforce sector-by-sector; the **NCSC is the Single Point of Contact and the CSIRT**. OESs must notify the designated competent authority of a significant NIS incident "no later than 72 hours after the operator is aware that a NIS incident has occurred."

**3b. Cyber Security and Resilience (Network and Information Systems) Bill**
- **GOV.UK collection:** https://www.gov.uk/government/collections/cyber-security-and-resilience-bill | **Policy statement (April 2025):** https://www.gov.uk/government/publications/cyber-security-and-resilience-bill-policy-statement/cyber-security-and-resilience-bill-policy-statement | **Parliament Bill page:** https://bills.parliament.uk/bills/4035 | **Summary factsheet:** https://www.gov.uk/government/publications/cyber-security-and-resilience-network-and-information-systems-bill-factsheets/summary-of-the-bill | **NCSC blog:** https://www.ncsc.gov.uk/blog-post/cyber-security-resilience-bill-policy-statement
- **Status:** Introduced to Parliament (first reading) **12 November 2025**; second reading **6 January 2026**; the Public Bill Committee was expected to conclude by early March 2026 (per the DSIT Impact Assessment), with subsequent Commons stages through 2026.
- **Scope / effect:** Reforms and adds to the NIS Regulations 2018 — brings data centres (classed as essential services, with data infrastructure as a NIS sector), Managed Service Providers (MSPs) and critical suppliers into scope; strengthens regulator powers; expands and accelerates incident reporting; gives the Secretary of State powers (including a statement of strategic priorities and powers of direction) to update the regime via secondary legislation; aligns where appropriate with EU NIS2. It puts NCSC CAF principles "on a firmer footing."
- **Scale (from DSIT's 12 Nov 2025 Impact Assessment, https://publications.parliament.uk/pa/bills/cbill/59-01/0329/impact_assessment.pdf):** the UK has roughly **12,867 active MSPs**, of which an estimated further **900–1,100 medium/large MSPs (RMSPs)** are brought into scope; data-centre thresholds (≥1 MW; enterprise ≥10 MW) and large load controllers (≥300 MW) are also captured.
- **Penalties (from the DSIT enforcement factsheet, 12 Nov 2025):** a two-band regime — standard breaches up to the greater of **£10m or 2%** of worldwide turnover; serious breaches up to the greater of **£17m or 4%**; failure to comply with national-security directions up to the greater of **£17m or 10%**; plus daily fines up to **£100,000** for continuing contraventions. (Precise turnover definitions to be set in secondary legislation.)

---

### 4. Critical National Infrastructure (CNI)

- **Publisher:** NPSA — National Protective Security Authority (successor to CPNI; part of MI5; the UK's National Technical Authority for physical and personnel protective security). **CNI page:** https://www.npsa.gov.uk/about-npsa/critical-national-infrastructure | **FAQ:** https://www.npsa.gov.uk/frequently-asked-questions-0 | **About:** https://www.npsa.gov.uk/about-npsa
- **The 13 CNI sectors (verbatim):** "Chemicals, Civil Nuclear, Communications, Defence, Emergency Services, Energy, Finance, Food, Government, Health, Space, Transport and Water." Several have sub-sectors (e.g., Emergency Services = police, fire and rescue, ambulance, coastguard). Each sector has one or more Lead Government Departments (LGDs).
- **Official UK Government definition of CNI (verbatim):** "Those critical elements of infrastructure (namely assets, facilities, systems, networks or processes and the essential workers that operate and facilitate them), the loss or compromise of which could result in: a) Major detrimental impact on the availability, integrity or delivery of essential services — including those services whose integrity, if compromised, could result in significant loss of life or casualties — taking into account significant economic or social impacts; and/or b) Significant impact on national security, national defence, or the functioning of the state."
- **The "criticalities process":** LGDs, working with industry, categorise asset criticality; those meeting certain criteria are designated CNI. (Notably, the Food sector "has no individual assets which are designated at CNI" owing to its inherent resilience.)
- **"Crown jewels" / critical assets (official NCSC/NPSA usage):**
  - NCSC, "Stage 2a: Prioritise your organisation's 'crown jewels'": https://www.ncsc.gov.uk/collection/assess-supply-chain-cyber-security/stage-2-develop-an-approach/stage-2a-prioritise-your-crown-jewels — "Determine the critical aspects in your organisation that you need to protect the most (your 'crown jewels'), taking into consideration potential threats, vulnerabilities, impact and your organisation's risk appetite."
  - NCSC Board Toolkit, "Identifying the critical assets in your organisation": https://www.ncsc.gov.uk/collection/board-toolkit/principle-a-risk-management/identifying-the-critical-assets-in-your-organisation — frames "crown jewels (ie the things most valuable to your organisation)."
  - NPSA, "Identify your Most Valuable Assets": https://www.npsa.gov.uk/security-best-practices/passport-good-security/identify-your-most-valuable-assets

---

### 5. UK Cyber Security Strategy

- **Government Cyber Security Strategy 2022 to 2030:** https://www.gov.uk/government/publications/government-cyber-security-strategy-2022-to-2030 (HTML: https://www.gov.uk/government/publications/government-cyber-security-strategy-2022-to-2030/government-cyber-security-strategy-2022-to-2030-html). Published **25 January 2022**. Two complementary pillars: **Pillar 1 — build organisational cyber resilience**; **Pillar 2 — "defend as one."** Adopts the NCSC CAF "as the assurance framework for government," with tiered government CAF profiles; notes that NIST CSF and ISO 27001 "are consistent with the CAF." Five underpinning objectives mirror CAF (manage risk; protect; detect; minimise impact; plus cross-government working).
- **National Cyber Strategy 2022:** https://www.gov.uk/government/publications/national-cyber-strategy-2022 (HTML: https://www.gov.uk/government/publications/national-cyber-strategy-2022/national-cyber-security-strategy-2022). Five pillars: (1) strengthening the UK cyber ecosystem; (2) building a resilient and prosperous digital UK; (3) taking the lead in vital technologies; (4) advancing UK global leadership; (5) detecting, disrupting and deterring adversaries. Centred on the concept of "cyber power."
- **Update (important):** The **Government Cyber Action Plan** (published **6 January 2026**: https://www.gov.uk/government/publications/government-cyber-action-plan/government-cyber-action-plan) supersedes the strategy's delivery detail and states the 2030 target "for all government organisations to be resilient to known vulnerabilities and attack methods is not achievable by the original target date of 2030," moving to a more centralised, CAF/GovAssure-driven model.

---

### 6. NCSC General Guidance (supporting the document)

- **10 Steps to Cyber Security:** https://www.ncsc.gov.uk/collection/10-steps (published 11 May 2021). Ten components: Risk management; Engagement and training; Asset management; Architecture and configuration; Vulnerability management; Identity and access management; Data security; Logging and monitoring; Incident management; Supply chain security.
- **Cyber Essentials:** https://www.ncsc.gov.uk/cyberessentials/overview — five technical controls: **firewalls; secure configuration; user access control; malware protection; security update management.** Requirements doc v3.2: https://www.ncsc.gov.uk/files/cyber-essentials-requirements-for-it-infrastructure-v3-2.pdf
- **Supply chain security — 12 principles:** https://www.ncsc.gov.uk/collection/supply-chain-security/principles-supply-chain-security (collection: https://www.ncsc.gov.uk/collection/supply-chain-security). Grouped into four stages: understand the risks; establish control; check your arrangements; continuous improvement.
- **Cloud security — 14 Cloud Security Principles:** https://www.ncsc.gov.uk/collection/cloud/the-cloud-security-principles — applies to cloud platforms and SaaS; covers data-in-transit protection, asset protection/resilience, separation, governance, supply-chain security, identity and authentication, audit, and secure use.
- **Operational Technology (OT) / ICS:** "Secure connectivity principles for Operational Technology (OT)" — NCSC-led international guidance (January 2026): https://www.ncsc.gov.uk/files/ncsc-secure-connectivity-for-operational-technology.pdf — eight goal-oriented principles, produced with CISA, FBI, ASD's ACSC, the Canadian Cyber Centre, Germany's BSI, NCSC-NL and NCSC-NZ. Complemented by CISA/NCSC OT-architecture asset-visibility guidance (September 2025: https://www.cisa.gov/news-events/alerts/2025/09/29/cisa-and-uk-ncsc-release-joint-guidance-securing-ot-systems).
- **PKI / trust anchors / root keys:** NCSC "In-house public key infrastructure" collection: https://www.ncsc.gov.uk/collection/in-house-public-key-infrastructure/introduction-to-public-key-infrastructure (the PQC timelines page details enterprise-PKI migration: new PQC root-of-trust, cross-signing, staged certificate issuance).

---

### 7. Standards Relationships

- **ISO/IEC 27001:2022 (ISMS):** Official ISO page: https://www.iso.org/standard/27001. Jointly published by ISO and IEC (under ISO/IEC JTC 1, Subcommittee SC 27). The "world's best-known standard for information security management systems." Transition to the 2022 edition required by 31 October 2025. Relevant to UK cyber resilience as a recognised ISMS standard that NCSC/GCSS treat as consistent with CAF.
- **IEC 62443 / ISA-IEC 62443 (IACS / OT security):** Official IEC publication page (e.g., IEC 62443-2-1:2024): https://webstore.iec.ch/en/publication/62883. Series developed jointly by the IEC (TC 65/WG 10) and ISA (ISA99); recognised by the IEC as a *horizontal* standard in 2021. Uses a risk-based approach with the "zones and conduits" model and Security Levels — directly relevant to OT/ICS PQC migration where long asset lifecycles and legacy protocols dominate.
- **CAF ↔ standards mapping:** The Government Cyber Security Strategy explicitly states NIST CSF and ISO 27001 are consistent with CAF. Official GOV.UK mapping (cyber governance code → NCSC CAF): https://www.gov.uk/government/publications/cyber-governance-mapping/mapping-cyber-governance-code-to-ncsc-cyber-assessment-framework. *(Note: a detailed CAF-to-IEC-62443 mapping for ICS/OT exists via the industry ICS Community of Interest (ICS COI), but this is **not an official NCSC document** — it carries an explicit disclaimer that "no formal review of this guidance article has been undertaken by the NCSC.")*

---

### 8. Comparative Context

- **US OMB High Value Assets (HVA):** OMB Memorandum **M-19-03**, "Strengthening the Cybersecurity of Federal Agencies by Enhancing the High Value Asset Program" (10 December 2018): https://www.whitehouse.gov/wp-content/uploads/2018/12/M-19-03.pdf. Establishes three HVA designation categories — **Informational Value, Mission Essential, and Federal Civilian Enterprise Essential (FCEE)** — and consolidates/rescinds the earlier M-16-04 and M-17-09. (HVAs are reported to CISA/DHS and assessed/remediated centrally — a prescriptive, designated-asset model. The June 2026 White House PQC executive order, "Securing the Nation Against Advanced Cryptographic Attacks," further ties HVAs to PQC migration deadlines.)
- **EU NIS2 Directive (Directive (EU) 2022/2555):** Official text on EUR-Lex (https://eur-lex.europa.eu, CELEX 32022L2555). Distinguishes **essential entities** (proactive/ex-ante supervision; administrative fines up to €10m or 2% of total worldwide annual turnover) from **important entities** (ex-post supervision; up to €7m or 1.4%). Covers 18 sectors across Annex I (high criticality) and Annex II (other critical sectors); classification is driven by sector + size thresholds. Enforceable from 18 October 2024. (ENISA provides implementation guidance.)

| Dimension | UK | US | EU |
|---|---|---|---|
| Core construct | Essential functions / CNI / "crown jewels" | Designated High Value Assets (HVAs) | Essential vs Important entities |
| Designation model | Risk/outcomes-based; devolved to orgs + LGDs | Centrally designated & reported to CISA | Size + sector thresholds; self-identification |
| Anchor instrument | CAF + NIS Regs 2018 / CSR Bill | OMB M-19-03 | Directive (EU) 2022/2555 |
| PQC end-state | 2035 (all systems) | HVA/high-impact deadlines (e.g., 2031 for signatures, per 2026 EO) | Member-state roadmaps toward 2035 |

---

### 9. Why the UK Has No Formal HVA Program

The UK's approach is **risk-based and outcomes-focused by design**, in contrast to the US's prescriptive, centrally-designated asset list. The authoritative framing:
- **CAF is outcome-based, not a checklist:** the Introduction to CAF states the principles are "written in terms of outcomes, i.e. specification of what needs to be achieved rather than a checklist of what needs to be done," and CAF was built "to maintain the outcome-focused approach of the NCSC cyber security and resilience principles and discourage assessments being carried out as tick-box exercises."
- **Prioritisation is devolved:** organisations identify and protect their own "crown jewels"/critical assets (NCSC Board Toolkit and supply-chain guidance), and **Lead Government Departments — not a central registry — run the "criticalities process"** to categorise CNI asset criticality (NPSA). There is no UK equivalent of a single, government-held designated-asset list.
- **The PQC timelines reflect this:** rather than mandating asset-by-asset central designation, NCSC asks each organisation to run its own discovery exercise and "prioritis[e] those systems which process business and personally sensitive data, or which manage critical communications and systems."

---

## Recommendations (for authoring the reference document)

1. **Cite the NCSC PQC timelines page (https://www.ncsc.gov.uk/guidance/pqc-migration-timelines, 20 March 2025, v1.0) as the single canonical milestone source** and quote the 2028/2031/2035 wording verbatim — this is the most-misquoted item in third-party commentary, so use NCSC's exact phrasing.
2. **Source all algorithm/parameter and hybrid claims from the August 2024 v2.0 white paper** (https://www.ncsc.gov.uk/whitepaper/next-steps-preparing-for-post-quantum-cryptography): ML-KEM-768 and ML-DSA-65 for most use cases; SLH-DSA/LMS/XMSS for firmware/software signing; hybrid only as an interim measure with a path to PQC-only; single migration preferred for PKI.
3. **Frame "crown jewels"/critical assets as the UK analogue of US HVAs, but explicitly state the UK has no central designated-asset list** — back this with the CAF "outcomes not checklist" wording and the NPSA criticalities process. This is the cleanest way to answer the comparison and the "why no HVA program" sections together.
4. **Use CAF v4.0 as the current version** and enumerate the four objectives + 14 principles exactly as listed; flag that GovAssure profiles are access-restricted.
5. **For legislative currency, lead with the legislation.gov.uk text for NIS 2018 and the GOV.UK collection/factsheets for the CSR Bill**, and date-stamp the Bill's status (introduced 12 November 2025; second reading 6 January 2026) since it is actively moving through Parliament.

**Benchmarks that would change these recommendations:** (a) NCSC issuing protocol-specific PQC configuration guidance (promised "when ready") would supersede general parameter advice; (b) Royal Assent of the CSR Bill plus its secondary legislation would replace the policy-statement/factsheet figures with statutory text; (c) a new CAF version (>v4.0) or a revised Government Cyber Action Plan milestone would update Sections 2 and 5.

---

## Caveats

- **Living legislation:** The Cyber Security and Resilience Bill is mid-passage; most operational detail (penalty turnover definitions, exact thresholds, sector additions) will be set in secondary legislation. Penalty figures and the ~900–1,100 RMSP estimate come from DSIT factsheets/Impact Assessment (12 November 2025) and may change.
- **Superseded targets:** The Government Cyber Security Strategy 2022–2030's 2030 resilience target has been formally revised by the Government Cyber Action Plan (6 January 2026); cite the strategy for framing ("defend as one," CAF adoption) but note the revised delivery position.
- **Version drift:** The PQC white paper remains v2.0 (14 August 2024) on the NCSC site, but its "Also see" section links to newer related NCSC items (e.g., a December 2025 update on security certificates, TLS and IPsec) — check for protocol-specific updates before publishing, as NCSC has signalled more granular guidance is coming.
- **Non-official sources flagged:** The detailed CAF-to-IEC-62443/Purdue ICS mapping (ICS COI) and various explainer figures (techUK, vendor blogs, the AWS Security Blog corroboration of FIPS 140-3/ML-KEM) are **not** UK Government/NCSC/legislation.gov.uk/ISO/IEC/EU primary sources and should be cited only as supplementary context, clearly attributed.
- **Two URL variants:** NCSC serves several documents under both `/whitepaper/…` and `/paper/…` (and `/guidance/…` + a `/sites/default/files/pdfs/…` PDF). All variants listed above were confirmed live; prefer the `/whitepaper/` or `/guidance/` HTML canonical URLs for citations.
- **One link not independently re-verified via fetch:** the EUR-Lex CELEX URL for NIS2 (Directive (EU) 2022/2555) is constructed to the standard EUR-Lex pattern; confirm the exact CELEX landing page (eur-lex.europa.eu) before publishing rather than relying on third-party NIS2 explainer sites.