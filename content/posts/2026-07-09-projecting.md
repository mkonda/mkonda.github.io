+++
title = "Projecting"
date = "2026-07-09"
description = "An animated art piece about the many windows we place between our inner flame and the outside world"
tags = ["art", "programming"]
featured = true
+++

## Projecting

This piece started from a simple image: a sphere with a small flame
at its center, and windows scattered across the surface. Each window
is different. Some are open, some are barred, some are bricked shut.
The viewer watches the sphere rotate, then zooms into a window and
sees the flame through whatever filter that window imposes.

<iframe src="/art/projecting.html" style="width:100%;height:500px;border:1px solid #333;border-radius:4px;margin:1.5em 0;"></iframe>

<p style="text-align:center;margin-top:-0.5em;"><a href="/art/projecting.html" target="_blank">View fullscreen</a> — restart for a different set of windows</p>

## The Idea

We all have something at our core — call it a soul, a self, an inner
light. But no one ever sees it directly. They see it through windows,
and we choose (or don't choose) which windows to show. Some of those
windows are honest. An open window lets the flame through clearly,
and that feels vulnerable. A frosted window is gentler — you can sense
the warmth without the detail.

But some windows are performances. A polished window looks perfect,
reflecting a gleam that has nothing to do with the actual flame. A
painted window shows a landscape that isn't even real — a scene we
want people to see instead of what's actually inside. A gilded window
frames the flame like a museum piece, curated and controlled.

And some windows are defenses. Bars, shutters, curtains, armor plating.
A bricked window says: there is nothing here. A hollow wall says: there
was never a window at all.

The piece cycles through these windows randomly. Each restart shuffles
the order, so you never see the same sequence twice. I like that the
viewer can't predict which window comes next — just like in life, you
don't always know which version of a person you're about to encounter.

## The Windows

There are 32 windows in total. A few that I find particularly
interesting:

**Painted** — A pleasant landscape is painted directly on the glass.
Behind it, the real flame is almost invisible. This is the window of
someone who has constructed an entire false front. You see rolling
hills and a sunset, not the fire underneath.

**Measured** — The left half is clear glass, the right half frosted.
A precise, controlled amount of visibility. This is the window of
someone who has decided exactly how much of themselves to reveal and
will not deviate.

**Hollow** — There is no window. Just rough stone wall. Not even the
pretense of an opening. The faintest warm spot on the stone is the
only hint that something once existed here.

**Bright** — The opposite extreme. The flame is tripled, blazing,
with lens flares. Almost too much. This is the window of someone
showing everything, whether you asked for it or not.

**Display** — A spotlight, a pedestal, a velvet rope. The flame is
real but staged. It has been turned into a performance, an exhibit
for others to admire at a safe distance.

## Building It

Like Inner Landscape, this is a single HTML file with zero
dependencies — Canvas 2D and vanilla JavaScript. The sphere uses
Fibonacci distribution to place 32 windows evenly on its surface,
then projects them to 2D with a simple perspective divide. A gentle
vertical wobble on the rotation gives the sphere a more organic feel.

Each window is its own render function. Some are simple (barred is
just rectangles over the flame), some are involved (boarded has
individually tilted planks with wood grain, nails, and light bleeding
through gaps). The arch-shaped window frame clips all the interior
rendering, so each effect is self-contained.

The animation shows four windows per 48-second cycle. With 32
windows and random shuffling, you'd need to watch for several minutes
to see them all — or just keep hitting restart.

[View the full piece here](/art/projecting.html).
