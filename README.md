# Mindcraft

**Your AI Board of Directors.**

Mindcraft is a Claude Code skill that assembles a personalized advisory board from the world's best startup, growth, and product minds. It reads your project, recommends the right advisors, and runs an interactive brainstorming session where they debate, disagree, and build on each other's ideas — just like a real board meeting.

## Install

```bash
git clone https://github.com/beknazar/mindcraft.git ~/.claude/skills/mindcraft
```

## The Board

This is Mindcraft's core feature. Run `/mindcraft board` and watch it work:

1. **Reads your project** — analyzes your code, README, git history, and product context
2. **Recommends 3 advisors from anyone** — not limited to installed mentors. It picks the best combination for your specific project, whether that's PG + Elena + Levels, or Sam Altman + Julie Zhuo + Patrick Collison. Installed mentors get their full verified knowledge base; others are channeled from Claude's knowledge of their public work.
3. **Opens the session** — each board member gives their initial read on your product
4. **Asks you what to focus on** — presents focus areas via interactive questions
5. **Runs discussion rounds** — board members debate, disagree, react to each other
6. **Checks in with you** — after each round, asks if you want to go deeper or pivot
7. **Synthesizes action items** — delivers a prioritized plan from the collective wisdom

```
/mindcraft board
```

The board members don't just take turns talking. They challenge each other. PG might push back on Elena's growth loop suggestion. Levels might call both of them out for overcomplicating it. Real tension, real insights.

You can also pick your own board:

```
/mindcraft board pg elena levels
```

## Other Modes

### Advisory — Quick Questions
```
/mindcraft pg: should I add a freemium tier?
/mindcraft elena: how do I build a growth loop for my SaaS?
/mindcraft levels: should I hire my first employee?
```

Get a single mentor's perspective on a specific question, delivered in their authentic voice with relevant principles and quotes.

### Roast — Brutal Critique
```
/mindcraft roast "AI-powered CRM for SMBs"
/mindcraft roast https://myapp.com
```

Every mentor critiques your idea through their unique lens. No sugarcoating. Ends with a synthesis and top 3 action items.

### Strategy — Roundtable Discussion
```
/mindcraft strategy: we have 2k users but growth is flat
```

A structured roundtable where mentors give their takes, respond to each other, and deliver a prioritized action plan.

### Learn — Crash Course
```
/mindcraft learn elena --topic growth-loops
/mindcraft learn pg
```

A mini-masterclass in any mentor's thinking: who they are, their top principles, framework walkthrough, common mistakes, and recommended reading.

## Mentors

### Paul Graham (`pg`)
Co-founder of Y Combinator. Essayist. Funded Dropbox, Airbnb, Stripe, Reddit, Coinbase. Author of "Founder Mode" (2024), "Writes and Write-Nots" (2025), and 200+ essays on startups and thinking.

**Domain:** Startups, product-market fit, fundraising, building things people want.

### Elena Verna (`elena`)
Head of Growth at Lovable ($200M ARR in 13 months, $6.6B valuation). Previously CMO at Miro, SVP Growth at SurveyMonkey, Interim Head of Growth at Amplitude. Creator of the Motions x Levers growth framework at Reforge.

**Domain:** Product-led growth, growth loops, organic social, creator-led growth, reverse trials.

### Pieter Levels (`levels`)
Solo founder. $420K/month revenue. Zero employees. 80% profit margins. $40/month VPS runs everything. Built Nomad List, Photo AI, Remote OK, Interior AI, and Fly.pieter.com ($0 to $1M ARR in 17 days, built in 3 hours with AI).

**Domain:** Shipping fast, bootstrapping, indie hacking, boring tech stacks, building in public.

## Add Your Own Mentor

Create a new directory in `mentors/` with these files:

```
mentors/your-mentor/
  profile.md          # Who they are
  principles.md       # Core beliefs (numbered)
  frameworks.md       # Decision frameworks
  quotes.md           # Key quotes with attribution
  voice.md            # How they talk/write
  anti-patterns.md    # What they warn against
  sources.json        # Content sources for refresh
```

See [`docs/adding-a-mentor.md`](docs/adding-a-mentor.md) for the full guide.

PRs welcome. Add mentors like:
- **Design:** Dieter Rams, Jony Ive, Julie Zhuo
- **Engineering:** DHH, Kelsey Hightower, Dan Abramov
- **Growth:** Andrew Chen, Casey Winters, Lenny Rachitsky
- **Founders:** Naval Ravikant, Tobi Lutke, Patrick Collison
- **AI:** Andrej Karpathy, Dario Amodei, Sam Altman

## How It Works

Mindcraft ships with pre-curated knowledge bases for each mentor — their principles, frameworks, quotes, voice patterns, and anti-patterns, extracted from their actual blogs, interviews, podcasts, and social posts. Every quote is sourced and verified.

When you invoke a mode, Claude reads the relevant mentor files and applies their specific thinking to your situation. It's not generic advice — it's what PG, Elena, or Levels would actually say, based on their documented philosophy.

### Refresh (keep it current)
```
/mindcraft refresh paul-graham
/mindcraft refresh --all
```

Fetches latest content from blogs, YouTube transcripts, HN API, and podcast feeds. No paid APIs required.

## Examples

See the [`examples/`](examples/) directory for full output examples of each mode, including a complete interactive board session.

## License

MIT
