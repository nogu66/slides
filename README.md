# Slidev Presentations

This directory contains technical presentation slides created with [Slidev](https://sli.dev/).

## Directory Structure

```
Slidev/
├── presentations/          # All presentation slide decks
│   └── [topic-slug]/      # Each presentation in its own folder
│       ├── slides.md      # Main slides file
│       └── images/        # Presentation-specific images
└── .claude/
    └── agents/
        └── slidev-creator.md  # Agent for creating Slidev slides
```

## Creating a New Presentation

Presentations are created through the `content-creator` skill or directly via the `slidev-creator` agent:

```bash
# Using the content-creator skill (creates both article + slides)
# Simply ask Claude: "Create content about [topic]"

# Or create slides only by delegating to slidev-creator agent
```

## Slidev Setup

To preview slides locally:

```bash
# Install Slidev globally (one time)
npm install -g @slidev/cli

# Navigate to presentation directory
cd presentations/[topic-slug]

# Start the dev server
slidev slides.md
```

## Presentation Guidelines

Each presentation should:
- Focus on solving a specific problem (aligned with Zenn article if exists)
- Use visual storytelling over text-heavy slides
- Include code examples that are readable and focused
- Have clear narrative flow: Problem → Solution → Implementation → Results
- End with CTA linking to detailed Zenn article (if available)

## Integration with Zenn

Slidev presentations complement Zenn articles:
- **Articles**: Deep technical explanations with complete code
- **Slides**: Visual overview for presentations and talks

When both exist for the same topic, slides should reference the article for deeper exploration.

## Common Slidev Commands

```bash
# Start dev server (auto-reload on changes)
slidev slides.md

# Export to PDF
slidev export slides.md

# Export to single-page HTML
slidev build slides.md --base /[topic-slug]/

# Open presenter mode (with notes)
# Press 'o' when presentation is running
```

## Slide Format

Slides use Slidev's extended Markdown format:
- Frontmatter for configuration
- `---` to separate slides
- Built-in layouts: `cover`, `center`, `image-right`, `two-cols`, etc.
- Vue components for interactivity
- Icons via UnoCSS

See `.claude/agents/slidev-creator.md` for detailed formatting guidelines.

## Topics

Presentations in this repository cover:
- TRAE AI Editor features
- React Native development
- AI-assisted coding techniques
- Developer productivity tools
- Mobile development best practices

## Author

**nogu**
- X (Twitter): [@_nogu66](https://x.com/_nogu66)
- Zenn: [https://zenn.dev/nogu](https://zenn.dev/nogu)
