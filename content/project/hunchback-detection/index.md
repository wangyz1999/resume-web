---
title: Hunchback Detection
subtitle: A sitting posture classification model that helps you maintaining good posture
summary: A sitting posture classification model that helps you maintaining good posture
tags:
- Academic
- Computer Vision
date: "2022-08-28T00:00:00Z"
lastmod: "2021-08-28T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ""

image:
  caption: The hunchback detection program classifing my sitting posture in realtime
  focal_point: Smart

links:
url_code: "https://github.com/wangyz1999/hunchback-detection"
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

The most common position of our spines throughout most of the day is a rounded or hunched one. Modern activities, such as using a smartphone, tablet, or laptop, cause us to bend our neck and upper back. A hunchback – medically termed kyphosis or hyperkyphosis in the extreme – is an abnormal forward curvature in the upper back. Bending your neck for a prolonged time doesn’t look good and may cause muscle imbalance and compression in blood vessels, leading to long-term health risks.

One could exercise targeted neck muscles to fix muscle imbalance and a hunched posture. But most importantly, one needs to make lifestyle changes and be conscientious about making spinal posture upward during walking and sitting. Nonetheless, lifestyle changes are not easy, and one may quickly shift back to a lousy posture without noticing.

![correct sitting posture](https://images.theconversation.com/files/122639/original/image-20160516-26379-1enhc2m.jpg "Correct Sitting Posture")

Dedicated to fixing my bad sitting posture, I devised the idea of detecting bad sitting posture using a frontal webcam. Whenever I carelessly hunched forward, a notification would pop up to remind me to maintain an upright posture again. Ideally, this “posture training program” may gradually help me form a good sitting posture habit.

A hunchback detection program is essentially a sitting posture classification task. Based on the degree of neck bending, head forwardness, and back ‘hunchness,’ one may classify the sitting posture as ‘excellent,’ ‘okay,’ ‘bad,’ and ‘terrible’. To train such a classifier, one needs to collect posture data for each one of the classes, which can be done by utilizing [MediaPipe Pose](https://google.github.io/mediapipe/solutions/pose), which gives 3d pose landmarks (coordinates) data about head and shoulder position. As each class of sitting posture uniquely defines a set of pose landmarks, one may use the coordinate data to train the classifier.

While running MediaPipe Pose, I possess four types of sitting posture (excellent, okay, bad, and terrible posture) and press corresponding keys to collect data instances. Each class has around 400 instances, and the data-collection process takes about 2-3 minutes. I then trained a simple classifier using the [scikit-learn Logistic Regression](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LogisticRegression.html) model, which converges in less than 10 seconds. After training, I can make sitting posture classification and pop up a Windows notification using [Windows 10 Toast Notifications](https://github.com/jithurjacob/Windows-10-Toast-Notifications) (a python library) at the lower right corner whenever a ‘bad’ or ‘terrible’ posture is detected.

One limitation of this model is that it is user specific. Since the landmark coordinate may be determined by multiple factors such as camera position, chair height, distance to the camera, and different people may have different head-body ratios, one may want to collect their own data and train their own model for personal use.

The entire process, from forming ideas to implementation realization, takes me about 2 hours, but I will probably continue using this tool until my bad posture habit is fixed. The program demo is shown in the gif below:

![demo](output.gif)