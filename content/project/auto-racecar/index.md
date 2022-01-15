---
title: Automonous Driving Agent
summary: Simulate a car racing agent using reinforcement learning in Unity3D
tags:
- Simulation
- Reinforcement Learning
date: "2021-04-27T00:00:00Z"
lastmod: "2021-05-10T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ""

image:
  caption: Our car agent exploring the experiment with distance sensors
  focal_point: Smart

links:
- icon: external-link-alt
  icon_pack: fas
  name: Website
  url: https://csci527.wixsite.com/agentsmart
url_code: "https://github.com/hyitong/AgentSmarts"
url_pdf: "https://0b5b5102-2b8f-4166-846b-a04b28f41e75.filesusr.com/ugd/45d7c8_5ebe55979a514ee1b63e5804947213a2.pdf"
url_slides: ""
url_video: "https://video.wixstatic.com/video/45d7c8_18f2ef61c34942b8ad44d66d46731388/720p/mp4/file.mp4"

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: ""
---

Machine learning has been a popular technique used in video games and real world in recent decades. Autonomous vehicle is a typical situation that use ml-based solutions. The aim of this project is to simulate an autonomous vehicle in racing games. In this game project, we explored various reinforcement learning algorithms provided by Unity Ml Agent such as PPO and SAC, and other self-coded reinforcement algorithms to train the car agent. In addition to reinforcement learning, other machine learning methods is examined such as imitation learning. To optimize the agent performance, various related factors is tested including observation methods, action states and reward structure. Potential problems were proposed based on the experiment observations and improvement methods were introduced to solve these problems. These improvement methods might be used to deal with similar problems in real life and have meaningful affects to self-driving research.

Our group aims to build intelligent agents that could be successfully employed in car-racing games. The basic environment setup is Unity3D with ml-agents package for reinforcement learning, and we will interface PyTorch with the Barracuda package for enabling GPU computation and testing our custom models such as DQN, PPO, and genetic algorithms.

There are tons of extra features that we could add to the game to make it more playable and diversified such that different strategies can be learned. For example, agents might drift to turn fast at corners or use nitro acceleration during straight tracks. We could also include additional collectibles such as scoring items or temporary speed boosts.

The simplest goal of the agent is to follow the road tightly at its maximum speed and hope that it will learn to drift. To achieve this, it is necessary to identify and avoid any obstacles that come in the way and competitor’s vehicle. For better scenarios, that agent might also learn to strategically block competitors or bump them to obstacles.

There are two types of input to our model: camera view and lidar depth field. The camera view gives an RGB picture of what the car sees and we could potentially use CNN for road, obstacle, collectibles, and competitor’s car detection. The lidar depth field gives direct distances from the center of the car to its surroundings. Given the inputs, the model is expected to predict the optimal steering angle and accelerator usage.

{{< youtube PQ8m98DVrTo >}}