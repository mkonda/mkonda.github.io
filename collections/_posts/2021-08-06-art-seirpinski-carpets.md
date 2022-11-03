---
title: 'Digital Art Sierpinski Carpets'
date: 2021-08-06 00:00:00
categories: ["Art","Programming"]
thumbnail: /assets/images/color-sierpinski.jpg
description: Making art with code has been a fun diversion
---

![Sierpinski](/assets/images/color-sierpinski.jpg)

## Digital Art

When the pandemic hit, I found myself with a lot of time and energy
that I didn't know what to do with.  One of the things I picked up
was playing with different art in code.

You might ask: "why would
you want to spend more time in code or at a computer?"  The truth
is that I spend so much time building the business, in meetings and
writing code for things that are needed that I haven't had much
time to write code for fun lately.  So this turned out to be a
satisfying fun adventure.

I'm hoping this will be the start of a series of posts about different
art I've worked on or played with.  One thing that is really interesting
is that as you write code to create an image, you have to think a bit
about what makes that art unique or different.  For instance, I wanted
to write a script that would generate Mondrian style images and it
turned out to be a lot harder than I thought because many of the things
that make those images *work* are not as basic as you might think.

Anyway, this is just an intro post about one of the early efforts.  I
started by looking at fractals, because different kinds of fractals
are cool, right!  One simple one is a Sierpinski Carpet.  Which, BTW,
is my LinkedIn image header background.

## Sierpinski Carpet

So a [Sierpinski Carpet](https://en.wikipedia.org/wiki/Sierpiński_carpet)
is a plane fractal built with squares.  If you look at the image above, it
was made by starting with a black background and then removing squares in 
a number of iterations.  Each iteration, each square is cut into 9 pieces
(3x3) and the central square is removed.

The diagram below (from [wikipedia](https://en.wikipedia.org/wiki/Sierpiński_carpet)) 
shows the progression through each iteration.

![Progression](/assets/images/sierpinski-rounds.png)

## Code

This is the code I used to create the carpet.

```python
import numpy as np 
from PIL import Image 

total = 8
size = 3**total 
square = np.empty([size, size, 3], dtype = np.uint8) 
color = np.array([255, 255, 255], dtype = np.uint8) 
square.fill(18) 
  
for i in range(0, total + 1): 
    stepdown = 3**(total - i) 
    for x in range(0, 3**i): 
          
        # checking for the centremost square 
        if x % 3 == 1: 
            for y in range(0, 3**i): 
                if y % 3 == 1: 
                    square[y * stepdown:(y + 1)*stepdown, x * stepdown:(x + 1)*stepdown] = color 
  
save_file = "sierpinski.jpg"
Image.fromarray(square).save(save_file) 
i = Image.open("sierpinski.jpg") 
i.show() 
```

