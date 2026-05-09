# Eluu Documentation — voice and structure

This is product documentation for **business operators** — heads of sales, customer success, marketing, ops, founders. Not engineers. Most have never written a line of code and never will.

## Voice rules — non-negotiable

These are mistakes the previous draft made. Don't repeat them.

**Lead with what they can do, not with UI elements.**
- Bad: "The composer is the input area at the bottom..."
- Good: "When you talk to a colleague, you can attach files, pick the model, and pause anytime."

**No reference-page framing.**
- Don't write pages titled "X reference" or "anatomy of Y".
- Don't open with "This page covers all the controls in...".
- Operators don't read reference. They read for outcomes.

**Skip the trivia.**
- No placeholder text, char limits, validation rules, file-extension lists, state-machine tables, keyboard-shortcut tables.
- If it's a detail an engineer would put in a spec, leave it out.

**No internal naming.**
- Never say "the composer", "the panel-tab strip", "the wizard".
- Use plain English: "the chat", "the side menu", "creating a colleague".

**Show, don't list.**
- Bad: tables of state names with code-formatted values.
- Good: a sentence describing what happens.
- A real example beats a table every time.

**Concrete over abstract.**
- Bad: "Configure the colleague's role with a clear, descriptive sentence (40-180 chars)."
- Good: "Give them a real role — like a senior sales colleague who runs morning pipeline reviews and drafts follow-ups. The more concrete you are, the better they perform."

**Short pages.**
- 200-500 words is the target.
- If a page is over 600 words, you're probably writing reference, not docs.

## Terminology — UI names always

In docs, always use what the product calls things — never the code names.

| Use this | Not this |
|---|---|
| Colleague | Agent |
| Session | Task |
| Job | Reminder |
| Hard disk | Artifact storage / Hard Drive (UI says Hard Drive — use that. Internal code says artifacts) |
| Memory | Workspace state, accumulated context |
| Personal / Shared | PRIVATE / TEAM |
| Skill | (no alternate) |
| View | (no alternate) |
| Integration | (no alternate) |

## Eluu-specific style

- "Eluu", not "Eluu AI" in body copy. "Eluu AI" only in formal contexts.
- Never call colleagues "AI agents" or "AI assistants" — both signal commodity. Always "colleague".
- Use **Sofia** as the canonical example colleague (it's the platform default).
- Show what the colleague is replacing where useful — "what a sales operations SaaS would do".
- When showing a Slack flow, write the example mention: `@Sofia look at the last 20 emails...`.

## Mintlify components — use sparingly

- `<Card>` and `<CardGroup>` — overview pages and "next" links.
- `<Steps>` — only for actual procedures (creating something, connecting Slack).
- `<Note>`, `<Tip>`, `<Warning>` — sparingly. One per page max.
- `<Frame>` — around screenshots with captions.
- Avoid `<Tabs>` unless there are real variant flows.
- Avoid `<AccordionGroup>` except for FAQs.

## Confidential — never publish

- The Daytona / sandbox runtime
- The MCP Manager service
- The LiteLLM proxy
- Anything about "Claude Code" lineage (refer to the platform's own architecture only)
- Per-colleague pricing model (still internal)
- Workspace org URLs, internal API key shapes

## Frontmatter

```yaml
---
title: <sentence-case title>
description: <one line, max 160 chars, explains the value to a business operator>
icon: <lucide icon name>
---
```

Don't reference internal facts in the description. Make it readable on a search results page.

## When unsure

The authoritative source is `product/documentation/facts-ledger.md` for behaviour, and `strategy/positioning-and-pricing.md` for positioning. If a fact isn't there, ask Krishna. Don't invent.
