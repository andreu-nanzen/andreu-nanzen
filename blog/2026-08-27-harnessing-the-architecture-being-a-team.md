---
title: "Harnessing the architecture being a team"
date: 2026-08-27
author: Andreu Mora
audience: Nanzen team
tags: [architecture, team, product, first-principles]
---

# Harnessing the architecture being a team

_Posted 27 August 2026 — a message to the Nanzen team._

Hey team, wanted to share here some reflections on this week after all the team being back on holidays, the team update, and me being frustrated for being _harnessed_ to the bed by a virus.

Yesterday felt like a really great day. I had a couple of architecture discussions with you and I felt really good about it.

- I saw you guys making choices and questioning assumptions, including and especially "what Arnau said or what Andreu wrote".
- I saw you guys taking initiative.
- I saw you guys challenging each other to reach better outcomes.
- I saw you guys working out from first principles what great looks like.

And behaving like this you have the impression that we are unstoppable. The world will keep throwing obstacles and placing traps at Nanzen but this is how we will always come on top.

In the end it's about making something we're proud of. To be frank, I am not yet proud of the product itself right now. Neither the underlying code. But we have a plan and we are working towards it. We are taking control of the code and we're constantly talking to customers to understand better how we will exactly create value.

A couple of notes on something that got me spinning around the architecture we discussed yesterday:

**We need to be aware or careful to not build Nanzen as another SaaS.**

We must not assume that SaaS is the right model for finance workflows. A lot of successful AI companies are either installable applications (e.g. Claude Code, Factory, Cursor) or frameworks (e.g. LangGraph).

Also we are selling to the finance people who are already bloated with tools and SaaS, we definitely don't want to be seen as yet another one.

I am saying this because there's a non-negligible chance that Nanzen needs to be installed within the premises of a customer, or even within a stand-alone computer.

Nothing we decided yesterday blocks this constrain afaik but good to keep it mind.

**We need to consider Nanzen as a collaborative service**

Two words matter here:

(1) Service: the world is moving more and more towards thinking "what is the value this service brings to me". Less on "what does this software do for me" (the difference is that human or AI work answers the first one). When we talk about Nanzen we should think of hours of human pain gone away, covering all the surface that humans couldn't, stopping revenue leakage and monetizing opportunities.

(2) Collaborate: Arnau framed it really well from one of his customer discussions. People don't want another 1-human-to-1-agent tool. They want to collaborate over it. If we want to unlock N-human-to-M-agent collaboration probably that can only happen on Slack right now. BTW, the agents might not be all Nanzen agents, but also other companies' agents.

Let's talk about it in the standup have a great day of building today.
