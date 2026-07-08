+++
title = "Inner Landscape"
date = "2026-07-08"
description = "An animated art piece that maps emotions to mountains"
tags = ["art", "programming"]
featured = true
+++

## Inner Landscape

I've been wanting to get back to making art with code. This time, I
wanted to build something that *moves* — a piece that unfolds over time
and tells a kind of story. The result is Inner Landscape, a looping
animated piece built entirely with SVG and JavaScript in a single HTML
file.

<iframe src="/art/inner-landscape.html" style="width:100%;height:500px;border:1px solid #333;border-radius:4px;margin:1.5em 0;"></iframe>

<p style="text-align:center;margin-top:-0.5em;"><a href="/art/inner-landscape.html" target="_blank">View fullscreen</a> — reload for a different arrangement</p>

## The Idea

The piece is intended to capture a common situation where we have 
an outward representation of how we are doing (a window) but then
when we reflect we realize it isn't necessarily quite so simple a
view. Then, I wanted to capture the idea that as we reflect we get
better and better sense for our internal emotions. I imagine
meditating and noticing these bulbs of feeling and as I make space
for the feelings to emerge I start to know which is which.

## Building It

I built this collaboratively with Claude Code, iterating through several
rounds. We started by considering different technical approaches — Canvas
2D, Three.js, even Rust compiled to WASM — and settled on SVG + JavaScript
for simplicity. Zero dependencies, one file, just open it in a browser.

The interesting part was the creative iteration. The first version had all
the peaks appear at once during the aerial phase, which felt flat. We
changed it so peaks emerge progressively — the largest ones appear first
(visible from high altitude), and smaller peaks materialize as you descend.
That made it feel like an actual descent. The side view got a similar
treatment with a slow zoom that accentuates the front ridges.

The emotion layer came last. We mapped 24 emotions to HSL colors based on
psychological associations — warm hues for active emotions like Rage and
Courage, cool hues for contemplative ones like Calm and Trust, purples
for complex states like Pride and Longing. Then we shuffled the assignment
per page load so every viewing is different.

## A Few Technical Details

The animation uses `requestAnimationFrame` with a phase-based timeline.
Each phase maps elapsed time to a 0-1 progress value, which keeps the
rendering code simple:

```javascript
function phaseOf(t) {
  if (t < 6)  return { name: 'window',   p: t / 6 };
  if (t < 14) return { name: 'crack',    p: (t-6) / 8 };
  if (t < 17) return { name: 'toAerial', p: (t-14) / 3 };
  if (t < 29) return { name: 'aerial',   p: (t-17) / 12 };
  if (t < 32) return { name: 'toSide',   p: (t-29) / 3 };
  if (t < 47) return { name: 'side',     p: (t-32) / 15 };
  return { name: 'fadeOut', p: (t-47) / 7 };
}
```

The crack animation uses a classic SVG trick: each crack line has
`stroke-dasharray` set to its total length and `stroke-dashoffset`
animated from that length to zero. This makes the line appear to draw
itself outward from the impact point.

The side view creates depth with four overlapping ridge layers. Front
layers are darker and taller, back layers lighter and shorter. As the
view zooms in, front-layer opacity increases faster than back layers,
simulating atmospheric perspective.

## The Emotions

The full set: Joy, Grief, Anger, Peace, Fear, Hope, Love, Shame,
Wonder, Doubt, Pride, Calm, Rage, Trust, Guilt, Bliss, Awe, Envy,
Desire, Sorrow, Anxiety, Courage, Longing, and Gratitude.

I like that the piece works on two levels. Without labels it's an
abstract landscape — just color and shape and movement. With labels
it becomes a map of inner experience. Both readings are true at the
same time.

[View the full piece here](/art/inner-landscape.html). Watch it
through twice to see the labels appear on the second cycle.
