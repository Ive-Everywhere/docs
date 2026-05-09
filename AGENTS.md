# Eluu Documentation — agent instructions

## About this project

- This is the Eluu product documentation site, built on [Mintlify](https://mintlify.com).
- Pages are MDX files with YAML frontmatter.
- Navigation lives in `docs.json`.
- Run `mint dev` to preview locally.
- Run `mint broken-links` to check links.

## Terminology — UI names, always

Eluu's code uses some different names from the product UI. **In docs, always use the product UI name.**

| Use this (UI) | Not this (code) |
|---|---|
| Colleague | Agent |
| Job | Reminder |
| Session / chat | Task |
| Team | Workspace |
| View | (no alternate) |
| Hard Drive | Artifact storage |
| Skill | (no alternate) |
| Tools | Integrations directory |
| Personal | PRIVATE visibility |
| Shared | TEAM visibility |
| Mine / Shared | The visibility filter (never "All") |

The glossary page at `/concepts/glossary` is the single source of truth — link to it on first use of any non-obvious term.

## Style preferences

- Active voice, second person (`you`).
- One idea per sentence. Cut filler.
- Sentence case headings (`Create your first colleague`, not `Create Your First Colleague`).
- **Bold** for UI elements: Click **Settings**, then choose **People**.
- `Code formatting` for file names, slash commands, paths, and field names.
- Don't use emojis unless the user explicitly asks.
- Don't say "simply", "just", "easy", or "powerful" — they don't help the reader and they age badly.
- Numbers in body copy: spell out one to nine, digits for 10+. Exceptions: limits, prices, durations.
- For lists of three or fewer items, use prose; four or more, use a list.

## Eluu-specific style rules

- **Product = Eluu, not "Eluu AI"** in body copy. Use "Eluu AI" only in formal/legal contexts.
- When referring to the LLM provider, say "Claude" — not "the model" — unless contrasting providers.
- Refer to the agent doing work as "your colleague" once the colleague has been introduced. First reference can be "an Eluu colleague" or "your colleague Sofia".
- Slash commands: always render as `code`, with the leading slash. Example: `/research`.
- Don't say "AI agent" or "AI assistant" — that's positioning we explicitly avoid (see strategy/competitive-landscape.md).
- When showing a state machine (pause/resume, task status), use a small table not prose.
- Show the colleague's name in toast/error copy examples — use **Sofia** as the canonical example colleague (matches the product's onboarding default).

## Mintlify components to prefer

- `<Card>` and `<CardGroup>` for entry-point grids on overview pages.
- `<Steps>` for procedural walkthroughs (sign up, connect an integration, etc.).
- `<Tabs>` for variant flows (e.g. password vs Google sign-in).
- `<Note>`, `<Tip>`, `<Warning>` sparingly — never two in a row.
- `<Frame>` around all screenshots, with a caption.
- `<AccordionGroup>` for FAQs only.
- `<CodeGroup>` for showing the same call across multiple languages (rare in user docs).

## Content boundaries

- Document only shipped features. If a feature exists in the database but has no UI yet (e.g. the public Skills registry), do not document it.
- Internal-only surfaces are out of scope: `/api/internal/*`, `/api/dev/billing/*`, the credential pool, MCP Manager, LiteLLM proxy.
- Do not reference the source-code names of services (`task-service.ts`, `daytona-service.ts`) in user docs.
- Don't document scoreboard targets, growth metrics, or company strategy.
- **Confidential — never publish:** the platform sandbox infrastructure, the agent runtime architecture (Daytona/sandbox/MCP Manager), internal API key formats. The "How Eluu works under the hood" page is allowed but stays at the conceptual level.

## When you're not sure of a fact

The authoritative source is `product/documentation/facts-ledger.md` in the agentic-ops chief-of-staff workspace. It has the exact copy, validation, options, and limits as shipped. If a fact isn't in the ledger, read the source file — don't invent.

## Page template

Every page should:

1. Open with one sentence stating what the page covers and who it's for.
2. Include a `<Note>` at the top if there's a gotcha that affects the whole page.
3. End with a `## Next` section linking to 2-3 related pages.
4. Have YAML frontmatter:
   ```yaml
   ---
   title: <sentence-case page title>
   description: <one-line SEO description, 50-160 chars>
   icon: <lucide icon name>
   ---
   ```
