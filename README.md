# HIDECS 2 — Reenactment

```
   ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░
   ░  ┌───────────────────────────────┐   ░
   ░  │  ▣ File  Edit  View  Special   │   ░
   ░  ├───────────────────────────────┤   ░
   ░  │ HIDECS 2 — Reenactment    2:00 │   ░
   ░  │ ┌───────────────────────────┐ │   ░
   ░  │ │ A 1962 program, rebuilt    │ │   ░
   ░  │ │ as an object you can touch │ │   ░
   ░  │ └───────────────────────────┘ │   ░
   ░  └───────────────────────────────┘   ░
   ░░░░░░░░[||||||||||||||||||||||||]░░░░░
   ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░
```

A 1962 decomposition program, reenacted as an object you can touch.

## What it is

In 1962, Christopher Alexander and Marvin Manheim wrote HIDECS 2 at MIT's Civil Engineering Systems Laboratory: feed it a list of design requirements and a graph of how those requirements interact, and it cuts the graph into the grouping that severs the fewest links — the hidden structure of a problem, computed rather than guessed at. There was no screen. Input was a card deck; output was a printed page a designer then redrew as a tree by hand.

This project, built with the McGill CoDEx group, reenacts that system as a physical machine a visitor can actually operate. This repo is the web half of it: a single page that renders a period-correct desktop computer in 3D CSS, with the project's record — the history, the model photos, the citations — running as real, selectable DOM text laid out *inside* the machine's own screen.

## Highlights

- A full 3D chassis (front, back, left, right, top, bottom faces) built from plain CSS transforms — no 3D library, no canvas scene graph for the shell.
- Drag to rotate, arrow keys to nudge, a resting pose it springs back to on click. Respects `prefers-reduced-motion`.
- The screen content is a real 1-bit desktop UI — menu bar, window chrome, tabs, scrollbar, a ticking clock — written in ordinary HTML and CSS.
- Where the browser supports `HTMLCanvasElement.requestPaint` / `drawElementImage`, that DOM is painted onto a `<canvas>` inside the 3D screen for a sharper composite; everywhere else it falls back to the plain DOM overlay. A status chip in the footer reports which mode is active.
- Three tabs tell the story: **Read** (the history), **Model** (photos of the physical acrylic/cork housing and the cardboard keyboard study), **Record** (year, role, the system it reenacts, and links to the original 1962 report and the ACADIA paper on the reenactment).

## Stack

Plain HTML, CSS, and vanilla JavaScript. No build step, no dependencies — the whole thing is `index.html`.

## Run locally

```bash
python3 -m http.server
```

Then open the served `index.html` in a browser.

## Map

```
index.html   the entire site: markup, styles, and the rotation/paint script
hero.webp    photo of the physical model (acrylic housing, cork panels, cardboard keyboard)
```

## Background

- Year: 2023 · Product design, HCI, media arts · with McGill University / McGill CoDEx
- System reenacted: HIDECS 2 (1962), Alexander & Manheim, MIT Civil Engineering Systems Laboratory, Publication 160, originally run on an IBM 709
- [The 1962 HIDECS 2 report](https://christopher-alexander-ces-archive.org/article/hidecs-2-a-computer-program-for-the-hierarchical-decomposition-of-a-set-which-has-an-associated-linear-graph/)
- [Vardouli, *Setting Historic Computer Systems in Motion*, ACADIA 2022](https://papers.cumincad.org/data/works/att/acadia22_726.pdf)
