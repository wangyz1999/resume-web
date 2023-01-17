---
# An instance of the Experience widget.
# Documentation: https://wowchemy.com/docs/page-builder/
widget: experience

# This file represents a page section.
headless: true

# Order that this section appears on the page.
weight: 30

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
  - title: Advanced Masters Researcher
    company: Creative Machines Lab
    company_url: 'https://www.creativemachineslab.com/'
    company_logo: cml
    location: New York, NY
    date_start: '2021-09-01'
    date_end: ''
    description: |-2  
      **Learning Robot Morphology Representation from Kinematic Data**

      * Developed a multiclass-multioutput classification model that predicts the morphology of a 12-DoF quadruped robot given its dynamics, which is represented as multinomial time series of robot position, orientation, and joint angles. The robot's structure can be configured in countless ways.

      **Talking Face Generation for Lip-Synchronizing Animatronic Robot Face**

      * Developed a deep regression model, Audio2Landmark, that generates lip-synced facial landmark movements given speech audio alone. Applied the model to lip-sync a face robot.
        
  - title: Research Assistant
    company: USC Institute for Creative Technologies
    company_url: 'https://ict.usc.edu/'
    company_logo: ict
    location: Los Angeles, CA
    date_start: '2020-03-18'
    date_end: '2021-08-28'
    description: |-2
      **Route Optimization on Graphs Using Reinforcement Learning**

      * Developed a sequential decision making framework that efficiently and approximately solves multi-agent route optimization problems such as *Capacitated Vehicle Routing Problem (CVRP)* utilizing *Graph Transformer* model and Reinforcement Learning.

      **PySigma Cognitive Architecture**

      * Unit Testing and front-end development to the (Py)Sigma Cognitive Architecture.

  # - title: Research Assistant
  #   company: Institute of Computing Technology, Chinese Academy of Sciences
  #   company_url: 'http://english.ict.cas.cn/'
  #   company_logo: cas
  #   location: Beijing, China
  #   date_start: '2019-05-06'
  #   date_end: '2019-08-20'
  #   description: |-2
  #     **Chinese Part of Speech Tagging Error Correction**

  #     * Developed a Rule-Based Expert System that corrects Chinese *Part of Speech (POS)* Tagging errors made by SOTA language models.

design:
  columns: '2'
---
