# finance-bookmarks

A static German-language personal finance reference site for young Swiss residents. Four HTML pages + Pico.css via CDN. No build process. Hosted on GitHub Pages.

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
- `index.html` — navigation hub; title + one-line intro + three links
- `resources.html` — curated Blogs / Podcasts / YouTube (grouped by format)
- `tools.html` — curated external Rechner / Vergleichsportale / Broker / Apps (grouped by tool type)
- `glossary.html` — A–Z German glossary using `<dl>`/`<dt>`/`<dd>` semantics
- `PLAN.md` — scope, content structure, open items
- `README.md` — project overview and getting started
- Each page links Pico.css (classless) via CDN in `<head>`. No JS. No build step.

## Critical Rules
- **All user-facing content must be in German.** No multilingual infrastructure.
- Never introduce a build process, bundler, or package manager without asking first.
- Never add JS dependencies or external scripts beyond the Pico.css CDN link without asking.
- Never delete `PLAN.md`, `CLAUDE.md`, or the `Let's go` placeholder without explicit user approval.
- Preserve the classless semantic HTML pattern — new content should fit `<section>` / `<article>` / `<dl>`, not new class systems.
- Keep the NZZ minimalist aesthetic as the default: no gradients, no card shadows, no emoji, no decorative elements. Discuss first if a change is needed.
