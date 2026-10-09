# House style

This session uses the same house style as the Epidemiological Thinking lecture series, so the decks look and read as one family.

## Slides

- reveal.js, 1280 by 720, styles from `assets/css/tokens.css` and `assets/css/slides.css`. Use the existing classes (`.lede`, `.claim`, `.claim.good`, `.claim.warn`, `.cards`, `.card`, `.stat`, `.eq`, `.frac`, `.pill`, `.cite`, `ol.sources`). Anything a deck needs beyond these, such as a chart, goes in that deck's own `<style>` block.
- Every slide title is a claim or a question, not a topic label. "Counts mislead. Divide by the number at risk", not "Rates".
- One idea per slide.
- When the room should think, put the question on one slide and the answer on the next.
- Every slide has speaker notes (`<aside class="notes">`), written as what the teacher would say.
- Text never smaller than 14 pt (19 px on the slide).
- No em dashes anywhere, including notes.
- Plain English: short sentences, define a term the first time it is used.
- Colours carry meaning: navy for the main series and claims, green for what works or resolves, amber for caution or a trap, red only for reject or harm.
- Real data wherever possible, cited on the slide (`.cite`) and in the sources slide. Any made-up example is labelled "Illustrative, constructed for teaching".
- The cover kicker reads `Health Communication · First MBBS`. No personal names on any visible page; credit AIIMS Bhopal.
- Video clips use the `.clip` player in the deck: a local poster frame, a Play button, a local file from `media/` if present, else YouTube (youtube-nocookie). Every clip slide also links to the clip on YouTube.

## Checks

```
python3 -m http.server 8765 &
npm install            # once, for playwright-core
node src/chk.mjs health-promotion-iec-bcc
```

The checker reports overflow past the slide, text under 14 pt, missing notes, em dashes and JS errors.

`python3 src/bundle.py [site_url]` writes a single-file copy of the deck to `dist/` for sharing offline.
