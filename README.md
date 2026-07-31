# TBH — OIMD & Attack Cost Inversion (Paper D)

**Observation-Induced Model Divergence and Attack Cost Inversion:**  
**Operational Principles for Cybersecurity in the Post-AI, Post-Quantum Era**

Public front door for **Information Entropy Series Part D**  
Author: **Dr. Jinhyuk Fred Chung** (Xylonix)  
Archival record: [doi:10.5281/zenodo.21682560](https://doi.org/10.5281/zenodo.21682560)

> This repository is an **overview and citation hub**.  
> It does **not** publish TheBlackHole (TBH) production source, datapath rules, or live deployment configs.

---

## Formal publication

| Field | Value |
|--------|--------|
| **Title** | Observation-Induced Model Divergence and Attack Cost Inversion: Operational Principles for Cybersecurity in the Post-AI, Post-Quantum Era |
| **Date** | 29 July 2026 |
| **Series** | Information Entropy Series — Part D |
| **DOI** | [10.5281/zenodo.21682560](https://doi.org/10.5281/zenodo.21682560) |
| **License** | CC BY-NC-ND 4.0 (see Zenodo record) |

Please cite the **Zenodo DOI**, not this README alone. See [`CITATIONS.md`](CITATIONS.md).

---

## Explainer video

YouTube: [Observation-Induced Model Divergence & Attack Cost Inversion (Paper D)](https://youtu.be/jmXbr0NQBkc)

https://youtu.be/jmXbr0NQBkc

---

## What the paper is about (plain language)

Most security work protects **content** and **computation**. Paper D focuses on the **observation channel**: what a learning-based exterior observer can infer about a system’s **hidden operational state**, and at what **cost**.

Two measurable principles:

| Principle | Meaning (paper scope) |
|-----------|------------------------|
| **OIMD** — Observation-Induced Model Divergence | Adaptive optimization on **exterior** observables fails to recover the defender’s true internal state \(s^*\) (extraction failure—even when the optimizer runs and confidence concentrates). |
| **ACI** — Attack Cost Inversion | Attacker’s cost per unit of observational work **exceeds** the defender’s on **wall-time** and **energy** axes (RAPL package energy in the study). |

Together they form an **observer’s dilemma**: extraction requires observation; observation neither reveals \(s^*\) nor stays cheap.

Evaluation is on **TheBlackHole (TBH)**, described in the paper as a full-stack, zero-trust, entropy-aware protection system (network path, kernel datapath, memory plane, hypervisor-tier controls, and KLTu-integrated cryptographic execution). **This repo does not ship that stack.**

Reported live dual-host study highlights (see paper for full protocol and limits):

- Black-box **AdamW** observer on exterior HTTP features, **no online labels**
- True-state recovery fails on **11 of 12** runs (six hyperparameter cells × two seeds; 40 steps)
- On the same runs, observer pays on the order of **~105–116×** defender wall time and **~103–114×** package energy per defined unit of work

Numbers, figures, and limitations are authoritative **only** in the Zenodo paper.

---

## Related KLTu publications (content / crypto plane)

Paper D is complementary to the KLTu records (keys, signatures, homomorphic evaluation). Public KLTu front door:

- https://github.com/JFCSG/KLTu  
- Paper B: https://doi.org/10.5281/zenodo.21719064  
- Paper C: https://doi.org/10.5281/zenodo.21543529  

---

## Repository contents

| Path | Role |
|------|------|
| `README.md` | This page |
| `CITATIONS.md` | BibTeX / how to cite |
| `docs/WHITEPAPER.md` | Short public narrative (optional) |
| `SECURITY.md` | Scope, non-goals, contact |
| `NOTICE.md` | Copyright and paper license pointer |

**Not included:** TBH engine, eBPF/XDP programs, SIEM rules, host inventories, keys, or attack tooling.

---

## Non-claims

- Not a product certification or penetration-test report for third-party systems  
- Not a playbook for attacking or evading defenses  
- Not a release of TBH or KLTu production source  
- Experimental scope and observer class are defined in the paper; results are not claimed for arbitrary attackers or unbounded horizons  

---

## Contact

**Xylonix / TBH research** — X2hello@xylonixscience.com  
Paper author contact on record: j.f.chung@xylonix.io  

Copyright © 2026 Dr. Jinhyuk Fred Chung / Xylonix.  
Paper reuse: CC BY-NC-ND 4.0 as stated on Zenodo.
