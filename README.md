[README.md](https://github.com/user-attachments/files/31515811/README.md)
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
└── damage-done/                WING 03 — my rig, my room, dated
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

Hybrids are not a problem — they are usually the best pieces. A hybrid files under
whichever hands open it.

Big names are fair game in DAMAGE_DONE when the piece is about chasing the sound.
They are never fair game as a ranked catalogue. Underground and fringe only;
this is not a greatest-albums site.

---

## Current inventory — 18 pieces

**JACKET_RIPPER (4)**
`the-deep-bin` · `the-deep-bin-vol-2` · `true-excavation` · `sophtware-slump`

**STUDIO_GLOW (6)**
`sonic-youth-tunings` · `king-of-limbs` · `two-rooms` · `the-sample-book` ·
`night-practice-book` · `night-practice-book-vol-2`

**DAMAGE_DONE (8)**
`signal-path` · `hx-stomp-xl` · `hx-stomp-xl-field-manual` · `spd-sx-pro` ·
`spd-sx-pro-kit-guide` · `nord-piano-88` · `launchkey-mk4-37` · `pyramid-song-piano`

---

## Adding a piece

1. `mkdir wing-name/piece-slug`, drop the finished HTML in as `index.html`.
2. Paste a row into the right wing in root `index.html`, renumber if inserting.
3. Bump the `Pieces live` count in the masthead spec strip.
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

Tags in use: Report · Instrument · Field manual · Field report · Ops manual ·
Dossier · Log · Sheet.

---

## House rules

- **Every piece ends with something you can operate.** A read with no handoff has failed.
- **Confidence is labelled.** Confirmed, reported, transcribed. Fan lore is riddled
  with misattribution and the honest move is also the useful one.
- **Paraphrase, never reproduce.** Short attributed quotes only, one per source.
  **No lyrics, ever.**
- **No photographs anywhere.** Every texture is a CSS gradient or hand-written
  inline SVG. This is a constraint, not a shortage.
- **Purchases name what they replaced and what they cost in learning time.**
- **Write for six-months-from-now you**, who has forgotten why the fourth string
  was a .022 and what the clock problem actually was.

---

## Design tokens

The chrome is the machine. The content is what is on the workbench. Site furniture
is strict instrument panel; content blocks are allowed to break the grid. Chrome never does.

```
Paper      #F2EFE8    reading surface
Panel      #DFDBD1    chrome fills
Ink        #16151A    type and hard rules
Blueprint  #1F4E7A    diagrams, technical drawing
Alarm      #D9541E    the single interaction colour

JACKET_RIPPER  #D2501B
STUDIO_GLOW    #8FE6D2   (text weight #1A6D5C — the fill fails contrast)
DAMAGE_DONE    #E8B93C   (text weight #8A6712)
```

Type: Bricolage Grotesque (display) · IBM Plex Serif (long-form) · IBM Plex Mono (all chrome).
Motion is mechanical, not cinematic. Things latch and step. Nothing fades in on scroll.
`prefers-reduced-motion` honoured everywhere.

---

## Deploy notes

- Pages serves from one branch. Check Settings → Pages before uploading; commits to
  any other branch change nothing live and look like a broken deploy.
- **Pages is case-sensitive. Windows is not.** This is the single most common way a
  link that works locally 404s in production.
- `CNAME` must survive every upload. Losing it drops the custom domain.
- The repo is public because Pages requires it on the free tier. No license is granted.

## Known gaps

- Wing landing pages and `/about/` — linked from the index, not yet uploaded.
- **The Bench** — downloadable standalone tools. Sits unlit at the
  bottom of DAMAGE_DONE until the first one is finished.
- **WET_FILM** and a terminal-tech wing — real, deferred. No new wing opens until
  three actual drafts exist. Rooms with nothing in them make the whole house read
  as abandoned.
