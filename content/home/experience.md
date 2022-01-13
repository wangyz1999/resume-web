---
# An instance of the Experience widget.
# Documentation: https://wowchemy.com/docs/page-builder/
widget: experience

# This file represents a page section.
headless: true

# Order that this section appears on the page.
weight: 20

title: Experience
subtitle:

# Date format for experience
#   Refer to https://wowchemy.com/docs/customization/#date-format
date_format: Jan 2006

# Experiences.
#   Add/remove as many `experience` items below as you like.
#   Required fields are `title`, `company`, and `date_start`.
#   Leave `date_end` empty if it's your current employer.
#   Begin multi-line descriptions with YAML's `|2-` multi-line prefix.
experience:
  - title: Student Researcher
    company: Creative Machines Lab
    company_url: 'https://www.creativemachineslab.com/'
    company_logo: cml
    location: New York, NY
    date_start: '2021-09-01'
    date_end: ''
    description: Directed by Prof. Hod Lipson and Ph.D. student Boyuan Chen, I created and implemented a supervised learning pipeline that learns the natural lips and facial movements through human speech visual-audio data. The pipeline utilizes a Wasserstein Generative Adversarial Network (WGAN) architecture conditioned on speech audio data and could generate face landmarks representing the facial movement implied by the audio. The model was trained on the VoxCeleb2 dataset, and I devised several data processing techniques including but not limited to facial landmarks extraction, visual-audio timing alignment, face alignment, and data distribution analysis. The pipeline will be integrated into the third generation of our face robot Eva to lip-synchronize its speech.
        
  - title: Student Worker
    company: USC Institute for Creative Technologies
    company_url: 'https://ict.usc.edu/'
    company_logo: ict
    location: Los Angeles, CA
    date_start: '2020-05-18'
    date_end: '2021-08-28'
    description: I did Cognitive Architecture, Reinforcement Learning, and Route Optimization research with Prof. Paul Rosenbloom and Research Associate Volkan Ustun. Collaborating with a team of 6 professionals, I started by developing a web application as a visualization and debugging tool for the (Py)Sigma Cognitive Architecture. Then, I created and co-developed an MDP semantic graph environment leveraging OpenAI Gym and NetworkX. With the environment, I led Reinforcement Learning experiments with DQN and PPO for Search-and-Rescue (SAR) route planning. I also co-developed Mixed-Integer Programming (MIP) models for SAR route planning utilizing Google OR-Tools. For the last half-year, I took ownership of the project and developed a Sequential Decision-making Framework using the Transformer Architecture for multi-agent Search and Rescue (SAR) Route Optimization. I have a first-author paper accepted to AAAI 2021 FSS. 

design:
  columns: '2'
---
