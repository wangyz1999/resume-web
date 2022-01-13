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
    description: |-2
      Multimodal Learning and Lip Syncronization Research:

      * Created the learning pipeline that generates face landmarks representing facial movements based on human speed audio data
      * Designed a sample efficient conditional WGAN deep learning architecture, trained on ~6000 videos using the VoxCeleb2 dataset
      * Initiated data analysis and pre-processing such as face alignment and audio processing to reduce training time within 15 mins
        
  - title: Student Worker
    company: USC Institute for Creative Technologies
    company_url: 'https://ict.usc.edu/'
    company_logo: ict
    location: Los Angeles, CA
    date_start: '2020-05-18'
    date_end: '2021-08-28'
    description: |-2
      Reinforcement Learning and Route Optimization Research:

      * Created and co-developed a MDP semantic graph environment using the OpenAI Gym and NetworkX
      * Led RL experiments using DQN and PPO for Search-and-Rescue (SAR) route optimization
      * Co-developed Mixed-Integer Programming (MIP) models for SAR route planning with Google OR-Tools
      * Led and Developed a Sequential Decision-making Framework by modifying the Transformer Architecture for multi-agent SAR
  
      Cognitive Architecture Research:

      * Front-End development of visulizing and debuging tool for (Py)Sigma Cognitive Architecture
      * Unit Testing, Literature Review

  - title: Research Assistant
    company: Institute of Computing Technology, Chinese Academy of Sciences
    company_url: 'http://english.ict.cas.cn/'
    company_logo: cas
    location: Beijing, China
    date_start: '2019-06-06'
    date_end: '2019-08-20'
    description: |-2
      Natural Language Processing Part-of-Speech Research:

      * Created and developed a Rule-Based Expert System to correct pos tagging errors
      * Data-Mined POS correction rules based on Stanford CoreNLP and NLPIR-ICTCLAS

design:
  columns: '2'
---
