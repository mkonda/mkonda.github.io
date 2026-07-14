+++
title = "Roulette of Emotion"
date = "2026-07-11"
description = "An animated art piece that spins a roulette wheel of emotions and lands on a random selection"
tags = ["art", "programming"]
featured = true
+++

## Roulette of Emotion

What if the emotions you feel right now were chosen at random?

This piece renders a roulette wheel with 24 emotions from
Plutchik's model — eight families of three intensities each,
from Ecstasy to Serenity, from Rage to Annoyance. The wheel
spins slowly at first, giving you time to read each emotion as
it drifts past the pointer. Then it accelerates past legibility,
blurring into streaks of color. A jolt. The wheel fights to stop.
Three emotions emerge.

<iframe src="/art/roulette-of-emotion.html" style="width:100%;height:500px;border:1px solid #333;border-radius:4px;margin:1.5em 0;"></iframe>

<p style="text-align:center;margin-top:-0.5em;"><a href="/art/roulette-of-emotion.html" target="_blank">View fullscreen</a> — restart for a different spin</p>

## The Idea

The previous pieces in this series — Inner Landscape, Projecting,
Immolation of Emotion — all treat our emotional experience as
something to be mapped, filtered, or questioned. This one takes a
different angle: what if we don't choose our feelings at all?

A roulette wheel is a machine for generating arbitrary outcomes.
Putting emotions on it suggests that what you feel might be less
about who you are and more about where the wheel happened to stop.
The slow spin invites you to consider each emotion — Admiration,
Terror, Boredom, Vigilance — and the acceleration takes that
consideration away. You don't get to pick. The wheel picks for you.

The three emotions that emerge at the end are always neighbors on
the Plutchik wheel, which means they're related — different
intensities of the same feeling, or adjacent families. That's an
interesting constraint: the randomness doesn't produce completely
unrelated emotions. It produces a cluster. Maybe that's closer to
how feelings actually work — you don't get Grief in isolation, you
get Grief and Sadness and Pensiveness all at once, in varying
proportions.

## Building It

The wheel is rendered in perspective — a vertical scale of 0.55
turns the circle into an ellipse, as if you're looking down at a
roulette table from across the room. A subtle green felt gradient
and a shadow ellipse reinforce the casino atmosphere.

The 24 segments use the actual colors from the Plutchik wheel SVG
on Wikipedia. Each segment gets a radial gradient (darker at the
inner edge, brighter at the outer) for depth. The text compensates
for the perspective compression with a local scale transform so
the letterforms stay proportional despite the vertical squash.

The spin dynamics use analytically integrated velocity curves. The
slow phase holds at 0.5 rad/s for 12 seconds — nearly a full
revolution, enough to read every emotion. The acceleration phase
ramps from 0.5 to 10 rad/s using a quadratic curve. At peak speed,
motion blur draws the wheel 3-5 times at slight angular offsets,
turning distinct segments into color streaks.

The deceleration uses a damped oscillator for the jolt effect:
`sin(38t) × e^{-5t}` produces about six rapid oscillations that
decay exponentially, like a physical ratchet catching on the frets.
When the wheel stops, it slides left and three emotion cards appear
on the right — clean panels with a colored accent bar and the
emotion name at 34px. A thin connecting line ties each card back to
its glowing segment on the wheel.

## The Randomness

Each restart picks a new landing position and a new triplet of
emotions. The selection is always three adjacent segments — one
at the pointer and its two neighbors. Because the 24 segments are
organized in families of three (intense, basic, mild), the landing
often produces a family cluster: you might get Ecstasy, Joy, and
Interest, or Rage, Anger, and Vigilance. Occasionally it crosses
a family boundary: Trust, Acceptance, Terror. Those crossings feel
unexpected, which is part of the point.

[View the full piece here](/art/roulette-of-emotion.html).
