---
title: Coffin Dance (Astronomia) ASCII Art
subtitle: Creating tone-based ASCII Art Video from the popular meme "Coffin Dance"
summary: Creating tone-based ASCII Art Video from the popular meme "Coffin Dance"
tags:
- Programming Art
date: "2020-04-22T00:00:00Z"
lastmod: "2020-04-22T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ""

image:
  caption: A classic frame of the Coffin Dance video made to ASCII Art
  focal_point: Smart

links:
url_code: ""
url_pdf: ""
url_slides: ""
url_video: "https://www.youtube.com/watch?v=QSfMJBRXhEA"

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: ""
---

An ASCII art video is made by playing a video using pure ASCII characters. In the earliest days, people made ASCII art videos that can be played on terminals such as [the Windows Star War Easter Egg](https://www.youtube.com/watch?v=UgKOgTxfvxE). However, such videos usually require an artist manually typing related characters and takes a considerable amount of time to make. It would be really interesting if one could turn any video into ASCII art video.

There are two types of ASCII art: tone-based ASCII art and structure-based ASCII art. The former places characters based on pixel lightness, which is relatively easy to make and widely made on the Internet. The latter requires recognizing the graphical pattern and placing the closest symbol, which is relatively difficult to make. Checkout my other project where I made a structure-based ASCII art video using a deep learning method: [Bad Apple!! Played on Structure-based ASCII Art](https://www.yunzhew.com/project/badapple-ascii/). 

There are several ways to turn a video into tone-based ASCII art. The most commonly used method is to divide each video frame into small patches, and replace each small patch to a fixed dictionary of ASCII characters based on average pixel color density separated by different thresholds. When picking a character to represent a pixel we need to measure the relevance of that pixel's color in the frame, based on that we can then select the most appropriate character based on the [relative luminance](https://en.wikipedia.org/wiki/Relative_luminance) in colorimetric spaces, using a simplified version of the luminosity function. For example, the characters below shows an increasing level of relative luminance:

```
[' ', '.', ':', '!', '+', '*', 'e', '$', '@', '8']
```

{{< youtube j9V78UbdzWI >}}

The video I choose is Astronomia, more commonly known as [Coffin Dance](https://www.youtube.com/watch?v=j9V78UbdzWI), which is a very popular meme video at that time. Here is my end result of turning it to an ASCII art video:

{{< youtube QSfMJBRXhEA >}}

