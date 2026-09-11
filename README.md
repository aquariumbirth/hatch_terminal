# HATCH_TERMINAL

Self-contained interactive documents on how records get made and how to make your own.

Live at **hatchterminal.com**. Static HTML, hand-written, served by GitHub Pages.
No framework, no CMS, no build step, no package manager, no dependencies.
Every document opens from a hard drive with no network and still works.

Built for one person first. If a stranger gets use out of it, that is a side effect,
not the brief.

---

## Structure

Three levels. There is no fourth. If a piece needs a sub-sub-category, that means
two wings are pretending to be one.

```
/
├── index.html                  root, links every piece
├── CNAME                       hatchterminal.com — do not delete
├── about/
├── jacket-ripper/              WING 01 — records, artists, scenes
├── studio-glow/                WING 02 — how it was done, and tools built from that
├── damage-done/                WING 03 — my rig, my room, dated
└── wet-film/                   WING 04 — film canon and lineage
```

Folder per piece, `index.html` inside, assets beside the piece that uses them.
Lowercase, hyphens, never spaces, never capitals.

Links in `index.html` are written as `wing/piece/index.html` rather than `wing/piece/`.
Slightly uglier, but a bare folder link does not resolve from a local drive, and
opening from a drive is the whole constraint. Find/replace to strip `index.html`
if that ever stops mattering.

---

## The routing test

Every idea sorts in two seconds on one question: **whose hands are on it?**

| Wing | Hands | What lives there |
|---|---|---|
| **JACKET_RIPPER** | Nobody's yet | Records, scenes, bin dives, discovery. Record-store clerk voice. |
| **STUDIO_GLOW** | Theirs | How a record got made, examined precisely. Plus instruments built from that research. |
| **DAMAGE_DONE** | Mine | First person, dated, gear-specific, includes what went wrong. |
| **WET_FILM** | The camera's | Film canon by documented lineage. Ballots, homages, citations — never received wisdom. |

Hybrids are not a problem — they are usually the best pieces. A hybrid files under
whichever hands open it.

Big names are fair game in DAMAGE_DONE when the piece is about chasing the sound.
They are never fair game as a ranked catalogue. Underground and fringe only;
this is not a greatest-albums site. WET_FILM is the one wing where canon titles are
allowed, and only because every entry has to carry the citation that earned it.

---

## Current inventory — 19 pieces

**JACKET_RIPPER (3)**
`the-deep-bin` · `the-deep-bin-vol-2` · `true-excavation`

**STUDIO_GLOW (5)**
`sonic-youth-tunings` · `king-of-limbs` · `two-rooms` · `sophtware-slump` ·
`remain-in-light`

**DAMAGE_DONE (6)**
`signal-path` · `spd-sx-pro` · `spd-sx-pro-kit-guide` · `the-sample-book` ·
`night-practice-book` · `night-practice-book-vol-2`

**WET_FILM (4)**
`72-genre-films` · `30-cult-transmissions` · `eloquent-ruin` · `nitrate`

**Unlisted (1)**
`studio-glow/mobile-meltdown` — Sonic Youth tunings as a playable instrument.
Reachable only from the quiet `Mobile_Meltdown` link in the footer, by choice.

**In the repo, delisted from the index (4)**
`damage-done/hx-stomp-xl` · `hx-stomp-xl-field-manual` · `nord-piano-88` ·
`launchkey-mk4-37`. Files still there, rows removed. Delete or relink.

---

## The index is an accordion

The root page shows four collapsed wing bands. Clicking a wing name expands it and
shuts whichever wing was open. JACKET_RIPPER opens on load so the page is not four
closed doors. All four collapsed fit one phone screen, which is the whole reason.

`#wet-film` and the other wing anchors are deep-linkable — the hash opens that wing
and scrolls to it, so the footer nav does not dead-end into a closed section.

---

## Adding a piece

1. `mkdir wing-name/piece-slug`, drop the finished HTML in as `index.html`.
2. Paste a row into the right wing in root `index.html`, renumber if inserting.
3. Bump the piece count in that wing's `.wcount` span.
4. Commit. Pages rebuilds in about a minute.

Row template:

```html
<a class="row" href="wing-name/piece-slug/index.html">
  <span class="n">01</span>
  <span>
    <h3>Title</h3>
    <p>One line. What is in it and what it costs the reader to find out.</p>
  </span>
  <span class="tag">Report</span>
</a>
```

Tags in use: Report · Instrument · Field manual · Ops manual · Dossier · Log.

Pieces written before the site existed have no way back to it. Each gets a thin
`.htbar` strip injected at the top of `<body>` — badge, wing link, scoped inline
styles with prefixed class names so it cannot collide with the document's own CSS.

---

## House rules

- **Every piece ends with something you can operate.** A read with no handoff has failed.
- **Confidence is labelled.** Confirmed, reported, transcribed, disputed. Fan lore is
  riddled with misattribution and the honest move is also the useful one. Where two
  sources contradict each other, print both and mark the clash. Never silently pick one.
- **Paraphrase, never reproduce.** Short attributed quotes only, one per source.
  **No lyrics, ever. No tablature, ever** — tab is a transcription of the composition,
  same category as sheet music. Tunings, gauges and credits are facts and are fair game.
- **No photographs anywhere.** Every texture is a CSS gradient or hand-written
  inline SVG. This is a constraint, not a shortage.
- **Purchases name what they replaced and what they cost in learning time.**
- **Write for six-months-from-now you**, who has forgotten why the fourth string
  was a .022 and what the clock problem actually was.

---

## Design tokens

Paper chrome, four dark rooms. Site furniture is strict instrument panel; content
blocks may break the grid, chrome never does. The underscore is the cursor — it blinks
inside every wing name, and trails the wordmark.

```
Paper      #F2EFE8    chrome: masthead, rails, footer
Panel      #DFDBD1    chrome fills
Ink        #16151A    type and hard rules
Blueprint  #1F4E7A    diagrams, technical drawing
Alarm      #D9541E    the single interaction colour

JACKET_RIPPER  #D6291E  red on #0D0B0B near-black, gritty
STUDIO_GLOW    #E9A23B  amber, #FFC66B glow, on #171009
DAMAGE_DONE    #C9A227  mustard panel; type #08192C dark blue + #14110A black
WET_FILM       #440F1D  dark wine; #FFF titles, #D3CDCF body
```

The wordmark is a black rectangle at top left, white type, small. It was oversized
display type until the unbroken word HATCH_TERMINAL broke the mobile masthead.
Its cursor cycles one colour per blink: red `#D6291E`, yellow `#F2C230`,
orange `#D9541E`, white. Wing cursors blink but hold their wing's colour.

DAMAGE_DONE is taped top and bottom — 9px hazard strips, 12px stripes, mirrored
angles, flush to both edges. Its header padding is 9px shy of the other wings so
the two strips do not make the band taller than its neighbours. All four collapsed
bands measure the same height.

WET_FILM texture is aged stock, gradients only: projector bloom, burnt vignette,
grain at three coprime periods so the stipple never tiles, scratches at irregular
spacing a fraction of a degree off vertical, unexposed border down both edges.

Type: Bricolage Grotesque (display) · IBM Plex Serif (long-form) · IBM Plex Mono (all chrome).
Motion is mechanical, not cinematic. Things latch and step. Nothing fades in on scroll.
`prefers-reduced-motion` honoured everywhere, which also pins every cursor solid.

---

## Deploy notes

- Pages serves from **`main`, `/ (root)`**. Was `claude-research` until the stale
  `main` stub was deleted and the live branch renamed. Check Settings → Pages before
  uploading; commits to any other branch change nothing live and look like a broken deploy.
- **Pages is case-sensitive. Windows is not.** This is the single most common way a
  link that works locally 404s in production.
- `CNAME` must survive every upload. Losing it drops the custom domain.
- Uploading a folder through the web UI merges, it does not replace. Dragging
  `studio-glow` adds to it and leaves the existing pieces alone.
- The repo is public because Pages requires it on the free tier. No license is granted.

## Known gaps

- Wing landing pages and `/about/` — linked from the index, not yet uploaded.
  `wet-film/` has no landing page either, so the WET_FILM breadcrumb on those four
  pieces currently goes nowhere.
- **`sophtware-slump` lists under STUDIO_GLOW but lives at `jacket-ripper/sophtware-slump/`.**
  It was relisted without moving the folder. Works, but breaks the rule that the path
  is the wing. Fix by moving the folder and updating one href.
- **`mobile-meltdown` is named for its footer link, not its contents.** Everything else
  in the repo is named for what is in it. It holds the Sonic Youth tuning instrument.
- A terminal-tech wing — real, deferred. No new wing opens until three actual drafts
  exist. Rooms with nothing in them make the whole house read as abandoned.
