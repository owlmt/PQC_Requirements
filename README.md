# PQC_Requirements

**Jurisdictional requirements for Post-Quantum Cryptography (PQC) migration.**

A reference library mapping how the United States, the United Kingdom, and the European Union each define their most critical systems and what each regime requires when migrating those systems away from quantum-vulnerable cryptography. The documents are written for CISOs, enterprise architects, government agencies, operators of critical infrastructure, cloud providers, compliance teams, software vendors, and PQC migration teams.

Every factual claim is cited to an official government, regulator, or standards-body source. No vendor marketing, no fabricated links.

---

## Why this repository exists

The migration to post-quantum cryptography is a multi-year programme that no organisation can complete instantly. Doing it in the wrong order wastes scarce capacity on low-consequence systems while leaving the highest-consequence ones exposed to "harvest-now-decrypt-later" attacks. Every major regime therefore tells organisations to migrate their most critical systems first.

The hard part is that each jurisdiction defines "most critical" differently:

- the **US** designates a central list of **High Value Assets (HVAs)**,
- the **UK** uses an outcomes-based model of **essential functions** and **"crown jewels"** with no central asset list,
- the **EU** regulates **essential and important entities** rather than assets at all.

This repository documents each model, the legal instruments behind it, and how to turn it into a defensible PQC migration priority order.

---

## Documents

| Jurisdiction | Document | Core construct | Key instruments |
|---|---|---|---|
| 🇺🇸 United States | [US OMB High Value Assets (HVA) Requirements for PQC Migration](docs/requirements/omb/OMB-HVA-Requirements-for-PQC-Migration.md) | High Value Assets (centrally designated) | OMB M-19-03, M-23-02, M-26-15; NSM-10; FIPS 199/200/203/204/205; CNSA 2.0 |
| 🇬🇧 United Kingdom | [UK Critical Systems and Crown Jewels Requirements for PQC Migration](docs/requirements/uk/UK.md) | Essential functions / "crown jewels" (risk-based, no central list) | NCSC CAF v4.0; NIS Regulations 2018; Cyber Security and Resilience Bill; NCSC PQC timelines (2028/2031/2035) |
| 🇪🇺 European Union | [EU Essential Services and Critical Assets Requirements for PQC Migration](docs/requirements/eu/EU.md) | Essential and important entities (entity-centric) | NIS2; CER Directive; CRA; DORA; GDPR; eIDAS 2.0; ENISA guidance; EU PQC Roadmap (2026/2030/2035) |

---

## How the three models compare

| Dimension | United States | United Kingdom | European Union |
|---|---|---|---|
| Unit of regulation | Asset (HVA) | Function / asset ("crown jewels") | Entity |
| Designation | Centrally designated, reported to CISA | Devolved to organisations and Lead Government Departments | Self-identification by sector and size |
| Anchor instrument | OMB M-19-03 / M-26-15 | NCSC CAF + NIS Regulations 2018 | NIS2 / CER / CRA / DORA |
| Central asset list? | Yes | No | No |
| Stated PQC end-state | High-impact systems first; full migration by 2035 | Highest-priority by 2031; full migration by 2035 | High-risk by 2030; medium/low by 2035 |

A more detailed comparison appears inside each document.

---

## Common thread across all three

Despite different legal models, the three regimes converge on the same operational sequence:

1. **Inventory cryptography** before changing anything (build a Cryptographic Bill of Materials, the CBOM).
2. **Classify and rank systems** by impact and data-confidentiality lifetime.
3. **Prioritise the most critical systems first** (HVAs, crown jewels, or essential entities).
4. **Migrate key establishment before signatures** to address harvest-now-decrypt-later exposure.
5. **Engineer for crypto-agility** so future algorithm changes are configuration, not re-architecture.

---

## Repository structure

docs/

└── requirements/

├── omb/   US OMB High Value Assets

├── uk/    UK Critical Systems and Crown Jewels

└── eu/    EU Essential Services and Critical Assets

---

## Status and contributing

These are living documents. Policy, legislation, and standards in this area change frequently (the EU NIS2 transposition, the UK Cyber Security and Resilience Bill, and the US PQC executive orders are all moving). To propose a correction or addition, open an issue or pull request and cite the official primary source for any factual change. Do not introduce links that have not been verified against an authoritative government, regulator, or standards-body publication.

---

## Disclaimer

This repository is an informational synthesis of public policy, legislation, and standards. It is not legal advice and is not an official government publication. Always consult the primary sources linked within each document.
