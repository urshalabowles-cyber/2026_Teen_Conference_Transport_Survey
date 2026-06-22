# Revenue Agent Runbook

This project uses Claude Code subagents to turn one business idea into a monetizable
content system. Mark (Product Launch Specialist) revised the workflow into a sequence with
clear dependencies so nothing gets built out of order.

## Workflow

1. The main Claude Code session acts as coordinator.
2. `market-signal-researcher` analyzes demand, psychology, and opportunity (read-only).
3. `offer-architect` turns the signal into positioning and an offer.
4. `content-angle-strategist` turns the offer into a YouTube concept and retention map.
5. `conversion-system-builder` creates the lead magnet, CTA, and follow-up sequence.
6. The coordinator combines the outputs into `outputs/revenue-agent-demo.md`.

## Dependencies (build order matters)

- Offer cannot be built before the signal is scored. (3 needs 2.)
- Titles and hooks cannot be locked before the offer is chosen. (4 needs 3.)
- Lead magnet and CTA cannot be written before the video concept exists. (5 needs 4.)
- The final file is assembled last. (6 needs 2–5.)

## Coordinator rules

- Do not let one agent do every job.
- Keep research separate from offer architecture.
- Keep content strategy separate from conversion.
- Ask for evidence and scores before finalizing.
- Every final output must connect to a monetization path.

## After creating the files

Summarize what was created and remember: **Claude Code must be restarted for manually
created subagent files to load.** New `.claude/agents/*.md` files are only picked up when
Claude Code starts. If `@agent-` mentions do not autocomplete, restart, or delegate in
plain language (see the runbook note below).

## EmpowHER team mapping (who owns each lane)

These four subagents are a new sub-team that slots into the existing EmpowHER roster.
For human accountability, each maps to a teammate's discipline:

- `market-signal-researcher` → Rebecca (research) + Albert (signal vs. noise)
- `offer-architect` → Aaron (strategy) + Carter (premium / corporate path)
- `content-angle-strategist` → Vicky (hooks) + Peggy (reader experience)
- `conversion-system-builder` → Emily (email) + Connie (community) + Mark (launch)

Frannie reviews the final output before it ships. Nothing ships without her sign-off.
