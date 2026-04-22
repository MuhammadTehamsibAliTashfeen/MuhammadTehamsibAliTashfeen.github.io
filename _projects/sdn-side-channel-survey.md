---
layout: page
title: Side-Channel Attacks in SDNs
description: Comprehensive survey of side-channel attack vectors in Software-Defined Networks, submitted to ACM Computing Surveys.
importance: 3
category: work
---

A systematic literature survey co-authored with [Prof. Zhiyong Shan](https://www.wichita.edu/profiles/academics/engineering/SoC/01_Faculty/Shan-Zhiyong.php), currently under review at *ACM Computing Surveys*.

**Scope.** Software-Defined Networking separates the control plane from the data plane, enabling programmable network management — but this architecture introduces side-channel attack surfaces absent in traditional networks. The survey maps these vectors, classifies existing attacks and defenses, and identifies open problems.

**Key attack classes covered.**
- **Control-plane timing leaks** — first-packet round-trip time reveals flow-rule existence to co-located adversaries
- **Flow-table covert channels** — TCAM capacity exhaustion as a cross-tenant side channel
- **Controller load oracles** — packet-in flooding to infer concurrent flow state

**Contribution.** A structured taxonomy of SDN-specific side channels with a gap analysis of current defenses — providing a reference map for future mitigation research.

**Status.** Under review at *ACM Computing Surveys* (2025).
