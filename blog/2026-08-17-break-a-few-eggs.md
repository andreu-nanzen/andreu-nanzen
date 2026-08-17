---
title: "Break a few eggs, and work from first principles"
date: 2026-08-17
author: Andreu Mora
audience: Nanzen team
tags: [speed, first-principles, ai-first, process]
---

# Break a few eggs, and work from first principles

_Posted 17 August 2026 — a message to the Nanzen team._

Team, as Arnau and I shared this morning we felt that we are going slow compared to our initial speed and what our position in the market demands.

There's the issue of having some team members taking some time off in August which is obviously fine and respected. Other companies or geographies don't do that but we are not concerned about it. We are building Nanzen for the long-term, to be competitive and also sustainable. So as long as you take reasonable time-off, you enjoy life and you get perspective and sense of gratitude I see it as a plus.

There are, however, other things that slow us down. I have been thinking hard about it and I found two main root-causes after talking to you and seeing the dynamics these last weeks, especially on how we behaved around a refactor. Both are capital sins at our stage and require that we re-wire our brain into a new way of thinking. Both are downstream unconscious artifacts of our experience and learning to work AI-first.

## 1. You need to break a few eggs to make an omelette

We are extremely early. We are pre-revenue. We are pre-PMF. The only thing we should be obsessed about is _learning as fast as possible_.

We need to still fully settle on what we are building. We need to learn whether it's true that customers would pay for what we are building. We need to learn to be ok with uncertainty and doing things that won't go anywhere.

That's why I think we are over-analyzing and treating our codebase as something sacred, production-grade and resilient. It is not. It's a prototype made to learn. It's very likely we will toss it away and start from scratch.

Let's put the example of the refactor. There's a spectrum where on one end we go YOLO and "just ask Claude to refactor" and another one where we need to have 1000x confidence that whatever Claude will do will be right and thus we overanalyze and write too many specs.

We want to optimize _for outcome_ not _output_. With the YOLO approach we get a lot of _output_. With the analysis-paralysis approach we get _outcome_ but at a very expensive price. I think we should be somewhere in between but closer to the YOLO approach.

We need to have a plan and make sure that the big choices we need to make are surfaced and we have a good opinion on. That's why I went ahead and asked for a plan first that ended up being a roadmap that ended up in a number of PRDs — and that's my fault and my learning. Then those PRDs resulted in an explosion of PRs and then the migration is ungovernable.

A bare minimum spec would have been: dictionary, canonical tables, packages/app/modules choices.

Then we hit GO. If things break it's fine, we will fix later working from first principles. We are iterating and fixing.

We want to optimize for _breaking things as fast as possible, not for not breaking things_.

And remember our code will be re-generated and tossed away. The price to pay to make things "right" is not worth it.

## 2. We are not _really_ working from first principles

Working from first principles means knowing your stuff, getting to the bottom of things and then making choices. The opposite would be herd thinking or, as I suspect we all do, following Claude's recommendations blindly and trusting the process (Zenbot, CI/CD...).

We decided we'd treat specifications as the artifacts that we hold dear and thus we concentrate our efforts into writing them and sharing with the team. That's what we review. We are blindly following that `/to-prd` because someone famous on X wrote it and it works. We created Zenbot and then we just review everything with it because we can. We then have rebase hell and we say, well, the agents will wait and merge for me.

I think that's wrong. I think that we should work from first principles, doubt everything and then decide whether we are doing the right thing in the first place.

Here are a few things I think we are doing wrong.

- Follow blindly the PRD template and having complicated English we don't even understand ourselves but that it sounds very professional.
- Write the PRDs with Claude. I think that pushes us, engineers, away from the core problem and we don't understand it fully. More and more I am resorting to typing myself things just to make sure I actually understand them.
- Have Claude and then Zenbot review things even though the likelihood of discarding them is > 70%. The problem is not the review itself, it is blindly trusting it works and then creating more bloat to compensate for the issues it finds. And also the speed loss on something that maybe it's ok not to review.
- Not having good grip on our codebase. I have seen a few module disasters, repeated code, objects that belong on different places or scattered across apps and packages. And the reason is that probably we don't understand what's there in the first place. And neither does Claude because it loads local files (or even file chunks) but it looks almighty. Then it tells you something like _"Good catch, your finding is load-bearing and it was all wrong in the first place — and that's the honest answer"_. One thing is that we don't write code, another thing is that we don't have a clue about our codebase.

I still think our durable artifact is the set of specifications we are writing and reviewing together. Claude should help us harden our thinking (not delegate it) and should streamline code writing. The code might well be reproducible with that input plus the agent guidelines but that doesn't mean we can't understand it.

## OK, now what?

What does this mean for the team? Here are some concrete actions and expectations. I include myself in the receiving end of this because I am also guilty of this.

- As a default, a migration should take 1 day, not 2 weeks. Let's put this baseline for us. That will force us to break a few eggs. If we can't do that we will not survive in startup land.
- I would expect everyone to ship around 2 PRs a day. The "it touches too many things in the code" is not a valid reason to postpone something. I won't challenge you for blowing the app up because a detail escaped. I would challenge you if (1) you shipped shitty engineering or (2) you were way too slow to ship because you were afraid of breaking things.
- I want to revisit the dev process first things next week when everyone is back. I will propose things in the line of:
    - Lighter PRDs/specifications.
    - Forcing all of us to understand the code it produces and explain it to a team member.
    - Being ready to explain a spec to a team member. It doesn't mean that Claude can't write it, but you need to own it.
    - Not running Zenbot on everything as a CI gate. How would you behave if you knew Zenbot wasn't there? Would you care more for understanding the code? We already removed it for docs but I think we can do for other tasks.
    - I want to revisit the CI gating as I want merging to be faster even if it feels a % less safe. I would trade 10x more speed for 2x more risk.
