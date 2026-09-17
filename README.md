<h1 align="center">evenS</h1>

<p align="center">
  BEng student in Mechatronics and Robotic Systems at XJTLU<br/>
  Working on Vision-and-Language Navigation, embodied AI, and autonomous mobile robots
</p>

<p align="center">
  <a href="https://github.com/sceneeeee/ETPNav-MID360-showcase">ETPNav × MID360</a>
  ·
  <a href="https://github.com/sceneeeee/navida-habitat">NaVIDA × Habitat</a>
  ·
  <a href="https://github.com/sceneeeee/ros2-fishbot">ROS 2 FishBot</a>
  ·
  <a href="https://github.com/sceneeeee?tab=repositories">Repositories</a>
</p>

## About Me

I am an undergraduate student at **Xi'an Jiaotong-Liverpool University (XJTLU)**, pursuing a BEng in **Mechatronics and Robotic Systems** (expected 2028).

My current work sits at the intersection of **robot navigation, embodied AI, and robot perception**. I am particularly interested in how learned navigation policies can be connected to geometric sensing and deployed on practical robotic systems.

**Research interests**

- Vision-and-Language Navigation (VLN)
- Embodied AI and robot navigation
- LiDAR / RGB-D perception for navigation
- Learning-based waypoint proposal and topological planning
- ROS 2, Nav2, simulation, and robot deployment

## Current Research

### [ETPNav × MID360](https://github.com/sceneeeee/ETPNav-MID360-showcase)

I am studying whether an RGB-D-based VLN system can retain its learned navigation prior when dense depth is replaced by **MID360-like sparse LiDAR geometry**.

The project currently focuses on the waypoint interface while keeping the downstream **GraphMap and language/topological planning pipeline** frozen whenever possible. Work so far includes explicit-geometry waypoint baselines, proposal–GraphMap interface analysis, sparse-depth zero-shot experiments, activation-level failure forensics, and feature-domain adaptation studies.

The longer-term path is **Habitat / R2R-CE → Isaac Sim native LiDAR → Livox MID360 + real robot navigation**.

**Public research materials:** [Research Showcase](https://github.com/sceneeeee/ETPNav-MID360-showcase) · [Application Summary](https://github.com/sceneeeee/ETPNav-MID360-showcase/blob/main/docs/APPLICATION_SUMMARY.md) · [Detailed Overview](https://github.com/sceneeeee/ETPNav-MID360-showcase/blob/main/docs/RESEARCH_OVERVIEW.md)

## Selected Projects

### [navida-habitat](https://github.com/sceneeeee/navida-habitat)

A paper-oriented integration of the official **NaVIDA** checkpoint with Habitat. The project implements a stateful inference service, historical RGB observation handling, strict action-chunk parsing, and closed-loop Habitat execution.

Highlights:

- official NaVIDA-3B checkpoint running in **4-bit on an RTX 4060 Ti 8GB**;
- paper-pure RGB + language inference protocol;
- stateful localhost HTTP service and episode lifecycle;
- end-to-end model → action parser → `env.step()` smoke testing;
- auditable logging for actions, latency, trajectories, and evaluation outputs.

### [ros2-fishbot](https://github.com/sceneeeee/ros2-fishbot)

A **ROS 2 Humble** mobile-robot workspace covering the main navigation software chain:

`URDF / Xacro → Gazebo → ros2_control → Nav2 → waypoint navigation → autonomous patrol`

It includes robot description, differential-drive control, localization/navigation configuration, Python navigation examples, custom services, patrol behaviors, and camera capture.

### [VLN](https://github.com/sceneeeee/VLN)

A deployment-oriented VLN scaffold connecting a **Jetson-side ROS 2 robot** with a remote GPU inference server. It covers camera history, remote NaVIDA inference, bounded action execution, `/cmd_vel`, and the STM32 serial chassis bridge.

## Technical Stack

<p>
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/C++-00599C?style=flat&logo=cplusplus&logoColor=white" />
  <img src="https://img.shields.io/badge/ROS%202-22314E?style=flat&logo=ros&logoColor=white" />
  <img src="https://img.shields.io/badge/Nav2-22314E?style=flat&logo=ros&logoColor=white" />
  <img src="https://img.shields.io/badge/PyTorch-EE4C2C?style=flat&logo=pytorch&logoColor=white" />
  <img src="https://img.shields.io/badge/OpenCV-5C3EE8?style=flat&logo=opencv&logoColor=white" />
  <img src="https://img.shields.io/badge/Habitat-111111?style=flat" />
  <img src="https://img.shields.io/badge/Gazebo-F58113?style=flat" />
  <img src="https://img.shields.io/badge/Linux-FCC624?style=flat&logo=linux&logoColor=black" />
  <img src="https://img.shields.io/badge/Git-F05032?style=flat&logo=git&logoColor=white" />
</p>

## Currently Learning / Building Toward

- stronger VLN experimentation and evaluation methodology;
- LiDAR-aware navigation perception;
- Isaac Sim robotics workflows;
- deployment-aware embodied navigation on edge robotics platforms.
