# Quant Lab

> A personal workbench for applied mathematics and computation. I take a concept from a course, book, or paper and test it through small self-contained exercises: from-scratch implementations in Python and R, tests that check the math, and a figure or two. The scope grows with my studies, and the repo doubles as a map of how the pieces fit.

## Why this repo exists

This is not a product, and not a course. It is a place to **turn understanding into working understanding**.

Whenever I meet a concept — in a lecture, a book, a paper, a discussion — I write a small exercise around it: implement it from scratch, test it, and look at what it actually produces. Doing the work forces me to write down the assumptions I had been skipping, to catch the parts I only *thought* I understood, and to build an intuition that reading alone does not give.

The second purpose is practical: the exercises are the **building blocks of my projects**. When I later build something real, I reach for blocks I have already written and tested instead of guessing. That is what keeps my projects small, readable, and grounded in things I actually understand.

## How the repo is organized

There are two kinds of places an exercise can live:

- **A subject folder** — the home of a concept: where it is stated, proven, and applied *within its own subject*.
- **`bridges/`** — the exercises that live at an *intersection of subjects*: a concept from one subject applied in another, or two subjects meeting on the same problem. The direction (which subject lends the concept, which provides the setting) is noted in the exercise itself.

Every exercise gets a **global number** (001, 002, …), unique across the whole repo and never reused, whatever folder it lives in. The index below is the map; the folders are just the addresses.

```
.
├── README.md
├── 01-Probability/     # one folder per subject, numbered in the order I study them
│   ├── 001-.../
│   └── 005-.../
├── 02-Satistics/
│   ├── 002-.../
│   └── 004-.../
├── 03-Econometrics/         # a new subject appears → a new folder appears
├── Bridges/               # intersections: where two subjects meet
│   ├── 007-.../
│   └── 011-.../
└── projects/
    └── p1-.../
```

(The subject folders above are examples — they appear as I study the subjects, in that order.)

## Anatomy of an exercise

Every exercise is self-contained: opening a folder should be enough to understand the whole thing without reading anything else.

```
<subject or bridges>/<NNN>-<concept>/
├── enonce.md     # statement, source, what to verify, links
├── py/           # Python implementation
├── r/            # R implementation
├── tests/        # tests that check the math, not just the code
└── figures/      # outputs worth keeping
```

- **`enonce.md`** — the exercise as stated, where it comes from (book, course, paper, with the reference), what exactly I set out to verify, and — at the end — a *Links* section: which concepts this one builds on, which ones it enables, and for bridges, the direction — concept from *subject X*, applied in the setting of *subject Y*.
- **`py/` and `r/`** — the same exercise in both languages. Writing the same thing twice is where a lot of the understanding comes from.
- **`tests/`** — the tests are part of the learning, not a chore. They check the mathematics — a relation, an approximation, a property — with a fixed seed and a tolerance, so the exercise can be re-run and re-verified at any time.
- **`figures/`** — the outputs that make the concept visible.

## How projects are fed

Projects live in `projects/`. The rule that keeps them honest:

> **A project is assembled from exercises that already exist — not the other way around.**

A project starts only when the blocks it needs are already written and tested (or can be written in an afternoon). This keeps each project small, and every line of it rests on something I already understand. The projects are where the concepts I practiced — including the bridges — have to *work together*; that is the test that shows the pieces fit.

```
projects/<p#>-<name>/
├── README.md     # what it does, and which exercises it builds on
└── ...
```

## Index

The map of the repo. Updated as exercises land.

| #   | Exercise | Subject(s)                    | Builds on | Enables |
|-----|----------|-------------------------------|-----------|---------|
| 001 | …        | Linear algebra                | —         | 007     |
| 002 | …        | Probability                   | —         | 011     |
| 007 | …        | Linear algebra × Probability  | 001, 002  | …       |

## Conventions

- **One global numbering** across subject folders and `bridges/`; a number is never reused.
- **One home per exercise**: the folder of the subject the concept belongs to — or `bridges/` if it lives at an intersection. When in doubt: if the concept is *defined* in subject A and merely *applied* in B, it lives in A's folder; if it genuinely needs both to exist, it lives in `bridges/`.
- One commit per exercise; the message says what was verified (e.g. `007: apply X from linear algebra to Y in probability, test under Z`).
- Reproducible: fixed seeds, no network access in tests.
- An exercise counts as done when it is implemented in both languages, its tests pass, and its *Links* section is written.

## Where this is going

Open-ended, on purpose. The next exercise is always the next concept I meet in a course, a book, or a paper; the next bridge is always the next place where two subjects turn out to meet; the next project is always the next place where several of them have to work together. The repo grows the way my understanding grows.