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
  - title: Masters Researcher
    company: Creative Machines Lab
    company_url: 'https://www.creativemachineslab.com/'
    company_logo: cml
    location: New York, NY
    date_start: '2021-09-01'
    date_end: ''
    description: |-2
      **Emotion Stylizable Talking Face Generation (Ongoing)**

      * Developed a generative model that synthesize facial landmark movements synching up with a given speech audio wav. The model can *zero-shot learning* to unknown speakers and languages.
      * Applied self-supervised representation learning to disentangle speech audio signal into content representation and prosody (emotion) representation via *information bottleneck*.
      * Aiming to stylize talking emotion by controlling the prosody representation and synthesize photo-realistic videos of talking faces with authentic lips movement, facial expression, and head poses  
  
  
      **Meta Self-Model: A Single Model That Can Control over 1024 Differently Configured Legged Robot in Simulation (Ongoing)**

      * Developed a single model that can predicts the future states (position, orientation, and joint angles) of 1024 differently configured legged robots each with 12 degree of freedom (4 legs each 3 joints), giving robots a sense of self-configuration and motion dynamics. 
      * Given forward baseline motion, I optimize the trajectories by applying *Beam Search* with added action noise, which improves robots’ performance in forward baseline motion and could perform unlearned tasks such as turning and backward movement with custom reward function.
      * Conducted a comprehensive literature review on Point Cloud Representation/Classification
      * Designed *Multi-Tasks Learning (MTL)* Objectives and *Auxiliary Tasks* to automatically balance training tasks difficulties
  

      **Lip synchronization for Animatronic Robot Face**

      * Designed and created a pipeline that can generate facial landmarks (lips and holistic facial expression) synchronized with a given speech audio. The landmarks are then converted into robot face motor commands via an inverse model.
      * The pipeline supports real-time inference and *zero-shot learn* to unknown languages and speakers
      * Pretrained an *Autoregressive Predictive Coding (APC)* model for speech audio embedding
      * Data Processing of the *VoxCeleb2 Dataset* (Landmark extraction, speech enhancing, landmark alignment, etc.)


      **Human-Robot Facial Simultaneous Expression**

      * Developed a predictive model that anticipates human facial expression changes thereby realizing simultaneous human facial expression mimicking (Simexpression).
      * Attempted various facial landmark alignment techniques (rotation and scaling, affine alignment, 3D alignment by shifting viewing frustum)
      * Extracted facial landmarks and applied *Head Pose Estimation* to remove lateral faces
  
        
  - title: Research Assistant
    company: USC Institute for Creative Technologies
    company_url: 'https://ict.usc.edu/'
    company_logo: ict
    location: Los Angeles, CA
    date_start: '2020-05-18'
    date_end: '2021-08-28'
    description: |-2
      **Route Optimization in Service of a Search and Rescue Artificial Social Intelligence Agent**

      * Investigated various *Graph Transformer* models for efficiently and approximately solving route optimization problems such as *Travelling Salesman Problem (TSP)* and *Capacitated Vehicle Routing Problem (CVRP)*.
      * Designed a *Coorperative Multi-Agent Reinforcement Learning* system where agents with different roles and capabilities use the said *Graph Transformer* models as the oracle to get approximately optimal paths and coorperate to solve a Search-and-Rescue task in a Minecraft environment.
      * Developed a *Markov Decision Process (MDP)* Semantic Graph environment to simulate search and rescue tasks and conduct deep reinforcement learning experiment with *Proximal Policy Optimization (PPO)* on the environment for route optimization
      * Devised *Mixed-Integer Programming (MIP)* Solutions to Discounted Reward Travelling Salesman Problem for Search and Rescue Tasks


      **PySigma Cognitive Architecture**

      * Unit Testing and front-end development to PySigma Cognitive Architecture
      * Literature review on message-passing inference algorithms for probabilistic graphical models.


  - title: Research Assistant
    company: Institute of Computing Technology, Chinese Academy of Sciences
    company_url: 'http://english.ict.cas.cn/'
    company_logo: cas
    location: Beijing, China
    date_start: '2019-05-06'
    date_end: '2019-08-20'
    description: |-2
      **Chinese Part of Speech Tagging Error Correction**

      * Developed a Rule-Based Expert System that corrects *Chinese Part of Speech (POS)* Tagging errors made by neural language models.
      * Designed a pipeline that discovers new POS tagging rules based on similarity analysis between the POS tagging results from Stanford CoreNLP model and NLPIR-ICTCLAS POS Tagging System

design:
  columns: '2'
---
