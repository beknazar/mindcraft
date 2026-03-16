# Adding a Mentor to Mindcraft

Want to add your favorite thinker to Mindcraft? Here's how.

## Create the directory

```bash
mkdir -p mentors/your-mentor-name
```

Use lowercase, hyphenated names: `paul-graham`, `elena-verna`, `naval-ravikant`.

## Required files

### 1. `profile.md`
Short bio: who they are, what they're known for, why they matter. 5-10 lines.

### 2. `principles.md`
Their core beliefs, numbered 1-15. Each principle should have:
- A bold title
- A 1-2 sentence explanation
- Why it matters

Source these from their essays, talks, interviews. Use their actual words when possible.

### 3. `frameworks.md`
Decision frameworks they use repeatedly. These should be step-by-step:
- Name the framework
- Explain when to use it
- List the steps
- Give an example

### 4. `quotes.md`
10-15 iconic quotes with attribution (which essay, talk, or interview). Use `>` blockquote format.

### 5. `voice.md`
Style guide for channeling their voice:
- Tone (formal? casual? blunt?)
- Speaking patterns (short sentences? analogies? data?)
- Typical phrases they use
- What they would NEVER say
- How to channel them (5 bullet points)

### 6. `anti-patterns.md`
10 things they warn against. Each with:
- A title
- 2-3 sentence explanation of why it's bad

### 7. `sources.json`
Where to find their content for the refresh command:

```json
{
  "name": "mentor-name",
  "shortcut": "short",
  "sources": {
    "blog": { "url": "...", "type": "html|rss" },
    "youtube": { "search_queries": ["..."], "type": "transcript" },
    "twitter": { "handle": "@...", "type": "tweets" },
    "podcast": { "episodes": ["..."], "type": "transcript" },
    "community": { "type": "comments", "description": "..." }
  }
}
```

## Quality checklist

- [ ] Principles are sourced from real content (not made up)
- [ ] Quotes have attribution
- [ ] Voice guide is specific enough to distinguish from other mentors
- [ ] Anti-patterns reflect their actual opinions
- [ ] Sources are publicly accessible

## Submit a PR

1. Fork the repo
2. Add your mentor directory with all 7 files
3. Test it: `/mindcraft [shortcut]: test question`
4. Submit PR with "Add mentor: [Name]" as title

We'll review for accuracy and merge.
