# Public Whitepaper Overview — Paper D

**Observation-Induced Model Divergence and Attack Cost Inversion**  
**Operational Principles for Cybersecurity in the Post-AI, Post-Quantum Era**

**Author:** Dr. Jinhyuk Fred Chung (Xylonix)  
**Document type:** Public overview (not a substitute for the formal Zenodo paper)  
**Series:** Information Entropy Series — Part D  
**Version:** 0.1 (GitHub)  
**Date:** 2026  

**Archival DOI:** [10.5281/zenodo.21682560](https://doi.org/10.5281/zenodo.21682560)  
**Explainer video:** https://youtu.be/jmXbr0NQBkc  
**Repository:** https://github.com/JFCSG/TBH-OIMD  
**Contact:** X2hello@xylonixscience.com  

---

## 1. Purpose of this document

This note is a **short public narrative** of Paper D for engineers, researchers, and partners.

It explains:

- why the **observation channel** is a distinct defensive surface from content and computation;
- the two principles **OIMD** and **ACI**, and the **observer’s dilemma** they form;
- how this work relates to **TheBlackHole (TBH)** and to the **KLTu** publications;
- where the **authoritative scientific record** lives.

**Measurement claims, protocols, tables, and figures are defined only in the Zenodo paper.** This overview does not expand or replace them.

---

## 2. Archival publication

| Field | Value |
|--------|--------|
| **Title** | Observation-Induced Model Divergence and Attack Cost Inversion: Operational Principles for Cybersecurity in the Post-AI, Post-Quantum Era |
| **Date** | 29 July 2026 |
| **DOI** | [10.5281/zenodo.21682560](https://doi.org/10.5281/zenodo.21682560) |
| **License** | CC BY-NC-ND 4.0 (see Zenodo) |

How to cite: [`CITATIONS.md`](../CITATIONS.md).

---

## 3. Problem framing

Defensive research has long concentrated on:

1. **Content** — confidentiality and integrity of data in transit and at rest;  
2. **Computation** — correctness and secrecy of processing (including post-quantum and homomorphic regimes).

A third question is less standardized:

> Does exterior observation **improve** an adaptive model of the system’s **hidden operational state**, and is that observation **cheap** for the attacker relative to the defender?

Hidden state, in operational terms, may include coarse attributes such as service role, enforcement regime, tenant or sensitivity class, or institutional class of target. Learning-based collectors treat sequences of exterior responses as evidence for such attributes.

If adaptive optimizers can lock onto those attributes at low cost, observation becomes a path to **strategic identification**. If they cannot—and if each attempt remains far more expensive for the observer than for the defender—then the observation channel itself becomes a **defensive surface**.

---

## 4. Two principles

### 4.1 Observation-Induced Model Divergence (OIMD)

**Operational idea:** Adaptive optimization on **exterior** observables fails to recover the defender’s true internal state \(s^*\).

Important distinction drawn in the paper:

- The optimizer may still **run** (parameters move; confidence can concentrate).  
- OIMD is scored by **extraction failure** against offline ground truth \(s^*\), not by “training loss went down.”  
- A **confidently wrong** model is still OIMD.

### 4.2 Attack Cost Inversion (ACI)

**Operational idea:** The attacker’s cost **per unit of observational work** exceeds the defender’s on stated axes (in the study: **wall time** and **package energy**, e.g. Intel RAPL).

ACI is treated as a **first-class security metric**, not only an implementation footnote: sustained learning-based observation is meant to be economically unfavorable even when legal or attributional controls are set aside.

### 4.3 Observer’s dilemma

Jointly:

1. **Necessity** — extraction requires observation;  
2. **Sterility** — under the paper’s exterior-only, label-free protocol, observation does not recover \(s^*\) (OIMD);  
3. **Expense** — each observation-plus-update step costs far more on the attacker side than on the defender side (ACI).

Observation is required for extraction, but need be neither sufficient nor cheap.

---

## 5. Evaluation setting (high level)

Paper D evaluates these principles on **TheBlackHole (TBH)**, described as a full-stack, zero-trust, entropy-aware information-theoretic protection system spanning network path, kernel datapath, memory plane, hypervisor-tier controls, and real-time **KLTu**-integrated cryptographic execution, with the observation channel treated as a first-class control surface.

Public summary of the reported dual-host study (authoritative detail only in the paper):

- Black-box **AdamW** observer restricted to **exterior HTTP** features  
- **No online labels**; true state reserved for offline scoring  
- Hyperparameter grid over learning rate and weight decay; multiple seeds; fixed step horizon  
- Reported outcome class: true-state recovery fails on **11 of 12** runs; ACI wall-time and energy ratios on the order of **~10²×** in favor of the defender on the defined unit of work  

This GitHub repository **does not** publish TBH source, datapath programs, or live configurations.

---

## 6. Relation to Papers A–C (KLTu)

Papers in the KLTu line address protection of **keys, signatures, and computation** under post-quantum and homomorphic regimes.

| Record | Role | DOI / link |
|--------|------|------------|
| Paper B | Native KEM/DSA and FIPS interop | [10.5281/zenodo.21719064](https://doi.org/10.5281/zenodo.21719064) |
| Paper C | FHE / FIPS bridge measurement | [10.5281/zenodo.21543529](https://doi.org/10.5281/zenodo.21543529) |
| KLTu public overview | GitHub front door | https://github.com/JFCSG/KLTu |
| **Paper D (this work)** | Observation channel: OIMD & ACI | [10.5281/zenodo.21682560](https://doi.org/10.5281/zenodo.21682560) |

Paper D is **complementary**: content/compute hardness does not automatically answer whether exterior learning recovers operational state cheaply.

---

## 7. Explainer video

https://youtu.be/jmXbr0NQBkc

Recommended path: problem framing → OIMD → ACI → observer’s dilemma → pointer to Zenodo for protocol and numbers.

---

## 8. Non-claims

This overview and repository **do not** claim:

- product certification or third-party assurance of any deployment;  
- results for arbitrary observer classes, unbounded horizons, or unrestricted feature access beyond the paper’s protocol;  
- a public release of TBH or KLTu production source;  
- a how-to for attacking or evading systems.

Falsifiability and limits are discussed in the formal paper; treat that text as authoritative.

---

## 9. Intellectual property

Copyright © 2026 Dr. Jinhyuk Fred Chung / Xylonix.  
Paper reuse follows **CC BY-NC-ND 4.0** as stated on Zenodo.  
See [`NOTICE.md`](../NOTICE.md) if present.

**Contact:** X2hello@xylonixscience.com · j.f.chung@xylonix.io  

---

## 10. Document history

| Version | Date | Notes |
|---------|------|--------|
| 0.1 | 2026-08 | Initial public overview on GitHub (`JFCSG/TBH-OIMD`) |

---

## 11. References

1. Chung, J. F. — Paper D — https://doi.org/10.5281/zenodo.21682560  
2. Chung, J. F. — Paper B — https://doi.org/10.5281/zenodo.21719064  
3. Chung, J. F. — Paper C — https://doi.org/10.5281/zenodo.21543529  
4. Explainer video — https://youtu.be/jmXbr0NQBkc  
5. GitHub overview — https://github.com/JFCSG/TBH-OIMD  
