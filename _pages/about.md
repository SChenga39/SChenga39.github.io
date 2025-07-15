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

_July 2025 ｜ OpenCV, Python, React_

This project explores an optimization-based approach to generate expressive, simplified sketches from complex images. Instead of relying on deep learning, the method is grounded in discrete optimization with direct human input — offering a balance between algorithmic control and user intent.

#### Objective

The core goal is to extract a **sparse and interpretable edge sketch** from a detailed image while preserving semantically important content. Users manually mark important areas (like faces, objects, etc.), and the system then selects a subset of edge segments that best represent those priorities — under a strict complexity constraint.

We formulate the problem as a **binary optimization** task:

$$
\max_{\mathbf{x} \in \{0,1\}^n} \sum_{i=1}^n w_i x_i \quad \text{s.t.} \quad \sum_{i=1}^n x_i \leq k
$$

Where:

- $x_i$ is a binary variable indicating whether to keep edge segment $e_i$
- $w_i$ is a weight (importance) derived from gradient strength and user annotations
- $k$ is the maximum number of edges allowed (sketch sparsity budget)

#### ️ Implementation Overview

I implemented this project using **Python + OpenCV** for the backend and **React** for the frontend interface.

#### Backend (Python OpenCV)

Key backend responsibilities include:

- **Edge Detection**: Using Canny to extract all potential edges.
- **Gradient Analysis**: Calculating edge strength and direction via Sobel operators.
- **User-Guided Scoring**: Incorporating user-defined importance using masks (e.g. must-keep, must-remove).
- **Optimization Loop**: Greedy selection of top-weighted edges within the user-defined budget, with penalties for redundant (parallel) edges and rewards for connectivity.

The optimization runs asynchronously in a background thread, allowing real-time UI feedback during interaction.

> Edge selection is influenced by a custom energy function considering gradient magnitude, neighborhood connectivity, and angular diversity — all hand-engineered without deep learning.

#### Frontend (React)

The frontend is a web-based interface that enables users to:

- **Upload an image**
- **Visualize Canny edge maps**
- **Draw masks** over important or unimportant regions via simple brush tools
- **Adjust parameters** like Canny thresholds and budget ratio using sliders
- **Preview final sketch output** after optimization

User actions are sent to the backend over HTTP, where the Python service processes the image and returns the updated sketch.

> User constraints are enforced via simple keyboard shortcuts (e.g., `K` for keep, `R` for remove), making the experience interactive and efficient.

#### Why It Matters

Unlike traditional sketch filters or learning-based simplifiers, this approach:

- Gives **explicit control** to the user
- Makes the logic **interpretable and tweakable**
- Works **offline**, without requiring large datasets or GPU support

It’s especially suited for creative applications, visual abstraction, or educational tools where clarity and human judgment are key.

#### Demo Workflow

1. Load an image into the frontend.
2. Use a brush tool to mark important (green) or unimportant (red) regions.
3. Adjust edge detection parameters and sparsity ratio as desired.
4. Let the system generate a sketch that reflects your priorities.
5. Save or further refine the result!

#### Tech Stack

- **Frontend**: React, HTML Canvas, Fetch API
- **Backend**: Python, OpenCV, NumPy, Matplotlib (for GUI)
- **Optimization Method**: Greedy selection based on weighted importance score
- **Image Communication**: HTTP + base64-encoded image buffers

</details>

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
