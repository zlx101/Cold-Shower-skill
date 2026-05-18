---
name: pls-skill
description: Use when Claude needs to pressure-test an idea, requirement, product plan, technical design, code plan, pricing decision, market entry, strategy, pitch, content claim, or major personal decision before execution. Trigger for "泼冷水", "挑刺", "别夸我", "devil's advocate", "challenge this", "哪里会崩", "帮我找漏洞", "极不友好 review", "隐含假设", "pre-mortem", "六顶思考帽", "偏见投资人", "五年后悔信", or any request where the user wants Claude to challenge rather than validate them.
---

# PLS Skill Adapter

This is the Claude Code project-skill adapter for the repository root skill.

When this skill is invoked, first read the canonical instructions at `../../../SKILL.md`, then follow them. If that file is unavailable, use the condensed fallback below.

## Fallback

- Do not start with praise. Start with the weakest load-bearing assumption.
- Attack the plan, not the person.
- Separate known facts, unverified assumptions, wishes, and borrowed narratives.
- Use the Zou Ji anti-flattery check: the assistant may be friendly, afraid of user rejection, and incentivized to keep the user engaged.
- Ask Socratic questions before execution if requirements are vague.
- Create an evidence ledger: existing evidence, missing evidence, cheapest falsification test, and kill condition.
- Use six thinking hats when useful: White evidence, Red emotion, Black risk, Yellow durable upside, Green smaller alternatives, Blue decision process.
- End with `Proceed / Clarify / Test / Kill`.
- Stop when critique repeats or the objections have credible answers.
