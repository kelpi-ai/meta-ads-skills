# Kelpi Skills: the Meta Ads Growth OS, runnable

Not a PDF about running Meta ads. The actual system, as 16 skill files you can run with Claude today.

The core is the **Meta Ads Growth OS**: 12 skills across 4 pillars, the whole job of a paid-social team written down and runnable. Around it, a **Message & Research** group covers the work that happens before any campaign exists: mining buyer language, tearing down competitors' proven angles, sharpening promises, and writing copy with the classic formulas.

Browse every skill with examples at **[kelpi.ai/skills](https://kelpi.ai/skills)**.

## Install

One command, via the open [skills CLI](https://github.com/vercel-labs/skills) (works with Claude Code, Cursor, Codex, and 60+ other agents):

```bash
# everything
npx skills add kelpi-ai/meta-ads-skills --all

# or one skill
npx skills add kelpi-ai/meta-ads-skills --skill daily-auditor
```

By hand instead: each folder in `skills/` holds one `SKILL.md` in the Claude skill format plus a `skill.meta.json`.

- **Claude Code:** copy any skill folder into `~/.claude/skills/` (or your project's `.claude/skills/`). Claude picks it up by name.
- **Claude (chat):** paste the skill's "Run it" prompt straight into a conversation.
- **Account access:** skills that read or write an ad account use the Meta Ads MCP:
  - available today, no waitlist: the Pipeboard-hosted MCP at `meta-ads.mcp.pipeboard.co` (~78 tools),
  - also works: Meta's official Ads MCP (`mcp.facebook.com/ads`, 29 tools) once your account clears its gradual rollout.
  - `mcp_access` in each skill's meta file tells you what it needs: `none`, `read`, or `write`.

Start with `daily-auditor` if you already run ads, `brand-reader` if you are starting from zero.

## The rules every skill is built on

1. **Read-only by default.** Every skill that touches an ad account analyzes first and leaves changes as explicit, separate steps you approve. Nothing writes without you.
2. **Honest numbers.** No skill invents a metric, rounds a guess into a fact, or claims a change it did not make. If the data is not in the account, the answer is "the data is not there."
3. **Angles over variations.** The offer is fixed; the angle (who + pain + outcome) is the experiment. Five variations of one idea is one test wearing five hats.
4. **Enough spend to judge.** No verdict on an angle before it has spent 2-3x your target cost-per-result. Small samples lie politely.
5. **Simple structure.** One campaign, one broad ad set, 3-5 genuinely different angles. Low budgets get killed by too much structure, not too little.
6. **Ban-safe.** Official API auth, sane rate limits, no burst write loops. The 2025 horror stories came from connectors that did the opposite.

## The map

```
skills/
├── Message & Research (before any campaign exists)
│   ├── competitor-ad-teardown   proven angles from the Meta Ad Library
│   ├── buyer-language-miner     verbatim pains, desires, objections
│   ├── pain-to-promise          promises that pass the one-second test
│   └── copy-formulas            PAS, AIDA, BAB and friends, honestly applied
│
├── 1 Brand & Creative
│   ├── brand-reader             reads a website into a brand kit
│   ├── angle-writer             5-6 genuinely different angles
│   └── creative-director        on-brand ad images, approved before upload
│
├── 2 Launch & Targeting
│   ├── media-buyer              one campaign, broad, $20/day, built PAUSED
│   ├── audience-builder         honest targeting research (often: "go broad")
│   └── lead-gen-builder         lead forms with bot-filtering friction
│
├── 3 Optimize & Protect
│   ├── daily-auditor            the read-only morning audit, max 5 findings
│   ├── fatigue-detector         the two-condition fatigue rule
│   └── budget-pacer             20% scaling steps, drafted first
│
└── 4 Measure & Scale
    ├── performance-analyst      reads the account without flattering you
    ├── catalog-commerce         catalogs and product sets for dynamic ads
    └── pixel-conversions        is the tracking telling the truth
```

## The other way to run this

All of it runs inside [Kelpi](https://kelpi.ai) on a schedule, with guardrails, whether or not you remember to ask: the audit lands every morning, launches are approved by you, creative is designed and uploaded. $99/mo flat, 7-day free trial, no card to start, cancel anytime.

The doctrine behind the skills (when to run ads at all, the loop math, the testing thresholds) ships with the OS document in the same collection.

## License

MIT. Open and inspectable on purpose: you should be able to read every instruction an agent runs against your ad account.
