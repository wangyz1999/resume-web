---
title: Bad Apple!! Played on Structure-based ASCII Art
summary: Recreating the Bad Apple!! video using Structure-based ASCII Art by classifing image patches to symbols
tags:
- Computer Vision
- Programming Art
date: "2022-04-25T00:00:00Z"
lastmod: "2022-04-25T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ""

image:
  caption: Our car agent exploring the experiment with distance sensors
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

"Bad Apple!!" is a Japanese dance-pop song initially featured in one of the arcade games from the Touhou series. Since its rise to popularity on Nico Nico Douga (NND) in 2009, the song has inspired an extensive list of remixes, dances, and musical tributes, primarily on the Japanese web. In October 2010, the original upload became the first NND video to reach 10 million views.

{{< youtube i8lDuo9yqfs >}}

As the original video only consists of black and white color, it can essentially be treated as a bitmap animation, where one can easily stylize the two colors into various forms. For example, people have attempted to recreate the video using pixelated animation, ASCII Art, and even stop motion animation using ordinary objects frame by frame.

There are two types of ASCII art: tone-based ASCII art and structure-based ASCII art. The former places characters based on pixel lightness, which is relatively easy to make and widely made on the Internet. The latter requires recognizing the graphical pattern and placing the closest symbol, which is relatively difficult to make. To tackle this problem, Akiyama propose a neural image classification method using convolutional neural network. Given a sketch image, they first segment the image into non-overlap patches. Then for each patch, they run the classification model to replace it with the actual ascii character. 

To use their method, I first uses regular canny edge detection method on the Bad Apple video. And then apply Akiyama’s method: for each frame, divide it into thousands of tiles, and do image recognition with deep neural network to find the closest matching character for each individual tile. Finally, make them back to images and joined to a full video. 


{{< youtube 8GulN69Cgbg >}}