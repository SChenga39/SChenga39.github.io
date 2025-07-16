---
permalink: /
title: ""
author_profile: true
redirect_from:
  - /about/
  - /about.html
---

## Introduction

<!-- Self Introduction -->

## Education

### Computer Science and Communications Engineering

Research on Mobile Communication

_Waseda University, Tokyo, Japan_

_2025-2027_

### Measurement, Control Technology and Instruments

_Wuhan University of Technology, Wuhan, China_

_2020-2024_

## Skills

<!-- Image Example -->

<!-- ![Editing a Markdown file for a talk](/images/editing-talk.png) -->

- Programming: Python, C++, Java, Go
- Software Development: Git, CI/CD
- Computer Vision: OpenCV
- GUI Design: Qt

## Projects

### Sketch Simplification via Human-Guided Sparse Edge Selection

_July 2025 ｜ OpenCV, Python (Flask), React_

This project explores an optimization-based approach to generate expressive, simplified sketches from complex images. Instead of relying on deep learning, the method is grounded in discrete optimization with direct human input — offering a balance between algorithmic control and user intent.

Key backend responsibilities include:

- **Edge Detection**: Using Canny to extract all potential edges.
- **Gradient Analysis**: Calculating edge strength and direction via Sobel operators.
- **User-Guided Scoring**: Incorporating user-defined importance using masks (e.g. must-keep, must-remove).
- **Optimization Loop**: Greedy selection of top-weighted edges within the user-defined budget, with penalties for redundant (parallel) edges and rewards for connectivity.

The optimization runs asynchronously in a background thread, allowing real-time UI feedback during interaction.

> Edge selection is influenced by a custom energy function considering gradient magnitude, neighborhood connectivity, and angular diversity — all hand-engineered without deep learning.

The frontend is a web-based interface that enables users to:

- **Upload an image**
- **Visualize Canny edge maps**
- **Draw masks** over important or unimportant regions via simple brush tools
- **Adjust parameters** like Canny thresholds and budget ratio using sliders
- **Preview final sketch output** after optimization

User actions are sent to the backend over HTTP, where the Python service processes the image and returns the updated sketch.

> User constraints are enforced via simple keyboard shortcuts (e.g., `K` for keep, `R` for remove), making the experience interactive and efficient.

### Face Recognition Access Control System

_Mar 2024 ｜ STM32, C++_

Graduation project focused on embedded system development (hardware and software).

- Developed a secure access control system with facial recognition, card swipe, and password unlock functions
- Added card swipe logging and intrusion detection with automatic image capture

### Temperature & Pressure Monitoring System for Injection Wells

_Dec 2023 ｜ Qt, C++_

Course project for upper-computer application development.

- Collected and visualized real-time data from embedded devices using Qt GUI components
- Stored historical data in a local SQLite database

### Quiz Buzzer System Using STC89C52

_Dec 2022 ｜ STC89C52, C_

Microcontroller application for embedded systems course.

- Designed a 4-player quiz buzzer with conflict-free matrix keypad input
- Included system reset functionality

### Exam System for International School

_Apr 2022 ｜ Vue, JavaScript_

Frontend development for a collaborative exam platform project.

- Modified the user interface to meet the client’s requirements
- Integrated a video player component and adjusted the playback strategy to ensure each video can be played once and only once
