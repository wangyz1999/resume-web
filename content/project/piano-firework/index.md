---
title: Piano Music Visualization using Minecraft Firework
summary: Visulizing piano music by sychronizing notes with Minecraft firework
tags:
- Programming Art
date: "2022-08-05T00:00:00Z"
lastmod: "2022-08-05T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ""

image:
  caption: Minecraft firework explosion syncing up with music climax
  focal_point: Smart

links:
url_code: ""
url_pdf: ""
url_slides: ""
url_video: "https://youtu.be/3jlBbc7pvCQ"

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: ""
---

Music visualization, a feature found in electronic music visualizers and media player software, generates animated imagery based on a piece of music. The imagery is usually generated and rendered in real time and in a way synchronized with the music as it is played. Visualization techniques range from simple ones (e.g., a simulation of an oscilloscope display) to elaborate ones, which often include a number of composited effects. The changes in the music's loudness and frequency spectrum are among the properties used as input to the visualization. Effective music visualization aims to attain a high degree of visual correlation between a musical track's spectral characteristics such as frequency and amplitude and the objects or components of the visual image being rendered and displayed.

To visualize piano music, one must know the sequence of music notes on the piano sheet. The process of recording music notes while hearing music is called music transcription, which usually requires music experts to repeatedly listen to the music. A standardized way for music sequences to be saved, transported, and opened in computers is the [Musical Instrument Digital Interface (MIDI)](https://en.wikipedia.org/wiki/MIDI).

Automatic music transcription (AMT) is the task of transcribing audio recordings into symbolic representations. Recently, neural network-based methods have been applied to AMT, and have achieved state-of-the-art results. [Kong et al.](https://arxiv.org/pdf/2010.01815.pdf) proposed a neural method that solves AMT with high resolution by regressing onset and offset times. By inputting a piano music recording, the model outputs a MIDI file that stores the timing and key of each music note transcribed. Their code and pretrained model is publically avaliable in [this GitHub repo](https://github.com/bytedance/piano_transcription).

{{< youtube 5U-WL0QvKCg >}}

[Minecraft](https://www.minecraft.net/en-us) is a sandbox video game developed by Mojang Studios. Players can freely build structures using various types of blocks. One of the key element in the game is “[particles](https://minecraft.fandom.com/wiki/Particles)”, which provides special graphical effects. Visualizing music using Minecraft particles is a popular internet culture. People can program various stunning visual effects that renders real time in the game using a special block call command blocks, which allows game mechanics modification.

Feeling inspired, I decided to make a music visualization video using Minecraft firework particle effect, where the key idea is to synchronize each music note with the firework explosion. The piano music I choose is "[Uchiage Hanabi](https://en.wikipedia.org/wiki/Uchiage_Hanabi)(Japanese: 打上花火)", which means "launching fireworks". The song is used for the anime film Fireworks. I found a piano version of the song performed by [Animenz Piano Sheets](https://www.youtube.com/watch?v=qGT8gGUMbS8).

After transcribing the music using Kong’s method, I visualize the output MIDI file by synchronizing music notes with Minecraft fireworks using Minecraft command blocks. Here is the end result:

{{< youtube 3jlBbc7pvCQ >}}