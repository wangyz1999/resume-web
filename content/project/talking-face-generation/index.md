---
title: Talking Face Generation
summary: Synthesizing facial movement based on speech audio to control robot face
tags:
- Academic
- Robotics
- Computer Vision
date: "2022-06-13T00:00:00Z"
lastmod: "2022-06-13T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ""

image:
  caption: Driving robot face (right) through generated facial landmarks (mid) from speech audio (left). 
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

Given a piece of speech waveform and a static face image, lip synchronization matches the person’s lips/facial movement to make it seem like the person is delivering the speech. This task is usually called talking face generation, which aims to synthesize a sequence of face images that correspond to given speech semantics. It is also commonly known as deep fake technology.

Our goal for this project is to design and implement an algorithm that takes the sequence of the audio as the input and outputs the corresponding sequence of facial landmarks with natural lip synchronization and facial expression. The generated landmarks will then be mapped from the human space to the robot space to eventually drive the robot face using an inverse model. This will be one of the modules of the entire software composition of the robot face, which enables it to speak naturally like a human being. Given that most face robots use hard-coded facial expressions with trivial lip synchronization, we are motivated to find deep learning solutions that teach the robot speech-related facial movements from human videos in the wild.

Our model is multi-lingual and can lip-sync breath sound and gibberish. The video below shows landmarks generated from audio reading the English poem "To a Skylark" by Percy Bysshe Shelley and the Chinese poem Qiang Jin Jiu (Chinese: 将进酒 [qiāng jìn jiǔ]) by Li Bai (Chinese: 李白 [Lǐ Bái])

More project detail will be released upon work published.

{{< video src="id8_to_a_skylark.mp4" controls="yes" >}}

{{< video src="ID11_jiangjinjiu.mp4" controls="yes" >}}