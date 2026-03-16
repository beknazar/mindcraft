# Mindcraft

**Your AI Board of Directors.**

Mindcraft is a Claude Code skill that assembles a personalized advisory board for your project. It reads your codebase, figures out what you're building, and recommends the right advisors from anyone in the world, whether that's Patrick Collison for developer tools, Andrej Karpathy for AI products, Julie Zhuo for design, or Elena Verna for growth.

Then it runs an interactive brainstorming session where they debate, disagree, and build on each other's ideas.

## Install

```bash
git clone https://github.com/beknazar/mindcraft.git ~/.claude/skills/mindcraft
```

## The Board

This is Mindcraft's core feature. Run `/mindcraft board` and watch it work:

1. **Reads your project** -- analyzes your code, README, git history, and product context
2. **Recommends 3 advisors from anyone** -- not limited to a fixed list. It picks the best combination for your specific project. Building a voice AI startup? It might recommend Jeff Dean, Patrick Collison, and Tomasz Tunguz. Building a consumer app? Maybe Julie Zhuo, Andrew Chen, and Naval Ravikant. The board is assembled from scratch every time based on what you actually need.
3. **Opens the session** -- each board member gives their initial read on your product
4. **Asks you what to focus on** -- presents focus areas via interactive questions
5. **Runs discussion rounds** -- board members debate, disagree, react to each other
6. **Checks in with you** -- after each round, asks if you want to go deeper or pivot
7. **Synthesizes action items** -- delivers a prioritized plan from the collective wisdom

```
/mindcraft board
```

The board members don't just take turns talking. They challenge each other. One might push back on another's suggestion. A third might call both of them out for overcomplicating it. Real tension, real insights.

You can also pick your own board:

```
/mindcraft board "Andrej Karpathy" "Patrick Collison" "Elena Verna"
```

## Example Mentors (ships with 3)

Mindcraft ships with deep, verified knowledge bases for 3 mentors as examples. These include sourced quotes, numbered principles, decision frameworks, voice guides, and anti-patterns, all extracted from real essays, interviews, podcasts, and tweets.

### Paul Graham (`pg`)
Co-founder of Y Combinator. 200+ essays. Funded Dropbox, Airbnb, Stripe.

### Elena Verna (`elena`)
Head of Growth at Lovable ($200M ARR in 13 months). Creator of the Motions x Levers framework.

### Pieter Levels (`levels`)
Solo founder. $420K/month. Zero employees. Built Photo AI, Nomad List, Fly.pieter.com.

For these 3, the board draws from their full verified knowledge base. For any other advisor, it channels them from Claude's knowledge of their public work, talks, and writing.

## Other Modes

### Advisory -- Quick Questions
```
/mindcraft pg: should I add a freemium tier?
```

### Roast -- Brutal Critique
```
/mindcraft roast "AI-powered CRM for SMBs"
```

### Strategy -- Roundtable Discussion
```
/mindcraft strategy: we have 2k users but growth is flat
```

### Learn -- Crash Course
```
/mindcraft learn elena --topic growth-loops
```

## Add Your Own Mentor

Want to add a deep knowledge base for any advisor? Create a folder in `mentors/`:

```
mentors/your-mentor/
  profile.md
  principles.md
  frameworks.md
  quotes.md
  voice.md
  anti-patterns.md
  sources.json
```

See [`docs/adding-a-mentor.md`](docs/adding-a-mentor.md) for the full guide. PRs welcome.

## How It Works

The board feature uses two tiers of knowledge:

**Installed mentors** (ships with PG, Elena, Levels) have full verified knowledge bases with sourced quotes, frameworks, and voice guides. You can add more by creating mentor folders.

**Any other advisor** is channeled from Claude's broad knowledge of their public work. The board can recommend anyone, whether they have an installed knowledge base or not. Jeff Dean, Sam Altman, Julie Zhuo, DHH, Naval, Karpathy, whoever fits your project best.

### Refresh (keep installed mentors current)
```
/mindcraft refresh paul-graham
/mindcraft refresh --all
```

## Examples

See [`examples/`](examples/) for full output examples, including a complete interactive board session.

## License

MIT
