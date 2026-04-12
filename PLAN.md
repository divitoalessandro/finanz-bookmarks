# PLAN — finance-bookmarks

Static, German-language personal finance reference site for young Swiss residents. Hosted on GitHub Pages. No build process.

## Summary of decisions

**Look & tone**
- NZZ-style minimalism: serif headlines, black/white/ivory, strict typographic hierarchy, generous whitespace, no gradients, no card shadows, no decorative elements.
- German only.
- Target audience: young Swiss residents (20s–30s), already familiar with the basics.

**Home (`index.html`)**
- Curated directory hub. No hero, no featured lists, no author.
- Only site title, one-line description, three links (Ressourcen, Tools, Glossar).

**Resources (`resources.html`)**
- Grouped by format: Blogs, Podcasts, YouTube.
- Per entry: title + URL, 1–2 sentence German description, format tag.

**Tools (`tools.html`)**
- Curated links to external tools only. No self-hosted calculators.
- Grouped by tool type: Rechner, Vergleichsportale, Broker, Apps.
- Per entry: name + URL, 1–2 sentence German description, `Gratis` / `Kostenpflichtig` tag.

**Glossary (`glossary.html`)**
- A–Z alphabetical, `<dl>`/`<dt>`/`<dd>` semantics, letter anchors.
- Per entry: term + 1–3 sentence German definition.
- Target: ~50 terms for v1.

**Technical**
- Four HTML files at repository root, no subfolders, no build.
- Pico.css (classless) via CDN.
- Priority: maintainability — adding a new entry is a predictable copy-paste.

## Content structure per section

### `index.html`
```
<header>  title + one-line intro
<main>    3 links: resources.html, tools.html, glossary.html
<footer>  disclaimer
```

### `resources.html`
```
<section id="blogs">     Blogs    — <article> per entry
<section id="podcasts">  Podcasts — <article> per entry
<section id="youtube">   YouTube  — <article> per entry
```
Entry pattern:
```html
<article>
  <h3><a href="…">Titel</a> <small>[Blog]</small></h3>
  <p>Ein bis zwei Sätze.</p>
</article>
```

### `tools.html`
```
<section id="rechner">           Rechner
<section id="vergleichsportale"> Vergleichsportale
<section id="broker">            Broker
<section id="apps">              Apps
```
Entry pattern:
```html
<article>
  <h3><a href="…">Name</a> <small>[Gratis]</small></h3>
  <p>Ein bis zwei Sätze.</p>
</article>
```

### `glossary.html`
```
<nav>      letter anchors A–Z
<section>  per letter, containing <dl>
  <dt>Begriff</dt>
  <dd>1–3 Sätze auf Deutsch.</dd>
```

## Open items

1. **Resource list** — Swiss personal-finance blogs, podcasts, YouTube channels + German descriptions.
2. **Tool list** — per category (Rechner, Vergleichsportale, Broker, Apps) with URLs, descriptions, Gratis/Kostenpflichtig flags.
3. **Glossary content** — ~50 German terms with 1–3 sentence definitions (or approval of a first-draft list).
4. **Legal footer** — disclaimer wording; impressum if required for the Swiss audience.
5. **GitHub Pages repo + domain** — repo name, custom domain, `CNAME` if applicable.
6. **Favicon** and final `<title>` wording.

## Next steps

1. User supplies (or approves Claude-drafted) resource list → populate `resources.html`.
2. User supplies (or approves) tool list → populate `tools.html`.
3. User supplies (or approves) glossary terms → populate `glossary.html`.
4. Finalize footer disclaimer and impressum.
5. Push to GitHub Pages and verify the live URL.
