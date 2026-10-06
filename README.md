# John Peng

Electrical and Computer Engineering student at the University of Southern California, graduating December 2027. My work centers on robotics and embedded systems: firmware, PCB design, actuator control, and the ROS 2 software that ties them together.

Currently an Advanced Development Engineering Intern at SRAM, a Robotics Engineer and Project Manager at Terra Labs, and Director of Technical Resources for USC Makers. Previously a Machine Learning Engineer Intern at Manycore Tech, and an undergraduate researcher in the Robot Locomotion and Navigation Dynamics Lab at USC since 2024.

[LinkedIn](https://www.linkedin.com/in/yc-john-peng/) · johnpeng@usc.edu

---

## Projects

### FlexSense: Tactile Sensing for Scrambler, a Passive Humanoid Climbing Hand
2nd Place, Himalaya Robotics Hack · 2026 · [ycjohnp/aruco-compliant-hand](https://github.com/ycjohnp/aruco-compliant-hand)

<img src="https://raw.githubusercontent.com/ycjohnp/aruco-compliant-hand/main/docs/hud_wrapping.png" width="700">

Scrambler is a fully passive climbing hand for the Unitree G1 that lets the humanoid drop to all fours and scramble terrain steeper than it can walk, with no added motors, wiring, or firmware. TPU Fin Ray fingers convert the robot's body weight into grip force. Built in 36 hours with a team; I owned the sensing side. Project overview on teammate Isaac Chan's site: [Scrambler](https://www.isaac.engineering/projects/scrambler.html).

FlexSense is that sensing system. ArUco markers on each finger are tracked by a wrist-mounted camera, and the measured marker poses are used to reconstruct finger deflection, giving the robot a grip readout with zero electronics in the hand. The live tool classifies each finger as wrapping, neutral, or back-bending and renders the deformed finger CAD over the camera view.

Key components:
- Full 6-DoF marker pose estimation, including resolution of the IPPE pose ambiguity through frame-to-frame tracking
- Screen-based camera calibration using an animated on-screen target, which produced lower-error intrinsics than a printed ChArUco board
- A co-rotational Euler-Bernoulli finite element solver with a Yeoh hyperelastic model for printed TPU, used to predict Fin Ray finger deformation under a given grip force
- 123 unit tests, including solver validation against the elastica and large-rotation benchmarks

Developed on a LeRobot SO-101 arm; the pipeline is platform-independent. Python, OpenCV, NumPy.

### Circuit Sensei: AI Agent for Breadboard Circuit Assembly and Verification
LA Hacks, April 2026

<img src="https://raw.githubusercontent.com/ycjohnp/pictures_for_lahacks/main/original_test_led.png" width="700">

An agent that takes a natural-language circuit goal and guides the user to a physically tested Arduino circuit. It generates a build plan, renders step-by-step breadboard diagrams, verifies each component placement through a webcam using Gemini Vision, and blocks progression until the step is correct. On completion it generates Arduino code, uploads it over serial, and runs electrical tests against the assembled circuit. Build and test steps are interleaved so errors are caught at the step where they occur.

<img src="https://raw.githubusercontent.com/ycjohnp/pictures_for_lahacks/main/Blank%20diagram%20(6).png" width="900">

Stack: Gemini 2.5 for planning and vision, FastAPI with WebSockets, React, ElevenLabs voice, and an Arduino Uno running a JSON command interpreter over USB serial.

### Cove: 7-DOF Robotic Arm
Terra Labs · Robotics Engineer · February 2026 – present · [ycjohnp/cove_motion_moveit2](https://github.com/ycjohnp/cove_motion_moveit2)

A 7-DOF arm built in 10 weeks. I designed the control architecture: ROS 2 on a Raspberry Pi 5 commanding CAN-based BLDC actuators.
- ROS 2 interfaces for `/joint_states`, `/target_joints`, and `/estop_event`, linking high-level commands to actuator-level control
- Hardware and software e-stop with heartbeat timeout, torque cutoff, and ROS 2 fault monitoring
- URDF with joint dynamics, transmission tags, and collision geometry for Gazebo and MoveIt 2 integration

### Tether: 7-DOF Inch-Worm Robot
Terra Labs · Project Manager · September 2026 – present

Follow-on project to Cove: a 7-DOF robot that locomotes by inching along a surface. Currently in development.

### Vyz: Sensory Adaptation Headset
Best Hardware Project, LA TechWeek AI/ML Buildathon · October 2025

<p float="left">
<img src="https://github.com/RakshetaK/GVO-Repo/blob/main/Images/vyz-physical-wearable.JPG" width="300">
<img src="https://github.com/RakshetaK/GVO-Repo/blob/main/Images/vyz-compute-box.JPG" width="300">
</p>

A Jetson-powered headset that detects and mitigates visual and auditory overstimulation in real time. OpenCV tracks ambient brightness and drives a servo-actuated visor; a microphone feeds a real-time SciPy audio filter. A GPT-3.5-based intervention engine selects response parameters, with end-to-end latency under 200 ms. I was responsible for the multithreaded Python architecture, wire harnessing, and power distribution across the servo, LED, and sensor subsystems.

### SkateMo: Autonomous Skateboard
USC Makers · Technical Project Lead · August 2025 – May 2026

Led a six-person team building a self-driving skateboard, owning integration across perception, navigation, and embedded control. Perception used OpenCV and YOLO with camera/IMU fusion; path planning was FSM-based and designed around skateboard steering dynamics; BLDC motor firmware handled speed regulation and current limiting. Ran design reviews and integration testing across the electrical, mechanical, and software subsystems.

### Self-Assembling Modular Robot System
[ycjohnp/self-assembling-modular-robots](https://github.com/ycjohnp/self-assembling-modular-robots)

<img src="https://github.com/john02px/modular-robot/blob/main/modular-robot/Project%20Photos/Multi%20Module.JPG?raw=true" width="500">

Independent research project. Each module has 4 DoF, wheeled locomotion, and electromagnetic connectors, allowing units to locate one another, attach, and reconfigure to complete tasks. ESP32 microcontrollers with PID control for motion; AprilTags and OpenCV for localization. Validated through tests of assembly speed, loaded performance, and connection strength.

[Demo video](https://www.youtube.com/watch?v=8HDp2pXij3Y)

### Camshaft-Powered Braille Embosser
[ycjohnp/novel-camshaft-braille-embosser](https://github.com/ycjohnp/novel-camshaft-braille-embosser)

<img src="https://raw.githubusercontent.com/john02px/braille-embosser/main/Project%20Images%20and%20Diagrams/Machine%20Picture%20(with%20banana%20for%20scale).jpg" width="400">

Independent research project. Commercial embossers cost $2,000 or more and rely on loud linear solenoids. This design replaces them with a camshaft mechanism, bringing the parts cost to approximately $160, operating noise below 60 dB, and dot height tolerance to ±0.12 mm.

### Karate Kid: Motion-Tracking Training Wearable
USC Makers · Wireless Systems Lead · February – May 2025

Designed a custom two-layer PCB in KiCad integrating an ESP32, a 6-DoF IMU, and MOSFET-driven haptic motors. Wrote firmware mapping IMU quaternion data to a Unity skeleton over UDP, and managed the full PCBA process including BOM generation, stencil ordering, and reflow assembly.

### Additional Projects
- **IoT Smart Room Control** (EE250): Raspberry Pi 4 running YOLOv3-Tiny for presence detection, Arduino Uno for actuation, UART communication, and a web dashboard. [Repository](https://github.com/NamithGang/EE250FinalProject)
- **Embedded Temperature Monitor**: DS18B20 sensor, LCD, rotary encoder, servo, and RGB LED with EEPROM-stored thresholds and UART alerts. Implemented timer, interrupt, and PWM handling directly.

  <img src="https://raw.githubusercontent.com/ycjohnp/pictures_for_lahacks/main/20250429_004539.jpg" width="400">

---

## Experience

**SRAM** · Advanced Development Engineering Intern · Chicago, IL · June 2026 – present
Compact PCB design in Altium for AC-signal handling, balancing performance, cost, and manufacturability. PCBA support including component selection, bring-up, and debugging. Firmware and Android development for a resource-constrained device, and documentation supporting the transition from prototype to production.

**Terra Labs** · Robotics Engineer (February 2026 – present), Project Manager (September 2026 – present) · Los Angeles, CA
Projects Cove and Tether, described above.

**USC Makers** · Director of Technical Resources · May 2026 – present
Lead technical resource development for a 100+ member engineering club: documentation systems, tutorials, parts and project indexing, and sponsor and industry outreach.

**Manycore Tech** · Machine Learning Engineer Intern, LLM/RAG · Hangzhou, China · May – July 2025
Built a knowledge-graph-augmented RAG pipeline on Alibaba Bailian and KuzuDB, combining vector search, graph neighbor expansion, semantic filtering, and deduplication into a unified retrieval path. Improved retrieval relevance by 40% and reduced latency by 20%. Developed LangChain agents for multi-hop retrieval and containerized the system with Docker.

**Robot Locomotion and Navigation Dynamics Lab, USC** · Undergraduate Researcher · August 2024 – present
Research on multi-legged locomotion and body-leg phase coordination in cluttered environments. Redesigned the phase-control scheme from degree-based offsets to normalized phase offsets, executed 46 OptiTrack-tracked trials, built the kinematic data-processing pipeline, and iterated on the robot's mechanical and enclosure design.

**MFE Education** · IoT Systems Intern · Shanghai, China · June – July 2024
Developed an IoT device communication library for Huawei's Astro Dashboard, taking users from sensor setup to live cloud visualization in under 10 lines of code. Onboarding documentation reduced setup time by 50% across 70+ users.

---

## Skills

**Languages:** Python, C/C++, Java, MATLAB, Verilog, SQL
**Robotics:** ROS 2, MoveIt, Gazebo, motion control, PID, BLDC and servo actuators
**Embedded:** ESP32, Raspberry Pi, NVIDIA Jetson, RTOS, firmware debugging, hardware/software integration
**Protocols:** CAN, I2C, SPI, UART, USB, Ethernet, TCP/IP, BLE
**Hardware:** Altium, KiCad, schematic capture, PCB layout, PCBA, reflow assembly, oscilloscopes, logic analyzers
**AI/ML:** PyTorch, OpenCV, YOLO, LangChain, vector databases, LLM APIs
**Tools:** Git, Docker, Linux
