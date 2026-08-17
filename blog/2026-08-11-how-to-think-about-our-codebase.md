---
title: "How to think about our codebase"
date: 2026-08-11
author: Andreu Mora
audience: Nanzen team
tags: [codebase, first-principles, simplification, verification]
---

# How to think about our codebase

_Posted 11 August 2026 — a message to the Nanzen team._

Hey team, I wanted to persist in writing what we discussed yesterday around how to think about our codebase.

We have iterated very quickly and we should keep doing so, however, we should also be aware of the trail we leave behind and make sure we treat our code as our most precious asset even if it is cheap to generate now with agents.

In the age of AI there's a real danger of small companies like ours becoming an infinite collection of half-baked features, bells and whistles without a clear purpose and that will eventually die because users won't pay for it.

I hope I was clear yesterday on how I want you to think when we look at the code and the strategic choices we will make around it. Yesterday it was framed around the exercise for removing the big dependency on Job&Talent asks as well as the coupling of buyer and seller and move it to a generic app, however that is valid at anytime for Nanzen.

## Step 0 — Delete what we don't need

Code is cheap to create and you should treat it more ephemerally than before. Question why something is there, chances are it is not needed anymore. This is where we need to govern our codebase and think from first principles.

In case of doubts, err on the side of simplification. If it hurts, we can add it back.

Needless to say, we do not keep code just because it might be useful for later. Persist the lessons learnt and get rid of what we do not need.

## Step 1 — Fix fundamental issues

Address systematic and fundamental errors and bugs on stuff we absolutely need. For example, we now have around 7500+ error log lines. That's not healthy. Either we do not need the code below, the logging is too strict/verbose or we need to fix something.

## Step 2 — Establishing baseline performance (and then climbing)

Let's focus on establishing baseline performances and standard user journeys and make sure the system does a good job at doing so. This will require us to create canonical datasets and scenarios and us spending time analyzing traces and trajectories and "getting in the weeds" of how agents perform.

Only after we understand fully how our systems work we should attempt to introduce variations and alterations (optimize).

## Step 3 — Automate verification

Last step is once we know for sure manually something works, how can we automate that confidence? This is where we build the on-the-fly lookups, verifications, audits and verification harness.

This is in some form a variation of Musk's algorithm — Question / Delete / Simplify / Accelerate / Automate — that I am sure we will be revising in our own way.
