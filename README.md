# Your First DJ Mix

A nine-slide Slidev introduction for ages 8–16 with no DJ experience. The talk and live demos total **10 minutes**; any hands-on practice is additional.

## Run

Requires Node.js 22.12+ and pnpm 10.

```sh
pnpm install
pnpm dev
```

Slidev prints the local URL. Open presenter mode from its toolbar to see the teaching notes. Arrow keys navigate the slides.

```sh
pnpm build       # static site in dist/
pnpm preview     # preview the built site
```

## Edit

- `slides.md`: all nine slides, timing, demonstration instructions, and presenter notes.
- `components/DeckSetup.vue`: simplified two-deck teaching diagram, not an exact hardware/software screenshot.
- `style.css`: colours, typography, and slide layouts.
- `public/`: local assets, including the slide 2–4 photos (`dj-photo.jpg`, cropped `cdj-3000x.jpg`, `dj-pair-left.jpg`, and `dj-pair-right.jpg`) and the Iosevka fonts from afriendlywave.com (SIL OFL 1.1; license in `public/fonts/iosevka-LICENSE.md`). Reference a file such as `public/djay.png` as `/djay.png` in the slides.

## Before teaching

- Replace the two music placeholders in slide 1's presenter notes. No music is bundled. Use appropriate, permitted sources and check the exact lyrics/versions.
- Rehearse with the actual djay version, device, and controller. Check compatibility, access to required features, track analysis, headphone routing, crossfader assignments, and comfortable volume levels.
- Bring two prepared tracks with clear beats, similar tempos, and sections that work together. Sync is a helper, not a guarantee that tracks fit.
- Optionally replace the slide 5 diagram with a labelled screenshot of the actual djay layout. No screenshots are bundled.
- Confirm learner numbers, controller access, helpers, and practice time. The last slide supports either practice rotations or a group-directed demonstration.

## Outline

1. You're in charge of the music — 1 minute.
2. Vintage DJ console photo — visual interlude (no extra time).
3. Modern DJ setup photo — visual interlude (no extra time).
4. Two home DJ setups — visual interlude (no extra time).
5. Meet your decks — 2 minutes.
6. Find the beat — 1 minute.
7. Listen before everyone else — 1 minute.
8. Make your first transition — 4 minutes.
9. Your turn — 1 minute.

The core transition uses Sync, headphone preview, a prepared start point, and the crossfader. EQ, effects, loops, scratching, and manual beatmatching are deliberately left for another session.
