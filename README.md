# Cream — Indulge

A scroll-driven landing page for a small-batch ice cream brand, built from AI-generated photography and video. It's a single `index.html` with no framework and no build step.

## What's on the page

- **Scroll hero.** A photoreal vanilla scoop floats among blueberries. As you scroll, blueberry sauce pours in and rings it, splashes out in slow motion, then marbles and drips. A purple wave then rises and floods into the next section.
- **Let it melt.** A four-flavour carousel (blueberry, salted caramel, black cherry, pistachio) with arrows, dots and swipe. The background colour changes per flavour.
- **The menu.** Four pints with an order basket.
- **How to melt** steps, and a subscribe footer.

## Run locally

```bash
python -m http.server 8000
```

Then open http://localhost:8000.

## How the hero works

- `assets/frames/1280/` (desktop) and `assets/frames/720/` (phones) hold 150 WebP frames cut from a 10-second clip.
- Frames load coarse-to-fine, so scrubbing works before every frame has arrived. Scroll position picks the frame and draws it to a canvas, and the end of the scroll draws the rising purple wave.
- `assets/src/` keeps the original full-size PNGs and the source MP4. The page doesn't load them.

## Not wired up yet

- The basket and checkout are a demo. No payment is taken.
- The subscribe form only shows a confirmation message and doesn't send the email anywhere.
- Brand, flavours, prices and links are placeholders.
