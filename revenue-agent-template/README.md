# The Revenue Agent Template

**Drop your business idea in. Get positioning, an offer, YouTube angles, a lead magnet, and a follow-up sequence out — in one run. Built on Claude Code. No prompt engineering degree required.**

This is the exact system from the video. It is a small team of AI agents that hand work to
each other, one after another. You run one command, and it produces five business assets
built off a single idea.

---

## Beginner Mode: what's actually in this folder

You don't need to understand any of this to use it. But here's what each piece is, in
plain English:

- **`MY-BUSINESS.md`** — the only file you edit. You paste your business idea here. Think
  of it as the form you fill out before the team gets to work.
- **`.claude/commands/revenue-agent.md`** — the "go" button. In Claude Code you type
  `/revenue-agent` and this runs the whole team in order.
- **`.claude/agents/`** — your five hired helpers, each with one job. You never open these.
  They just do their part and pass the work down the line:
  1. **offer-architect** — turns your idea into sharp positioning and an offer
  2. **content-strategist** — turns the offer into YouTube angles and hooks
  3. **lead-magnet-builder** — turns the best angle into a free lead magnet
  4. **follow-up-architect** — turns the lead magnet into a 5-email sequence
  5. **positioning-validator** — checks the whole thing for what would lose your buyer
- **`revenue-agent-output.md`** — this file doesn't exist yet. The team *creates* it for
  you when you run the command. That's your finished work.
- **`example-run.md`** — a real example so you can see what "good" looks like before you start.

---

## Setup (one time, about 10 minutes)

**Step 1 — Install Claude Code.**
Claude Code is a free app from Anthropic that runs in your computer's "terminal" (a plain
text window). Go to **https://www.claude.com/claude-code** and follow the install steps for
your computer (Mac or Windows). When you can open a terminal and type `claude` and it
starts, you're done with Step 1.

> A "terminal" is just a window where you type commands instead of clicking buttons. It
> looks technical. It is not code. You will forget it's there in ten minutes.

**Step 2 — Connect your account.**
The first time you run `claude`, it will walk you through signing in. A Claude subscription
(Pro or Max) or API access covers it. Just follow the prompts on screen.

**Step 3 — Put this folder where you'll work.**
Move this entire `revenue-agent-template` folder somewhere easy to find (your Desktop is
fine). This folder *is* your project. Everything the team needs is already inside it.

**Step 4 — Open it in Claude Code.**
Open your terminal, then point it at this folder and start Claude Code:

```
cd ~/Desktop/revenue-agent-template
claude
```

(`cd` means "change directory" — it just tells the terminal which folder to work in.)

**Step 5 — Let the team load.**
The five helpers only load when Claude Code starts. Since you just started it inside this
folder, they're ready. If you ever add or change a helper, quit and restart Claude Code.

---

## How to run it (every time, about 5 minutes)

1. Open `MY-BUSINESS.md` and fill in your idea. There are five short questions. Don't
   overthink it — rough answers are fine. The team sharpens them.
2. In Claude Code, type:

   ```
   /revenue-agent
   ```

3. Hit enter. Watch the team work. When it's done, open **`revenue-agent-output.md`** —
   that's your positioning, offer, three YouTube angles, lead magnet brief, and 5-email
   sequence, all built off your one idea.

That's it. Run it again any time your offer changes.

---

## What this template does NOT do (read this — it matters)

This template produces the **material**. It does not exercise **judgment** on the material.
That distinction is the whole game.

It **cannot** tell you:

- Whether your **niche is too broad** ("entrepreneurs" is not a niche — it's a phone book).
- Whether your offer **reads premium** or reads like every other AI coach online.
- **Which of the three hooks** is the one you should actually lead with for *your* audience.

Those are judgment calls, and they're the difference between a system that makes money and
content you're proud of that nobody buys. When you run this and something feels off — the
niche feels wide, the offer sounds generic, none of the hooks feel like *you* — that is not
a bug. **Write those questions down.** That's exactly the gap we work through together,
live, in the **$27 monthly "Come Build With Me" workshop**. The template gives you the
structure. The workshop gives you the judgment.

---

## Troubleshooting

- **`/revenue-agent` doesn't show up when I type it.** Quit Claude Code and restart it from
  *inside* this folder (Step 4). Commands and helpers only load on startup.
- **It asks me about my business instead of just running.** Make sure `MY-BUSINESS.md` is
  filled in and saved. The command reads from that file.
- **The output feels generic.** Good — that's the signal, not a failure. See "What this
  template does NOT do" above. Bring it to the workshop.

*Built by EmpowHER. The money is not in the tool. The money is in the system.*
