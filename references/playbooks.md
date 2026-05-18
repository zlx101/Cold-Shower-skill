# Cold Shower Playbooks

Load this file only when the user asks for a scenario-specific cold-shower session.

## Requirements Before Coding

Goal: prevent Codex from turning vague confidence into production code.

Checklist:

- Who is the exact user?
- What job are they trying to finish?
- What is the smallest valuable outcome?
- What is explicitly out of scope?
- What input can be malformed, missing, huge, duplicated, or adversarial?
- What does success look like in observable behavior?
- What should happen when the system fails?

Cold-water questions:

1. If this is not built, what breaks for the user today?
2. What are you assuming the user will patiently do?
3. Which requirement is actually a solution disguised as a problem?
4. What would make this twice as small and still useful?
5. What will you regret hardcoding?

Gate:

- Proceed only if user, job, acceptance criteria, constraints, and edge cases are clear.
- Otherwise ask questions before implementation.

## Technical Plan Or Architecture

Goal: find the future maintenance pain while the plan is still cheap to change.

Attack surfaces:

- Load-bearing assumptions.
- Unowned complexity.
- Cross-module coupling.
- Migration and rollback path.
- Data consistency and idempotency.
- Observability and failure recovery.
- Security and permission boundaries.
- Testability.

Questions:

1. Which part requires every other part to behave perfectly?
2. What happens if traffic, data size, latency, or retries increase 10x?
3. What would a maintainer curse six months from now?
4. Where is the plan solving imaginary scale?
5. Which dependency or abstraction owns too much power?

Gate:

- Prefer the smallest design that preserves reversibility and testability.

## Product, Pricing, Or Startup Idea

Goal: avoid building a polished product around an unproven wound.

Pressure points:

- User pain intensity.
- Existing workaround.
- Switching cost.
- Distribution path.
- Willingness to pay.
- Retention reason.
- Competitive response.
- Founder delusion: "AI makes this easy" does not mean "the market cares."

Questions:

1. Who has the problem badly enough to pay or change behavior this month?
2. What are they using now, even if ugly?
3. Why has this not already become a default feature in a larger workflow?
4. Which claimed advantage disappears if a better-funded team copies it?
5. What evidence would make you stop?

Gate:

- Test demand before building depth.
- Treat MVP as evidence collection, not construction.

## AI-Native Startup Stage Gates

Goal: stop the user from confusing lower build cost with better judgment.

Core rule:

```text
"我做不出来" no longer proves much. "我选的问题值得做" still requires evidence.
```

### Idea

Objective: choose a problem that deserves execution.

Traps:

- starting because building is now cheap;
- using AI to prove the founder right instead of finding disconfirming evidence;
- describing a broad persona instead of a specific painful workflow;
- borrowing a market narrative without first-hand evidence.

Cold-water questions:

1. What evidence exists before a prototype?
2. Who already has this pain badly enough to change behavior?
3. What would make you admit the idea is not worth building?
4. Which competitor, internal tool, spreadsheet, or manual workaround is the real incumbent?

Gate:

- Do not proceed to MVP unless there is a named user, painful workflow, current workaround, and falsifiable demand signal.

### MVP

Objective: collect evidence, not finish construction.

Traps:

- treating MVP as a mini product launch;
- polishing AI-generated code before validating usage;
- measuring signups instead of repeated use, payment, or recommendation;
- mistaking "users are impressed" for "users come back."

Cold-water questions:

1. What user behavior would prove the MVP matters?
2. What retention, payment, or referral signal would change your confidence?
3. What is the smallest version that can expose willingness to use or pay?
4. Which feature is vanity polish hiding from evidence collection?

Gate:

- Continue only if users use, return, pay, recommend, or pull the product forward.

### Launch

Objective: turn founder effort into repeatable systems.

Traps:

- mistaking launch noise for PMF;
- relying on the founder to manually handle growth, support, and operations;
- treating every user complaint as a roadmap item;
- adding features before understanding retention.

Cold-water questions:

1. Which part of growth collapses when the founder stops pushing?
2. What support or ops pattern repeats often enough to systematize?
3. Which metric proves retention rather than attention?
4. What should be ignored even if users ask loudly?

Gate:

- Do not scale until growth, product feedback, customer support, and operations have repeatable loops.

### Scale

Objective: compound what others cannot copy quickly.

Traps:

- calling feature count a moat;
- assuming AI implementation speed is defensibility;
- ignoring integration depth and workflow lock-in;
- letting AI-generated technical debt erode the codebase's mental model.

Cold-water questions:

1. What gets stronger as more users use the product?
2. What domain knowledge or user data improves the workflow?
3. Which integrations make switching away painful for legitimate reasons?
4. Where is context drift already making the codebase incoherent?

Gate:

- Scale only around compounding advantages: domain knowledge, proprietary user data, integration depth, and workflow lock-in.

## Market Entry

Goal: compare the plan against previous deaths, not against the founder's internal movie.

Use browsing when naming companies or recent failures.

Classify failures:

- no urgent pain;
- no distribution;
- high switching cost;
- low willingness to pay;
- feature not product;
- incumbent bundled it;
- regulation or trust barrier;
- unit economics broke;
- retention collapsed after novelty.

Question:

```text
它们当年相信的那句话，和你现在相信的哪句话最像？
```

Gate:

- Enter only with a specific wedge, distribution route, and falsifiable demand signal.

## Pitch Or Investor Review

Goal: remove self-flattering narrative before someone else does it in the room.

Investor objections:

- "This is a feature, not a company."
- "Your moat is just prompt polish."
- "The user pain is real but not budgeted."
- "The incumbent can bundle this."
- "Your growth story depends on a channel you do not control."
- "Your numbers show activity, not retention."

Questions:

1. Which slide would collapse under one follow-up question?
2. Which metric is vanity dressed as traction?
3. Which part of the story is true but irrelevant?
4. What would your competitor say to make you look naive?

Gate:

- Strengthen evidence before strengthening prose.

## Personal Major Decision

Goal: reveal hidden costs, identity traps, and irreversible downside.

Pressure points:

- reversibility;
- runway;
- opportunity cost;
- family and health constraints;
- social validation;
- sunk cost;
- fear disguised as strategy;
- excitement disguised as evidence.

Questions:

1. What are you refusing to price in because it ruins the romance?
2. What must remain true for this to be a good decision?
3. What is the boring alternative you are dismissing too quickly?
4. What would make you reverse course within 90 days?
5. Who pays the hidden cost if you are wrong?

Gate:

- Make the first step smaller, more reversible, and tied to a date-based review.
