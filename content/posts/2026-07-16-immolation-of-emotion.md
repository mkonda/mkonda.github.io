+++
title = "Immolation of Emotion"
date = "2026-07-16"
description = "An animated art piece that burns away the Plutchik wheel of emotions to see what remains"
tags = ["art", "programming"]
featured = true
+++

## Immolation of Emotion

Robert Plutchik's wheel of emotions is one of the most elegant
models in psychology. Eight primary emotions arranged like flower
petals, each with three intensities — from Ecstasy down to Serenity,
from Rage down to Annoyance. Between adjacent petals sit the
combination emotions: Joy plus Trust equals Love. Disgust plus Anger
equals Contempt. It's tidy, satisfying, and complete.

This piece sets it on fire.

<iframe src="/art/immolation-of-emotion.html" style="width:100%;height:500px;border:1px solid #333;border-radius:4px;margin:1.5em 0;"></iframe>

<p style="text-align:center;margin-top:-0.5em;"><a href="/art/immolation-of-emotion.html" target="_blank">View fullscreen</a> — click "Blaze" for a different burn mode, then restart</p>

## The Idea

I've been thinking about the gap between how we categorize emotions
and how we actually experience them. The Plutchik wheel implies that
feelings are discrete, nameable, and neatly organized. But real
emotional life isn't like that. Grief bleeds into anger. Joy carries
fear. Surprise dissolves into something that doesn't have a word.

So I wanted to build the wheel — beautiful, organized, labeled — and
then destroy it. Not out of hostility toward the model, but as a
question: what's left when you take away the categories?

The answer the piece offers: a flame. The same small flame that
appears in my earlier piece *Projecting*, where it sits behind
thirty-two different windows. Here it emerges from the ashes of
taxonomy itself. The flame was always there. The wheel was just one
way of looking at it.

## Two Ways to Burn

The piece has two burn modes, toggled with the button in the controls:

**Sections** — Fire spreads methodically from one petal to the next,
consuming the outer ring first (the mild emotions), then the middle
ring, and finally the intense inner core. It feels surgical and
deliberate, like carefully dismantling a framework.

**Blaze** — A single massive conflagration engulfs the entire wheel.
The fire starts at one petal and rapidly spreads into a unified
inferno with rising columns, a white-hot core, smoke, and sparks.
The wheel chars uniformly underneath. It feels sudden and
overwhelming.

Both modes end in the same place: darkness, drifting ash, and then
the flame.

## Building It

Like the previous pieces, this is a single HTML file — Canvas 2D and
vanilla JavaScript. The Plutchik wheel uses arc sectors for the inner
and middle rings, and quadratic bezier curves for the outer ring to
create petal-shaped tips. Each section renders with a radial gradient
for depth.

The fire spread in Sections mode uses per-section burn delays based
on angular distance from the ignition point and ring depth. In Blaze
mode, the fire is rendered as a separate visual layer: five large
overlapping flame bodies (each with five bezier teardrop layers),
rising column flames, edge licks, smoke plumes, and sparks — all
swaying together in a shared wind vector to feel like one unified
mass rather than scattered campfires.

The wheel slowly rotates during the display and burn phases, then
decelerates and freezes as the fire destroys it. The deceleration
follows an integrated cubic curve — velocity drops as (1 - t&sup2;),
giving the rotation a feeling of surrender rather than a hard stop.

## The Connection

This is the third piece in what's become an informal series about
inner experience:

- **Inner Landscape** maps emotions to mountains seen from different
  altitudes
- **Projecting** shows a single flame seen through thirty-two
  different windows — each one filtering or distorting it differently
- **Immolation of Emotion** burns away the neat taxonomy and reveals
  that same flame underneath

The `drawFlame` function is literally the same code across all three
pieces. The flame is the constant. Everything else — mountains,
windows, wheels — is just a frame we put around it.

[View the full piece here](/art/immolation-of-emotion.html).
