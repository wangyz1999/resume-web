---
title: "Processing Creative Coding: China Cities Connection Visualization and Meditation Bubble Animation"
subtitle: Creating China cities connection animation and meditation bubble animation using Processing
summary: Creating China cities connection animation and meditation bubble animation using Processing
tags:
- Programming Art
date: "2021-01-17T00:00:00Z"
lastmod: "2021-01-17T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ""

image:
  caption: China Cities Connection Visualization (upper) and Meditation Bubble Animation (bottom)
  focal_point: Smart

links:
url_code: ""
url_pdf: ""
url_slides: ""
url_video: ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: ""
---

[Creative coding](https://en.wikipedia.org/wiki/Creative_coding) is a type of computer programming in which the goal is to create something expressive instead of something functional. It is used to create live visuals and for VJing, as well as creating visual art and design, entertainment (e.g. video games), art installations, projections and projection mapping, sound art, advertising, product prototypes, and much more.

One of the commonly used tools for creating programming animation is [Processing](https://processing.org/), a flexible software sketchbook and a language for learning how to code. In my project, I created two animations using this tool. 

The first animation is a few wobbling layers of bubbles that rotate while zooming in and out. The animation is accompanied by a breathing sound and is intended to be used for meditation practice: breathing in while the buzzle zooms in and breathing out while the bubble zooms out. My idea was inspired by the [Apple Watch Breathe app](https://apps.apple.com/us/app/breathe/id1459455352). The animation is essentially a polar [Perlin noise](https://en.wikipedia.org/wiki/Perlin_noise) loop, where I followed the tutorial [here](https://www.youtube.com/watch?v=rX5p-QRP6R4) and [here](https://www.youtube.com/watch?v=ZI1dmHv3MeM) from [this playlist](https://www.youtube.com/playlist?list=PLRqwX-V7Uu6bgPNQAdxQZpJuJCjeOr7VD).

{{< youtube kpgF47uiJts >}}

The second animation visualizes China cities connections. I downloaded the [China Cities Database](https://simplemaps.com/data/cn-cities) and creates a 2d map with dots using the latitude and longitude data. Each dot represents a city and the dot size correlates with the city population. I connect each city with their nearest neighbors. Starting randomly from one city, a beam is shooted to neighboring cities, and the beam propagates to farther cities. The beam motion follows the arrival steering behavior with acceleration physics leaving a shining trail behind. To add visual complexity, each city dot also shines randomly in sine motion.

{{< youtube i-6xpqGxad0 >}}




