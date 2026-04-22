---
layout: page
title: Side-Channel Attacks in SDNs
description: Comprehensive survey of side-channel attack vectors in Software-Defined Networks, submitted to ACM Computing Surveys.
importance: 3
category: work
---

A systematic literature survey co-authored with [Prof. Zhiyong Shan](https://www.wichita.edu/profiles/academics/engineering/SoC/01_Faculty/Shan-Zhiyong.php), currently under review at *ACM Computing Surveys*.

---

#### SDN Architecture

{% include figure.liquid path="assets/img/projects/sdn_arch.png" caption="SDN architecture (Open Networking Foundation): decoupled control plane (controller) and data plane (switches), creating new side-channel attack surfaces." class="img-fluid rounded z-depth-1" zoomable=true %}

---

#### Attack Surface Summary

| Attack Class | Vector | Target | Mitigation Gap |
|---|---|---|---|
| Control-plane timing leak | First-packet round-trip time | Flow-rule existence | Partial (randomized delays) |
| Flow-table covert channel | TCAM capacity exhaustion | Cross-tenant traffic inference | Open problem |
| Controller load oracle | High-rate packet-in flooding | Concurrent flow state | Partial (rate limiting) |
| Topology fingerprinting | Probe packet timing | Network topology | Limited coverage |

---

#### Key Findings

**Software-defined networking creates three novel side-channel surfaces** absent from traditional networks:

1. **Control-plane timing leaks** — the round-trip time of a first-packet lookup reveals whether a flow rule exists, enabling topology fingerprinting without breaking encryption.
2. **Flow-table covert channels** — TCAM capacity exhaustion allows a malicious tenant to infer other tenants' traffic across isolation boundaries.
3. **Controller load oracles** — saturating the packet-in queue enables inference about concurrent flow state.

**Status.** Under review at *ACM Computing Surveys* (2025).
