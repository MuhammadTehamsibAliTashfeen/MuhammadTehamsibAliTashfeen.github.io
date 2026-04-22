---
layout: post
title: "Side-Channel Attacks in SDNs: What the Literature Reveals"
date: 2025-03-10 00:00:00 -0500
description: A summary of key findings from my survey on side-channel attack vectors in Software-Defined Networks, submitted to ACM Computing Surveys.
tags: [SDN, side-channel, network security, survey]
categories: research
---

Software-Defined Networking decouples the control plane from the data plane, enabling flexible, programmable network management. That architectural separation, however, creates new side-channel attack surfaces that traditional network security models were not designed to address.

My survey — currently under review at *ACM Computing Surveys* — systematically maps the landscape of side-channel attacks specific to SDN environments. Here are three patterns that stood out.

**Control-plane timing leaks.** Because SDN switches consult a centralized controller for flow-table misses, the round-trip time of a first-packet lookup leaks information about whether a flow rule exists. An attacker co-located on the data plane can use this to fingerprint traffic policies or infer network topology without breaking any encryption.

**Flow-table capacity exhaustion as a covert channel.** TCAM-based flow tables have bounded capacity. A malicious tenant can flood the switch with synthetic flows, observe the degradation in legitimate traffic, and extract a timing signal correlated with other tenants' behavior — a covert channel that crosses tenant boundaries without any direct data access.

**Controller load as an oracle.** High-rate packet-in events saturate the controller's processing queue. A patient attacker can modulate their own traffic to probe this queue and infer information about concurrent flows being processed — effectively using the controller as an unwitting oracle.

The survey also reviews proposed defenses — randomized flow-table eviction, rate limiting on packet-in messages, and control-plane isolation — and identifies gaps where no satisfactory mitigation exists yet.

If you are working on SDN security or side-channel defenses and want to discuss the findings, feel free to reach out.
