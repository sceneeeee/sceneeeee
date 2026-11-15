<h1 align="center">evenS</h1>

<p align="center">
  BEng student in <strong>Mechatronics and Robotic Systems</strong> at Xi'an Jiaotong-Liverpool University (XJTLU)<br/>
  Expected graduation: 2028<br/>
  <strong>Robotics · Embodied AI · Autonomous Navigation</strong>
</p>

<p align="center">
  <a href="https://github.com/sceneeeee/room-sign-guided-navigation">Room-Sign Navigation</a>
  ·
  <a href="https://github.com/sceneeeee/ETPNav-MID360-showcase">ETPNav × MID360</a>
  ·
  <a href="https://github.com/sceneeeee/navida-habitat">NaVIDA × Habitat</a>
  ·
  <a href="https://github.com/sceneeeee?tab=repositories">All repositories</a>
</p>

---

## About

I am an undergraduate engineering student interested in **robot navigation, embodied AI, and perception-grounded decision making**.

My work focuses on connecting visual and language-based reasoning with geometric perception and practical robot systems. I am particularly interested in how navigation methods can remain interpretable, experimentally testable, and transferable from simulation to real platforms.

**Research interests**
- Vision-and-Language Navigation (VLN) and embodied navigation
- RGB-based semantic search and landmark-guided reasoning
- RGB-D / LiDAR perception for mobile robots
- Waypoint prediction, topological planning, and navigation evaluation
- ROS 2-based robot integration and edge deployment

## Current Research

### [Room & Sign-Guided Indoor Navigation](https://github.com/sceneeeee/room-sign-guided-navigation)

An **RGB-first, human-in-the-loop** project exploring how room numbers and directional signs can guide search in unfamiliar indoor environments.

The system is designed around visual observations, OCR evidence, physical-door association, landmark memory, and high-level search decisions. The current implementation is a research prototype, not a completed autonomous room-search system.

**Progress**
- **M0:** The camera-capture, OCR, review, and export workflow has been merged into main.
- **M2.1–M2.4:** Evidence-aware landmark memory, a rule-based baseline, constrained text-LLM planning, Qwen3-4B integration, offline evaluation, and JSONL event streaming have been implemented in development branches.
- **Integration prototype:** [Draft PR #4](https://github.com/sceneeeee/room-sign-guided-navigation/pull/4) integrates M0 with M2.4 and adds an OCR-event adapter, RGB candidate detection, short-term visual tracking, and bounded human-confirmed visual guidance. These additions have offline tests, but still require real-camera validation.

**My contributions**
- M2.1–M2.4 reasoning and evaluation
- LandmarkMemory and evidence-aware rule-based reasoning
- Qwen3-4B text planner and constrained decision validation
- Offline evaluation framework and regression tests
- M1/M2 integration, M3/M4 integration design, and evaluation methodology

**Collaborator-led work:** the M0 camera/OCR field workflow and M1 room-sign perception / physical cross-frame association.

**Validation boundary:** robust physical-door association, real-camera integration, and controlled multi-door search evaluation remain ongoing. The complete search loop has **not** yet been demonstrated in the field.

## Completed Research & Engineering Projects

### [ETPNav × MID360](https://github.com/sceneeeee/ETPNav-MID360)

A discontinued research exploration of adapting ETPNav waypoint proposals to MID360-inspired sparse-depth geometry. The work includes explicit geometry variants (Geometry V0, BNMS, MRU, G-Min), sparse-depth zero-shot failure analysis, activation-level forensics, and a negative result showing simple feature-statistics alignment was insufficient.

The line was stopped before learned-adapter held-out validation, formal VLN benchmarking, Isaac Sim runtime, or physical MID360 deployment. The repository preserves the experiments and closeout record; it is **not current research**.

## Selected Engineering Projects

### [NaVIDA × Habitat](https://github.com/sceneeeee/navida-habitat)

Integrated the official NaVIDA-3B checkpoint with a stateful inference service and Habitat execution:
- 4-bit checkpoint loading on an RTX 4060 Ti 8GB
- Historical RGB observation handling and strict action-chunk parsing
- HTTP inference service and episode lifecycle management
- Model output → action parser → Habitat env.step() integration
- Multi-step smoke tests and auditable trajectory / latency logs

This validates an engineering integration path; it is **not** a standard R2R benchmark reproduction.

### [ROS 2 FishBot](https://github.com/sceneeeee/ros2-fishbot)

A completed **simulation-only** ROS 2 Humble workspace covering URDF/Xacro, Gazebo Classic, ros2_control differential drive, Nav2 maps/parameters, waypoint navigation, and a configurable patrol application with speech service and camera capture. No physical FishBot was purchased or deployed; hardware validation remains out of scope.

### [Bililive Recording & Upload Pipeline](https://github.com/sceneeeee/bililive-record-upload-pipeline)

A reproducible integration of recording, upload, retry, monitoring, and persistent cleanup workflows using Docker Compose, systemd, and SQLite-backed state tracking. The public repository documents its validation boundaries; natural-live end-to-end operation is still pending further verification.

### [Lecture-Grounded Tutorial Explainer](https://github.com/sceneeeee/lecture-grounded-tutorial-explainer)

A reusable ChatGPT Skill for explaining tutorials from supplied lecture materials, preserving source notation and connecting lecture concepts to step-by-step problem solving.

## Tools & Technologies

**Programming:** Python, C++

**Robotics:** ROS 2, Nav2, Gazebo Classic, Habitat

**Perception & AI:** PyTorch, OpenCV, OCR, Vision-Language Models

**Development:** Linux, Git, Docker

These are technologies used across my projects, rather than a claim of equal proficiency in every tool.

## Research Approach

I value controlled experiments, explicit system boundaries, reproducible evaluation, and honest reporting of negative results. I distinguish offline tests, simulation results, field observations, and benchmark results rather than treating them as interchangeable.

**Longer-term direction:** Isaac Sim, LiDAR-equipped mobile robots, and deployment-aware embodied navigation.
