# EmpowHER Revenue Agent — Team Review, Research & Revision

*Gail called the room. Pam set the schedule. Eight specialists took your build through
their lane. Frannie holds the gate — nothing ships without her sign-off.*

You asked the team to **review, research, and revise** your Revenue Operating System
build prompt for EmpowHER. Here is each member's pass, then the upgraded prompt, then a
map of everything that changed and what you run next.

> **The one decision that drove everything (Aaron):** your draft named the creator
> "FuturIQ" with a generic audience. EmpowHER already has a brand, a voice, and a real
> avatar (Ronnie — the ambitious, time-starved Black professional woman who knows AI
> matters but doesn't know what to build first). We aligned the build to *her*. If
> FuturIQ is a separate sub-brand, flip the Creator/Audience blocks back in
> `business-brief.md` — nothing else has to change.

---

## How to read this — Beginner Mode (Albert)

You asked us to treat you like a beginner and explain in plain English. That's my lane.
Here are the only four words you need:

- **Subagent** — a named helper with one job. Instead of one assistant doing everything,
  you hire four specialists. Each only does its part, so the work stays sharp. Think of
  it like your real team: you don't ask your editor to do your taxes.
- **`.claude/agents/` folder** — this is where Claude Code looks for your hired helpers.
  Each helper is one text file. The file *is* the job description.
- **Frontmatter** — the few lines at the top of each helper file between the `---` marks.
  It's the helper's name tag: what it's called, what tools it's allowed to touch, which
  model it runs on. Get this wrong and the helper won't show up for work.
- **Coordinator** — that's the main Claude Code chat. It's the manager. It doesn't do the
  specialist work; it hands each piece to the right helper and assembles the result.

Why files instead of one long chat prompt? Because a file is reusable. You build the team
once, and it shows up every time — for this video, the next one, and the one after that.
That is the difference between doing the work and *owning a system that does the work.*

---

## 1. Aaron — Strategy & Instruction Upgrade

I open strategy. Before anyone builds, I read what you actually asked for.

**1. What you're clearly asking for**
A real Claude Code subagent architecture (not one chat answer) that turns one business
idea into positioning, an offer, YouTube angles, a lead magnet, and a follow-up sequence
— saved as files, then run by a coordinator to produce a final video brief.

**2. What's implied but not stated**
- This is content marketing for *your* business, not a tech demo. The video is the top of
  a funnel that ends in revenue.
- "For EmpowHer" means it must sound like you and serve Ronnie — not a generic creator.
- You want to *learn while we build* (Beginner Mode), so the build is itself a teaching
  asset you could resell.

**3. What important context is missing**
- Which offer the video actually sells. "Template, workshop, OR paid offer" is three
  paths. Revenue systems convert better with one primary next step.
- Proof. The promise "AI systems make revenue" needs on-screen evidence, or it reads as
  hype. What can you show that's real?
- Platform reality. Is the channel new or established? That changes whether the angle is
  "you're not behind yet" (cold audience) or "I built this for you" (warm audience).

**4. Decisions you need to make before building**
- **D1 — Brand:** EmpowHER or FuturIQ? (We defaulted to EmpowHER.)
- **D2 — Primary CTA:** the free Revenue Agent template is the recommended single next
  step; workshop and premium offer sit behind it on the ladder.
- **D3 — Proof asset:** decide now what you'll show on screen (a real prior result, or the
  live build itself as the proof).
- **D4 — Niche depth:** "entrepreneurs" is broad. We narrowed to women coaches/
  consultants/creators so the promise is believable in 3 seconds.

**5. How I'd rewrite your request**
Your original was a stack of strong prompts, but it asked for everything at once. The
upgrade: name the brand, name the one offer, name the proof, then build. See the
**Upgraded Prompt** and the **Merged Prompt** at the bottom of this document — that's my
deliverable for the *Instruction Upgrade* and *Optional Merge* steps.

---

## 2. Rebecca — Market Signal Research

A good answer starts with a sharp question and ends with a source. You invoked the **Web
Research Fallback** ("assume the market signal is based on the business brief only; label
inference, not evidence"), so I worked brief-first and labeled my confidence honestly.

**Demand pattern**
- *Inference from brief (likely):* Women entrepreneurs and Black professional women are
  actively searching "how to use AI in my business" but bouncing off tool-by-tool tutorials
  that never connect to money. Your brief states this pain directly; I did not verify it
  against live search data in this pass.
- *Inference (likely):* "Agent" and "Claude Code" are rising-interest terms in the creator/
  AI-business space. Treat as a tailwind, not a guarantee — **unverified** without live data.
- *Confirmed (from your own assets):* EmpowHER already runs a $27 monthly live build
  workshop. That is a real, priced, proven next step — strong evidence the audience will
  pay to build, not just watch.

**Audience psychology (Ronnie)**
- *Wants:* leverage and her time back. To feel ahead, not behind.
- *Fears:* being left behind by AI; wasting money on tools she won't use; looking like a
  beginner.
- *Misunderstands:* that the win is the tool. It isn't. It's the system.
- *Secretly hopes is true:* that she can build something real today, herself, without
  becoming a programmer.

**Confidence flags for the strategist:** anything about search volume, trending titles, or
competitor view counts is currently **unverified**. Before publish, give me a real brief
and I'll source it (YouTube search, Google Trends, competitor channels) and upgrade these
from "likely" to "confirmed."

**Risk:** if the video can't show a real build producing a real, specific output, the
"systems not tools" promise collapses into the exact hype Ronnie is tired of.

---

## 3. Albert — AI Intelligence & Technical QA

My job is signal vs. noise, and to keep you ahead of the curve without drowning you in it.
I checked whether your agent architecture is *technically real*. Three findings, each with
"what it is / why it matters / what we did."

**Finding 1 — Some frontmatter fields aren't standard Claude Code (high signal).**
- *What it is:* your draft used `effort:`, `memory:`, and `disallowedTools:` in the agent
  files. Claude Code's officially supported subagent fields are `name`, `description`,
  `tools`, `model` (and `color` in recent versions).
- *Why it matters:* a file with unrecognized fields can fail to load, and a helper that
  doesn't load is worthless. This is the difference between a clever idea and a working
  system.
- *What we did:* Zola rewrote the files to use only supported fields. The "high effort"
  and "read project notes first" instructions moved into the body of each file, where the
  model still follows them. **Please verify against your installed Claude Code version** —
  fields change between releases; this is the one thing to confirm live.

**Finding 2 — The read-only researcher needed a different fix.**
- *What it is:* you wanted `market-signal-researcher` to never write files, expressed as
  `disallowedTools: Write, Edit`.
- *Why it matters:* the reliable way to make a subagent read-only is to *list only* read
  tools in its `tools:` line, not to deny tools. If you don't list Write/Edit, it can't write.
- *What we did:* its tools are now `Read, Grep, Glob, WebSearch, WebFetch`. Read-only by
  construction.

**Finding 3 — Manually created agents don't load until restart.**
- *What it is:* the `@agent-name` mentions won't autocomplete the moment you save the files.
- *Why it matters:* people think the build failed when it just hasn't loaded.
- *What we did:* the runbook now states this plainly, and gives the fallback — delegate in
  plain language ("have the market-signal-researcher analyze...") if mentions aren't live yet.

**Business implication:** the architecture is sound and worth building. The risk was never
the strategy — it was three small technical details that would have made the files silently
fail. Fixed.

---

## 4. Carter — B2B / Premium Path

Corporate buys outcomes, not inspiration. Your draft's value ladder ended at "premium AI
systems offer." I added the tier that pays the most and that EmpowHER is uniquely built to
sell: **the workplace.**

- **The business case (not the vibe):** an ERG or L&D buyer doesn't want "AI inspiration."
  They want a repeatable system that gives their women employees leverage and gives the
  company a measurable training outcome. Frame the same agent build as a workshop: *"Build
  your first revenue agent"* delivered to an ERG, priced per cohort.
- **Where it sits on the ladder:** free template → $27 live build → cohort/team workshop →
  done-with-you AI systems engagement for the org.
- **What the video must seed for this to work:** one line that signals you work with
  organizations, not just individuals. Don't pitch corporate in the video — just plant
  that you do it, so the L&D lead who's watching knows to email you.

I'd loop in Symone for contract review and Maxine for pricing before any corporate tier
goes live, but the path is real and it's the highest-margin lane in this build.

---

## 5. Mark — Launch Sequence

I think in milestones, dependencies, and promotion windows. I turned the runbook from a
description into an executable sequence (see `runbooks/revenue-agent-runbook.md`). The
core fix: **build order matters.** You can't write the lead magnet before the offer
exists. The runbook now states each dependency so nothing gets built out of order.

Pre-publish asset checklist (so launch day isn't a scramble):
- [ ] `business-brief.md` finalized (brand + audience + single CTA locked)
- [ ] Four subagent files saved and Claude Code restarted
- [ ] Coordinator run completed → `outputs/revenue-agent-demo.md` exists
- [ ] Frannie's strategic second pass passed → `outputs/final-video-brief.md` exists
- [ ] Lead magnet (the Revenue Agent template) actually built and hosted
- [ ] Email capture + 5-email sequence loaded (Emily's lane)
- [ ] Title/thumbnail locked from the strategist's options
- [ ] Screen-recording beats marked in the script so the real build is visible

Sequence: publish video → drive to template → template delivers + triggers the 5-email
sequence → sequence invites to the $27 workshop → workshop graduates into premium / corporate.

---

## 6. Peggy — Editorial Pass

The reader owes you nothing. Earn every sentence. Three questions: would Ronnie finish it,
share it, feel seen by it? Here's where the draft lost her and what I changed.

- **Cut the hedging.** "Template, a workshop, OR a paid offer" makes the viewer choose.
  Viewers don't choose; they leave. One next step. The rest is the ladder, not the ask.
- **The audience was a list, now it's a person.** "Coaches, consultants, creators, service
  providers, and entrepreneurs" is five hats. Ronnie wears one. The brief now leads with
  her so every downstream agent writes *to* her, not *about* a category.
- **"Beginner-friendly without being basic" needed a guardrail.** I added it to the brief
  as a hard line: never condescend — she has a degree and a career; she's new to LLMs, not
  to work. That single sentence protects the tone across every asset.
- **Premium is in the restraint.** I pushed every agent file to cut filler and theory. The
  promise feels expensive when the words are spare and the build is real.

If a draft doesn't pass me, it doesn't go to Frannie. This one passes.

---

## 7. Zola — Agent Architecture Revision

This is my actual job: I don't write prompts, I build agent systems — interlocking named
agents that own a whole domain. I reviewed your four subagent specs against my standard and
revised the files. Every agent answers one question first: *what does this give her back —
time, mental space, or revenue?*

**What I kept:** your four-lane split is correct (research → offer → content → conversion).
That separation of concerns is exactly right. Keeping research read-only is a strong
instinct — it stops a researcher from "helpfully" writing files and muddying the work.

**What I revised (in `.claude/agents/`):**
- Fixed the frontmatter to fields that actually load (per Albert), so the team shows up.
- Made `market-signal-researcher` read-only the correct way — a curated `tools:` list.
- Wrote each agent's identity in EmpowHER's voice and tied it to a real teammate's
  discipline, so the sub-team isn't a stranger to your roster:
  - market-signal-researcher carries Rebecca's + Albert's standard
  - offer-architect carries Aaron's + Carter's standard
  - content-angle-strategist carries Vicky's + Peggy's standard
  - conversion-system-builder carries Emily's + Connie's + Mark's standard
- Added "read the shared project file first" to the three writing agents so each builds on
  the last decision instead of restarting it.

**My recommendation:** ship these four as a named EmpowHER sub-team ("the Revenue Pod").
Reusable, on-brand, and it slots under the team you already built. That's the move that
turns this from a one-video trick into a system you own.

---

## 8. Frannie — Strategic Second Pass (scoring + QA gate)

I review everything, and nothing ships without my sign-off. Here's my score of the build
as revised, on your seven criteria (1–5), with what to fix to reach a 4+.

| # | Criterion | Score | Note |
|---|-----------|:----:|------|
| 1 | Specificity of audience | 5 | Ronnie is now a person, not a list. (Peggy's fix.) |
| 2 | Urgency of pain | 4 | "Behind on AI" is urgent; sharpen with one concrete cost of waiting. |
| 3 | Believability of promise | 3 → fix | **Below 4.** Promise still rests on a claim, not proof. **Action:** lock D3 — show one real output on screen. |
| 4 | Strength of unique mechanism | 4 | "A named agent team, not a prompt" is a real, ownable mechanism. |
| 5 | Lead magnet pull | 4 | The template directly extends the video. Keep it one-click usable, not a PDF. |
| 6 | Natural sales path | 4 | Ladder is clean now that there's one CTA. (Aaron + Carter.) |
| 7 | Under-15-min viability | 3 → fix | **Below 4.** Four agents in 14 minutes is tight. **Action:** show two agents live in full, summarize the other two with pre-built output. |

**Sections I'd rewrite before publish (the two scoring under 4):**
1. **Believability** — add a 20-second "here's the real result this produced" moment near
   the top. Proof up front, not just at the end.
2. **Runtime** — restructure the demo so it fits 14 minutes honestly. Don't fake four full
   builds; show the system working and let the template carry the rest.

**QA gate:** the build is approved to proceed to the coordinator run **with those two fixes
flagged.** When `outputs/revenue-agent-demo.md` and `outputs/final-video-brief.md` are
generated, bring them back to me and I'll do final sign-off before anything publishes.

---

## The Upgraded Prompt (Aaron — *Instruction Upgrade* deliverable)

> Use this in place of the original. It names the brand, the single offer, and the proof
> before any building starts.

**Build EmpowHER's Revenue Agent sub-team as a real Claude Code subagent architecture.**
Treat me as a beginner and explain each file and command in plain English as you go.

Context is fixed in `business-brief.md`: creator EmpowHER, audience Ronnie (ambitious,
time-starved Black professional women and women entrepreneurs who know AI matters but
don't know what to build first), voice bold/affirming/premium/no-fluff.

Primary CTA: the free **Revenue Agent template** (one next step — workshop and corporate
offer sit behind it on the ladder). The video's credibility rests on showing **one real
output on screen** within the first 90 seconds.

Build four subagents (research → offer → content → conversion), keep research read-only,
use only supported frontmatter fields, and remind me to restart Claude Code so they load.
Then coordinate them to produce `outputs/revenue-agent-demo.md`, and run a scored second
pass into `outputs/final-video-brief.md`. Quality bar: no generic AI advice, no "AI saves
you time" filler; every section must connect to attention, leads, revenue, or leverage.

## The Merged Prompt (Aaron — *Optional Merge*, your voice + the upgrade)

> Your voice and business goal, kept. Just clearer, more specific, more buildable.

"I'm building EmpowHER's Revenue Operating System — a real Claude Code agent team, not a
chat trick — that turns one business idea into positioning, an offer, YouTube angles, a
lead magnet, and a follow-up sequence. Build it for Ronnie. Walk me through every step
like I'm new to this, because I'm learning while we build. The point isn't the tools — the
money is in the system, and I want to own the system. Sell one thing: the free Revenue
Agent template, with my $27 build workshop and corporate offer behind it. Show one real
result on screen early so it's proof, not hype. Build the four subagents, coordinate them
into a final video brief, score it, and tighten anything weak before we ship. Freedom is a
strategy. This is part of mine."

---

## What changed and why (summary)

| Area | Original | Revised | Who |
|------|----------|---------|-----|
| Creator/audience | FuturIQ, generic list | EmpowHER, Ronnie (one person) | Aaron, Peggy |
| Offer ask | Template *or* workshop *or* offer | One CTA (template) + ladder | Aaron, Peggy |
| Corporate revenue | None | ERG/L&D/team tier added | Carter |
| Agent frontmatter | `effort`/`memory`/`disallowedTools` | Supported fields only; read-only via `tools:` | Albert, Zola |
| Agent identity | Generic | Tied to real EmpowHER teammates | Zola |
| Runbook | Description | Sequence + dependencies + checklist | Mark |
| Proof | Implied | Required on-screen, first 90s | Frannie |
| Runtime | "under 15 min" | Honest 14-min structure (2 live, 2 summarized) | Frannie |

## What you run next

1. **Restart Claude Code** so the four files in `.claude/agents/` load. (Manually created
   agents only load on startup.)
2. Run the **coordinator prompt** from your original spec to generate
   `outputs/revenue-agent-demo.md`.
3. Run the **strategic second pass** to generate `outputs/final-video-brief.md`.
4. Bring both back to **Frannie** for final sign-off, and lock the two fixes she flagged
   (proof on screen; honest 14-minute structure) before you publish.

*Built by the EmpowHER AI Team. Reviewed by Frannie. Freedom is a strategy.*
