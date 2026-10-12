# You shoot. We edit.

**Concept project — website and product panels for a white-label post-production partner.**
Weddings, events and content: the studio shoots, the partner edits behind the studio’s own name.

![The playhead: final grade on the left, raw LOG on the right](docs/hero-playhead.gif)

**Live demo:** `https://<your-username>.github.io/you-shoot-we-edit/` · **Case study:** Behance — *add your link*

> Fictional brand. All imagery, people and footage are AI-generated for presentation purposes (video: Luma AI).
> Figures, prices, clients and testimonials are invented.

---

## The idea

One orange line — the **playhead** — carries the whole visual language. Everything left of it is finished, everything right of it is still raw camera LOG. It sweeps across the hero, drives the five production stages, marks “our time” in the workflow and reserved months in pricing, and appears in every panel. Orange always means *post-production in progress*.

![Portfolio cards with the same before/after playhead](docs/portfolio-before-after.gif)

## What’s in the repo

| Page | What it shows |
| --- | --- |
| [`index.html`](index.html) | Landing page: hero with RAW → FINAL playhead, pain, scroll-driven process, style guide, offer, workflow, portfolio, white-label credits (type your studio name), team, pricing levels, FAQ, contact |
| [`login.html`](login.html) | Client sign-in · password reset · email sign-in link |
| [`signup.html`](signup.html) | Account creation with password strength |
| [`panel.html`](panel.html) | Client panel: projects on a five-stage pipeline, review player with timecoded notes, upload, deliveries, style guide |
| [`editor.html`](editor.html) | Edit suite (team, dark mode): queue, job workspace with client notes and a send-to-client checklist, board, capacity |
| [`admin.html`](admin.html) | Admin: capacity vs bookings, job assignment, clients & partnership levels, team access, billing |
| [`case.html`](case.html) | The full case study as 23 boards at 1400 px (challenge, persona, landscape, strategy, brand idea, moodboard, identity, applications, IA, journey, wireframes, design system, screens, mobile, panels, credits) — each board exports as one Behance image |
| [`figma-plugin/`](figma-plugin) | Rebuilds every screen in Figma (auto layout, color & text styles, button components) plus Behance presentation boards |

Flow: `index.html` → *Client login* → `login.html` → any valid email + password → `panel.html`.

## Design system

| Token | Value | Use |
| --- | --- | --- |
| Paper | `#EAE4DA` | Background |
| Ink | `#1A1714` | Text, primary buttons |
| Night | `#0E0D0C` | Dark sections, edit suite |
| Muted | `#5F584F` | Secondary text |
| Hairline | `#D3CBBF` | Rules and borders |
| Playhead | `#E5532A` | Only for “post-production in progress” |

Type: **Geist** for words, **Geist Mono** for everything that belongs to the edit suite — timecode, labels, metadata.

## Run locally

```bash
python3 -m http.server 8000
# open http://localhost:8000
```

## Publish on GitHub Pages

Settings → Pages → *Deploy from a branch* → `main` / `(root)`.

## Figma

Figma desktop → Plugins → Development → *Import plugin from manifest…* → `figma-plugin/manifest.json`, then run it in an empty file (20–60 s). The last page, **Behance case**, contains the cover (808×632) and the same 23 boards as `case.html` at 1400 px, ready to export at 2x.

## Tech notes

- Plain HTML, CSS and JavaScript — no build step, no framework. Each page is one self-contained file.
- The hero video is a single stacked file (FINAL on top, RAW below) drawn to `<canvas>`, so both halves stay frame-accurate.
- Scroll-driven stages, hover/touch scrubbing, keyboard focus states and `prefers-reduced-motion` support.
- Panels run on in-browser demo data; there is no backend.

## License

Code: MIT (see `LICENSE`). Images and video are AI-generated placeholders for this concept and are not covered by the code license.
