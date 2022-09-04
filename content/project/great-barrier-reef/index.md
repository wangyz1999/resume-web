---
title: Help Protect the Great Barrier Reef
summary: Detect crown-of-thorns starfish in underwater image data
tags:
- Computer Vision
- Academic
date: "2022-01-22T00:00:00Z"
lastmod: "2022-01-22T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ""

image:
  caption: coral-eating crown-of-thorns starfish detected
  focal_point: Smart

links:
url_code: "https://github.com/wangyz1999/kaggle-projects/tree/main/tensorflow-great-barrier-reef"
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

This is an object-detection [Kaggle competition](https://www.kaggle.com/competitions) project. 

Australia's stunningly beautiful Great Barrier Reef is the world’s largest coral reef and home to 1,500 species of fish, 400 species of corals, 130 species of sharks, rays, and a massive variety of other sea life.

{{< youtube UT2noVDFoaA >}}

Unfortunately, the reef is under threat, in part because of the overpopulation of one particular starfish – the coral-eating crown-of-thorns starfish (or COTS for short). Scientists, tourism operators, and reef managers established a large-scale intervention program to control COTS outbreaks to ecologically sustainable levels.

To help identify COTS undersea, [this Kaggle competition](https://www.kaggle.com/competitions/tensorflow-great-barrier-reef) releases the [CSIRO Crown-of-Thron Starfish Detection Dataset](https://arxiv.org/abs/2111.14311) and requires building an object detection model targeting COTS. Having no experience in object detection tasks, I decided to treat this as a valuable learning opportunity. After some literature review, I learned that the You Only Look Once (YOLO) model family is suited for this type of task, which applies a single neural network to the full image. This network divides the image into regions and predicts bounding boxes and probabilities for each region. These bounding boxes are weighted by the predicted probabilities.

To make sure I understand the background of the YOLO model, I followed [this YouTube tutorial](https://www.youtube.com/watch?v=n9_XyCGr-MI) and build YOLO v1 from scratch. Throughout the process, I learned the intuition behind the algorithm and related concepts such as intersection over union (IOU), non max suppression (NMS), and mean average precision (MAP). After training the model from scratch for a while, I noticed that its performance was too bad to get into the public leaderboard. 

After that, I decided to attempt fine-tuning the state-of-the-art pre-trained YOLO v5 model for this specific task. Unlike previous YOLO models, the YOLO v5 has a CSP backbone and PA-NET neck. The major improvements include mosaic data augmentation and auto-learning bounding box anchors. The YOLO v5 model is [open-sourced](https://github.com/ultralytics/yolov5), and I decided to finetune the medium version.

Besides training the model onto a different dataset and searching for the best confident hyper-parameter. I also attempted techniques such as image upscaling and tracking. My model was trained and fine-tuned on a Colab Pro GPU (P100). I eventually scored 607/2026 on the private leaderboard. With no prior experience in object detection and Kaggle competition, I learned a lot throughout the process: people would share their thoughts and methods on the discussion forum, and you get to read the code about top solutions in documented notebooks. 