<h1 align="center">evenS</h1>

<p align="center">
  BEng student in <strong>Mechatronics and Robotic Systems</strong> at Xi'an Jiaotong-Liverpool University (XJTLU)<br/>
  Expected graduation: <strong>2028</strong> · Based in Suzhou, China<br/>
  <strong>Robotics Software · Embodied AI · Autonomous Navigation · Reproducible Evaluation</strong>
</p>

<p align="center">
  <a href="https://github.com/sceneeeee/room-sign-guided-navigation">Room-Sign Navigation</a> ·
  <a href="https://github.com/sceneeeee/navida-habitat">NaVIDA × Habitat</a> ·
  <a href="https://github.com/sceneeeee/ETPNav-MID360">ETPNav × MID360</a> ·
  <a href="https://github.com/sceneeeee/ros2-fishbot">ROS 2 FishBot</a> ·
  <a href="https://github.com/sceneeeee?tab=repositories">All repositories</a>
</p>

## About

I am a third-year robotics undergraduate interested in connecting **visual perception, language-grounded reasoning, and reliable robot software**. My projects span RGB-based indoor navigation, vision-and-language navigation (VLN) model integration, geometric waypoint experiments, ROS 2 simulation, and reproducible engineering workflows.

I work primarily with **Python, C++, PyTorch, OpenCV, ROS 2, Nav2, Gazebo, Habitat, Linux, Git, and Docker**. These are tools used across different projects, not a claim of equal proficiency in every technology.

**Current focus:** RGB-first, human-in-the-loop room/sign-guided navigation. I am also seeking internships in robotics software, embodied AI engineering, perception, and simulation/evaluation.

## Current Research

### [Room & Sign-Guided Indoor Navigation](https://github.com/sceneeeee/room-sign-guided-navigation) — RGB, OCR, reasoning and bounded guidance

A two-person research testbed investigating whether observed room numbers and directional signs can guide the search for an unknown indoor room without a pre-annotated target location. Its current handheld stage uses **one RGB camera**; depth, SLAM and Nav2 are not part of this perception/reasoning pipeline.

**Verified progress**
- **M0:** Camera capture, RapidOCR, human review and data export are merged into `main` ([PR #1](https://github.com/sceneeeee/room-sign-guided-navigation/pull/1)).
- **M2.1–M2.4:** Evidence-aware `LandmarkMemory`, room-number Rule baseline, constrained Qwen3-4B text planner, offline evaluation and JSONL event streaming are merged via [PR #4](https://github.com/sceneeeee/room-sign-guided-navigation/pull/4) (**merged on Nov 7**, despite its historical WIP title/body).
- **M1 / M3:** OCR-event ingestion, RGB door/sign proposals, short-lived tracks, bounded camera-relative suggestions and regression tests are integrated. [PR #6](https://github.com/sceneeeee/room-sign-guided-navigation/pull/6) added validation/export of **21 human-reviewed instance records across 20 keyframes**; the review includes incomplete frames.
- **Recorded-video evaluation:** M3.1 runs detector → track → ROI OCR → M1/M2.4 → M3 on real *prerecorded* videos. M3.2 provides limited door-inspection suggestions, with `motion_authorized=false`. See [recorded-video validation](https://github.com/sceneeeee/room-sign-guided-navigation/blob/main/docs/m31-validation-summary.md) and [M3.2 boundary](https://github.com/sceneeeee/room-sign-guided-navigation/blob/main/docs/m32-door-approaching.md).

**My contributions:** M2 reasoning and offline evaluation, rule/text-LLM comparisons, strict decision validation, JSONL replay/integration, and M3/M4 experiment planning. **Collaborator-led contributions:** M0 field capture/OCR and M1 perception, annotation and physical-door association. Integrated modules reflect joint project work, not sole authorship.

**Boundary:** Offline tests, candidate detection and prerecorded-video suggestions do **not** establish a live multi-door room-finding loop, trustworthy physical-door identity across sessions, collision-free robot motion, or verified goal discovery. M3.3 human-in-the-loop live acceptance is pending.

## Completed Research and Engineering

### [NaVIDA × Habitat](https://github.com/sceneeeee/navida-habitat) — real-checkpoint integration and separate systems showcase

**SURF research period (Jul 2026): real model experiments.** I developed the NaVIDA-side runtime and stateful HTTP policy service and contributed the evaluator-side HTTP adapter and grounded demo to the [SURF team Habitat repository](https://github.com/RtimesC/habitat-lab). Evidence includes:
- Loading and running the **official NaVIDA-3B checkpoint in 4-bit (NF4)** on an RTX 4060 Ti 8GB; processing RGB observation history, language instructions and constrained action chunks.
- Model/service → HTTP → Habitat execution integration, including a five-step engineering smoke test.
- An **80-step, instruction/goal-grounded single-episode test with the real checkpoint**. Execution completed, but NaVIDA **did not reach the goal** (success 0, SPL 0; about 8.620 m final goal distance). This is one historical episode, **not an official VLN benchmark**. The separate Oracle's success is not a NaVIDA result.

**Post-SURF engineering closeout (Nov 15, 2026): deterministic Fake Policy.** I consolidated a provenance-tracked evaluator subset and validated real Habitat rendering, localhost HTTP, action queues, recorded poses and video. The final **21-action / 21-request** engineering showcase uses a **deterministic Fake Policy, not the NaVIDA checkpoint**, and demonstrates system execution rather than learned navigation. See [validation evidence](https://github.com/sceneeeee/navida-habitat/blob/main/docs/validation-report.md), [provenance](https://github.com/sceneeeee/navida-habitat/blob/main/docs/evaluator-provenance.md) and [labelled demo](https://github.com/sceneeeee/navida-habitat/blob/main/docs/engineering-demo.md).

The SURF research line and this engineering deliverable are **completed**. No successful learned-navigation benchmark, model training, physical-robot deployment or fresh post-migration checkpoint replay is claimed.

### [ETPNav × MID360](https://github.com/sceneeeee/ETPNav-MID360) — sparse-depth waypoint experiments (closed Nov 16, 2026)

Investigated adapting an ETPNav / Habitat waypoint proposal interface from dense RGB-D to **MID360-inspired sparse geometry**, while keeping downstream GraphMap and language/topological planning as stable as possible.

- Reproduced the original ETPNav pathway, refactored waypoint providers and tested interface equivalence.
- Implemented and compared **Geometry V0, bounded NMS (BNMS), middle-range utility (MRU), and G-Min**; audited how candidate geometry interacts with GraphMap.
- Ran controlled sparse-depth zero-shot tests and **activation-level failure analysis**. The frozen waypoint predictor collapsed despite partly active depth-encoder features; simple feature-statistics alignment did not recover the predictor.
- Reported comparisons on a **fixed 20-episode development panel**, not an official R2R-CE benchmark; see [closeout and evidence pack](https://github.com/sceneeeee/ETPNav-MID360/blob/main/docs/project-closeout.md).

**Boundary:** The sparse observations were deterministic approximations derived from simulated dense depth, **not real Livox MID360 scans**. Learned-adapter validation, Isaac Sim runtime and physical hardware deployment were not completed. This research line has been discontinued.

### [ROS 2 FishBot](https://github.com/sceneeeee/ros2-fishbot) — mobile-robot simulation (completed)

Built a **simulation-only** ROS 2 Humble workspace spanning URDF/Xacro robot descriptions, Gazebo Classic, `ros2_control` differential-drive control, Nav2 map navigation, Python `nav2_simple_commander` waypoint examples, and a configurable patrol application with speech-service and camera-capture interfaces. [Closeout](https://github.com/sceneeeee/ros2-fishbot/blob/main/docs/project-closeout.md). **No physical FishBot deployment is claimed.**

### [Bililive Recording & Upload Pipeline](https://github.com/sceneeeee/bililive-record-upload-pipeline) — reproducible software integration

Integrated existing recording/upload components with pinned upstream versions, SHA-256-verified patches, Docker Compose/systemd operations, SQLite-backed conservative cleanup, and Python/Node.js regression checks. The repository distinguishes historical production evidence from the **current public prerelease**, which has **not** passed a complete fresh-host production end-to-end acceptance. [Validation boundaries](https://github.com/sceneeeee/bililive-record-upload-pipeline/blob/main/docs/validation.md).

### [Lecture-Grounded Tutorial Explainer](https://github.com/sceneeeee/lecture-grounded-tutorial-explainer) — reusable ChatGPT Skill

Designed a source-first tutorial-explanation workflow that uses the learner's lecture materials, preserves notation, connects relevant figures to each question, and builds step-by-step solutions. It is a **Skill specification**, not a claim of a deployed standalone tutoring service.

## Industry Experience

**Package Testing Intern · Goertek Microelectronics Co., Ltd.** · Aug–Sep 2025

Exposure to semiconductor packaging/testing operations and industrial quality-oriented workflows under team supervision.

## Engineering Approach

I prefer explicit interfaces, controlled comparisons, tests and reproducible artifacts over unsupported performance claims. I distinguish **unit tests, recorded-video experiments, simulation engineering demonstrations, single-episode results and standardized benchmarks**. Research negative results and incomplete validation gates are documented rather than presented as successes.

**Longer-term interests:** deployable embodied navigation, 3D perception and robot software integration.
