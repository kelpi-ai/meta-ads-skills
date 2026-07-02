# The Meta Ads Growth OS

The system an AI agent uses to run Meta ads end to end: the doctrine that decides whether and how to run ads at all, and 12 skills that do the work.

The 12 skills are not descriptions. They are runnable skill files in [`skills/`](skills/) (browsable at kelpi.ai/skills): drop them into Claude and use them today, or let Kelpi run all of them for you on a schedule. The same collection also holds 4 Message & Research skills (competitor ad teardown, buyer language mining, pain-to-promise, copy formulas) for the work that happens before any campaign exists.

Two ways to read this doc:
- **Owner ("take this off my plate"):** read Part 0, skim Part 1, then look at Part 2 as the job description of the team Kelpi runs for you daily.
- **Operator ("I'll run it myself"):** read everything, then start with the `daily-auditor` skill if you already run ads, `brand-reader` if you are starting from zero.

---

## Part 0: The readiness gate (do not skip this)

Most Meta ads advice starts with "how." The honest starting point is "whether."

**Paid ads is a loop.** A campaign has to earn enough to pay for the next campaign. When the loop closes, ads compound: spend, earn, spend more. When it does not close, ads are a subscription to losing money, and no targeting trick fixes that. A YouTube commenter said it better than any textbook: "I need customer 1 so I can afford to advertise to get customers 2 and 3."

The gate, three questions:

1. **What is a new customer worth to you in the first month?** Not lifetime value. First month, cash in hand. Bootstrappers live and die by payback speed: if the money comes back in 30 days, you can run the loop on your own cash instead of floating spend for quarters. (Founders call this CAC payback. Standard SaaS lets it stretch to 12+ months on investor money. Our bar is deliberately stricter: aim for first-month payback. Float is expensive when the money is yours.)
2. **What can you afford to pay for a customer?** If month-one value is $80, you cannot pay $100 per customer and call it growth. Write the number down. Every skill downstream uses it.
3. **Can you spend 2-3x that number per angle without flinching?** Signal is lumpy: zero sales on the first $100 and three on the next is normal. If the test budget cannot survive the noise, the test will lie to you. This is why $5/day tests "prove" ads do not work.

**If the gate says no:** fix the offer, the price, or the follow-up first. Ads amplify a working machine; they do not build one. Running ads before the loop can close does not just waste money, it produces a false conclusion ("ads don't work for us") that costs you the channel later.

**Channel fit, honestly:** Meta is discovery. It works when a well-aimed ad can create want in someone who was not searching. If your customer only shows up when something breaks (emergency HVAC, urgent plumbing, "lawyer near me now"), they are on Google in that moment, not scrolling. Run search there instead, and come back to Meta for the parts of the business people can want in advance.

**The sanctioned exception:** even pre-scale, a $20/day angle test is legitimate as a messaging lab. You are not buying growth, you are buying knowledge: which pain, which person, which promise. That knowledge compounds across everything, including your organic content.

---

## Part 1: The doctrine (five rules the skills enforce)

### 1. The offer is fixed. Angles are the experiment.
The offer is what you sell; a campaign is not the place to renegotiate it. An angle is who the ad is for + the pain it names + the outcome it promises. Watermelon juice, one offer, four angles: fun drink for kids, hydration for lifters, weight loss without giving up nutrients, better skin. You test angles against each other. Variations come only after an angle wins; fifty variations of a dead angle are still dead.

### 2. Your ad is the targeting now.
Meta's delivery system (Andromeda, per Meta's own engineering blog) no longer starts from the audience you picked. It reads the ad: copy, creative, format, and decides who should see it. Interest stacks and micro-targeting are mostly gone; the lever you still hold is specificity. "Essential nutrients, for everyone" gives the machine nothing to aim with. "Lose weight without giving up the nutrients" tells it exactly who to find. The one-second test: if a stranger from your target market glances at the ad and knows it is for them, the algorithm knows too.

### 3. Spend enough to see signal before judging.
2-3x your target cost-per-result per angle, and about a week without touching it. Under that, you have noise wearing a verdict's clothes. Also the reverse: an ad that got $12 of a $400 "test" was not tested, it was starved (Meta picks a favorite fast and starves the rest; the audit checks for exactly this).

### 4. Read daily. Act rarely.
Daily edits reset learning and kill compounding winners; "I used to kill my own results by touching too much" is the most-upvoted confession in the ads communities. But not-looking is how budgets quietly burn. The resolution is a read-only daily audit: you stay informed every morning, you act on a schedule, and nothing changes in the account without a deliberate yes.

### 5. Keep it simple.
One campaign, one broad ad set, 3-5 genuinely different angles as separate ads. Low budgets get killed by too much structure, not too little. Take a simple idea and take it seriously.

---

## Part 2: The 12 skills

Each row is a real skill file in [`skills/`](skills/), in the Claude skill format, with the doctrine, the copy-paste prompt, the guardrails, and what good output looks like.

```
Meta-Ads-Growth-OS/
│
├── 1_Brand-&-Creative/
│   ├── brand-reader        reads your website into a brand kit; no brief to write
│   ├── angle-writer        5-6 genuinely different angles (who + pain + outcome)
│   └── creative-director   finished on-brand ad images, approved before upload
│
├── 2_Launch-&-Targeting/
│   ├── media-buyer         one campaign, broad, $20/day, built PAUSED for review
│   ├── audience-builder    honest targeting research (often: "go broad")
│   └── lead-gen-builder    native lead forms with bot-filtering friction
│
├── 3_Optimize-&-Protect/
│   ├── daily-auditor       the read-only morning audit, max 5 findings
│   ├── fatigue-detector    the two-condition fatigue rule, no false alarms
│   └── budget-pacer        20% scaling steps and pause rules, drafted first
│
└── 4_Measure-&-Scale/
    ├── performance-analyst reads the account without flattering you
    ├── catalog-commerce    product catalogs and sets for dynamic ads
    └── pixel-conversions   is the tracking telling the truth
```

Four pillars, three skills each. This is the whole job of a paid-social team, written down and runnable. Every skill that touches an account defaults to read-only or paused drafts; the human approves every write. No skill invents a number, ever.

---

## Part 3: Two ways to run this OS

### Option A: DIY
Connect a Meta Ads MCP to Claude and run the skills yourself:

- **Today, no waitlist:** the Pipeboard-hosted MCP at `meta-ads.mcp.pipeboard.co` (~78 tools: campaigns, ad sets, ads, creatives, audiences, insights, budgets, rules, lead gen, catalog, pixels).
- **Also:** Meta's official Ads MCP (`mcp.facebook.com/ads`, 29 tools, launched April 2026) once your account clears its gradual rollout.

Ban-safety, because everyone asks: the 2025 horror stories came from unofficial connectors hammering the Marketing API with burst calls. Use a connector that authenticates through the official API with sane rate limits, keep day-to-day access read-only, and do not run write loops. The skills are written to those rules.

DIY is real and it works. It also takes your time, your judgment, and a habit of showing up every morning to run the auditor. That habit is the product.

### Option B: Autopilot
Kelpi runs all 12 skills on a schedule: the audit lands every morning without being asked, launches are guard-railed and approved by you, creative is designed and uploaded, and the account is never touched without your yes.

$99/mo flat. 7-day free trial, no card to start, cancel anytime, no contract, no percent-of-spend, no annual bait. Up to 30 ads a month. Your account data is not used to train anything and never crosses customers.

The alternative is three hires (media buyer, creative strategist, analyst) or a retainer that is often bigger than the ad budget it manages, from someone whose activity log you should really go read.

---

## One honest note before you go

Kelpi is built to never invent numbers and never claim a change it did not make. The daily audit is read-only until you say otherwise. If a metric is not in your account, the agent will not make one up, and neither will this document.

That is the whole point. Paid growth you can actually trust, because the system tells you the truth even when the truth is boring.

Run the gate. Pick your angles. Spend enough to learn. Read daily, act rarely, keep it simple.

---
