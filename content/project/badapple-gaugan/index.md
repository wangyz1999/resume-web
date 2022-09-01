---
title: Bad Apple!! Made with Nvidia GauGAN
summary: Recreating the Bad Apple!! video using clouds and grass synthesized by Nvidia GauGAN model
tags:
- Computer Vision
- Programming Art
date: "2021-01-13T00:00:00Z"
lastmod: "2021-01-13T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ""

image:
  caption: A Bad Apple!! frame rendered by drawing sky and cloud using Nvidia GauGAN
  focal_point: Smart

links:
url_code: ""
url_pdf: ""
url_slides: ""
url_video: "https://youtu.be/baRUqyDVKSE"

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: ""
---

"[Bad Apple!!](https://www.youtube.com/watch?v=9lNZ_Rnr7Jc)" is a Japanese dance-pop song initially featured in one of the arcade games from the Touhou series. Since its rise to popularity on Nico Nico Douga (NND) in 2009, the song has inspired an extensive list of remixes, dances, and musical tributes, primarily on the Japanese web. In October 2010, the original upload became the first NND video to reach 10 million views.

{{< youtube i8lDuo9yqfs >}}

As the original video only consists of black and white color, it can essentially be treated as a bitmap animation, where one can easily stylize the two colors into various forms. For example, people have attempted to recreate the video using pixelated animation, ASCII Art, and even stop motion animation using ordinary objects frame by frame.

![Nvidia GauGAN](https://cdn.vox-cdn.com/uploads/chorus_asset/file/15972196/nvidia_gaugan_gif.gif "Nvidia GauGAN landscape drawing demo")

In my project, I attempted to recreate the animation using [Nvidia GauGAN AI Playground](https://www.nvidia.com/en-us/research/ai-playground/) (The improved version [GauGAN2](http://gaugan.org/gaugan2/) is now available). GauGAN is an AI demo for photorealistic image generation, that allows anyone to create stunning landscapes using generative adversarial networks. In their image editor, you can use paint tools to draw landscape images with simple colors, then a photorealistic image will be generated based on the semantic meaning of the color. For example, blue means sky, white means cloud, green means grass, and brown means rocks. This inspired me to create a Bad Apple video with moving clouds in the sky and moving grass on the land.

{{< youtube baRUqyDVKSE >}}

{{< youtube u-1GCGZNotA >}}