# finance-bookmarks

A static German-language personal finance reference site for young Swiss residents. Four HTML pages + Pico.css + a custom `styles.css` editorial layer. No build process. Hosted on GitHub Pages.

## Workflow & Behavior
- Always commit with conventional commit messages using /commit
- Search episodic memory at the start of each session for prior context
- Keep changes small and focused — one feature or fix per session
- Don't over-engineer. This is a hobby project. Simple > clever.
- After any correction, edit CLAUDE.md so the same mistake isn't repeated
- Ask before deleting files or making breaking changes

## Essential Commands
- **Run locally:** open `index.html` directly in a browser — no dev server
- **Deploy:** push to the GitHub Pages branch — GitHub serves the repo root
- **Format check:** none configured; keep HTML hand-formatted and readable

## Architecture Overview
- `index.html` — navigation hub; eyebrow + editorial H1 + numbered Roman index
- `resources.html` — curated Blogs / Podcasts / YouTube with a `.section-nav` anchor strip; external links open in new tabs and show a `↗` cue
- `tools.html` — curated Rechner / Vergleichsportale / Broker / Apps; same cue and section nav pattern as resources
- `glossary.html` — A–Z glossary authored as `<dl>`; inline JS transforms each `<dt>`/`<dd>` pair into a clickable `.term` button, wires up the `<dialog class="glossary-dialog">` modal, and powers the search field. Without JS the plain `<dl>` still renders as a readable fallback.
- `styles.css` — editorial layer on top of Pico: warm off-white palette, Fraunces serif, fade-up motion, hover reveals, bordered back button, modal styling
- `PLAN.md` — scope, content structure, open items
- `README.md` — project overview and getting started
- Every page links, in order: Google Fonts (Fraunces + JetBrains Mono) → Pico.css (classless) CDN → `styles.css`. The glossary page also ships a small inline `<script>` at the end of `<body>`. No build step.

## Semantic Class Vocabulary
The site is classless-first, but uses a small fixed set of semantic classes — do not invent new ones:
`.site-header`, `.site-footer`, `.site-nav`, `.eyebrow`, `.lede`, `.btn`, `.index`, `.alphabet`, `.section-nav`, `.tag`, `.letter`, `.glossary-search`, `.terms`, `.term`, `.glossary-dialog`, `.visually-hidden`.
Each sub-page starts its `<header>` with a `<nav class="site-nav">` linking Start / Ressourcen / Tools / Glossar; the current page is marked with `aria-current="page"`. Adding a new resource / tool / term copies an existing block 1:1. External article links must include `target="_blank" rel="noopener noreferrer"`.

## Critical Rules
- **All user-facing content must be in German.** No multilingual infrastructure.
- Never introduce a build process, bundler, or package manager without asking first.
- Never add JS dependencies or external `<script src="…">` tags without asking. The only allowed external resources are the Pico.css CDN and Google Fonts. The glossary page's inline `<script>` is the single exception and must stay vanilla + dependency-free.
- Never delete `PLAN.md`, `CLAUDE.md`, `styles.css`, or the `Let's go` placeholder without explicit user approval.
- Preserve the classless-first semantic HTML pattern — new content should fit `<section>` / `<article>` / `<dl>` plus the vocabulary above, not new class systems.
- Keep the NZZ minimalist aesthetic as the default: warm off-white background, Fraunces serif, a single wine-red accent, no gradients, no card shadows, no emoji. Discuss first if a change is needed.
