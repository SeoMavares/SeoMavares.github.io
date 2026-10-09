# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Users

Businesses, founders and small teams that need custom software built: an Android
app, a backend service, a web panel, or the three together. They arrive from
GitHub, a referral, or a search, usually on a phone or a laptop, and they are
deciding whether this developer can be trusted with a real project.

Secondary audience: technical reviewers who check the public repositories before
a conversation happens.

## Product Purpose

A one-page portfolio that shows real, running work so a client can decide to
start a conversation. Success is a visitor who understands what is offered,
sees evidence of it, and clicks through to GitHub.

## Positioning

One developer who ships the whole product: the Android app, the backend and the
web surface, with the source open where it can be. The public work is not a demo
or a tutorial reproduction: `miwayomi` is used by strangers, has stars,
forks and issues from outside the account.

## Operating Context

The visitor scans in seconds: what is offered, what has been built, what happens
next. Proof has to be legible without reading paragraphs. Technical depth is
available but must never be the first thing asked of a non-technical buyer.

## Capabilities and Constraints

Confirmed capabilities, all evidenced by the repositories on the account:

- Android nativo: Kotlin, Jetpack Compose, Material 3, ML Kit, Room, DataStore,
  foreground services, custom launcher as the system home app.
- Backend y APIs: Kotlin and Ktor on the JVM, Node.js services, SQLite, REST
  design, OAuth2 against Firebase HTTP v1.
- Web: HTML, CSS and JavaScript without frameworks, TypeScript, Blade.
- Streaming y datos: HLS and DASH with manifest rewriting, RSS and Atom
  ingestion, document pipelines (PDF, DOCX).
- IA aplicada: provider-agnostic chains with DeepSeek, Gemini and any
  OpenAI-compatible endpoint, on-device models as the offline fallback.
- Herramientas: Go, Docker, Gradle with ABI splits and R8, CI that publishes
  multi-architecture images.

Constraints:

- The site is a single `index.html`: no build step, no framework, no bundler.
- Dark only. The user asked for a black background for this surface.
- Contact channel is ForoBeta direct messages
  (`https://forobeta.com/direct-messages/add?to=seomavares`). No email, phone
  or other social account was supplied, so none may appear. GitHub is a place to
  read the code, never the way to get in touch.
- There are no product screenshots, client logos or testimonials in evidence.
  Mock product UI and invented proof are prohibited.

## Brand Commitments

- Name: SeoMavares.
- The only real identity asset in evidence is the LinguaLens launcher icon: a
  globe with meridians, in `#1B5E9B` with `#4FC3F7`. It belongs to that project,
  not to the studio: it may appear as project evidence, never as the site's own
  mark or palette.
- The user's binding instruction for this surface: black background, high-end
  feel, client-facing tone.
- Clarity beats concept. The user rejected a ledger-themed build as "confusing
  for a client". The page must be understood without explanation: conventional
  structure, obvious hierarchy, no metaphor carrying the layout.
- No numbers in the copy. The user asked to drop counts and quantities from the
  page: no number of projects, no stars, no language totals, not even the year
  in the footer. Claims stay qualitative but concrete.

## Evidence on Hand

Public, linkable:

- `github.com/SeoMavares/miwayomi`: Kotlin and Ktor on JVM 21, Apache-2.0,
  29 stars, 2 forks, open issues, GHCR images, Docker Compose. Loads
  Tachiyomi/Aniyomi extensions by converting DEX with dex2jar, repairing the
  bytecode with JarFixer, and loading classes through a child-first
  ClassLoader.
- `github.com/SeoMavares/lingua-lens-app`: Android translation app and launcher,
  Kotlin and Compose, ML Kit on-device engines, documented architecture in
  Spanish under `docs/`.

Private, no public link may be shown: a community management system, IPTV
streaming suites (web and Android), live-data admin panels, and institutional
websites. These may be described by domain, never by client name.

Absent and not to be fabricated: screenshots, testimonials, client names,
pricing, delivery timelines, team size beyond one developer.

## Product Principles

1. Evidence over adjectives. Every claim on the page points at something that
   exists and can be opened.
2. The work leads. The interface recedes behind the artifacts.
3. Speak to the decision the client is making, not to the developer's résumé.
4. Never invent proof: no fake screenshots, no fake numbers, no fake logos, no
   invented clients.
5. One clear next step: the ForoBeta message, stated once.

## Accessibility & Inclusion

WCAG AA contrast for body text and controls, AA for large text. Every
interactive element reachable and visible by keyboard. Motion respects
`prefers-reduced-motion`.
