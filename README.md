# John Peng

**Electrical & Computer Engineering @ USC · Class of 2027**
*Robotics, embedded systems, and the hardware that holds them together.*

I build robots and the electronics inside them: firmware, PCBs, actuator control, and the ROS 2 software on top. Currently at SRAM and Terra Labs, and running technical resources for USC Makers. Before that, LLM/RAG infrastructure at Manycore Tech and multi-legged locomotion research in USC's Robot Locomotion and Navigation Dynamics Lab.

LinkedIn: [linkedin.com/in/yc-john-peng](https://www.linkedin.com/in/yc-john-peng/)

Email: johnpeng {at} usc [dot] edu

---

## Experience

### **SRAM** | Advanced Development Engineering Intern
*Chicago, IL · Jun 2026 – Present*
* **PCB Design:** Compact Altium boards for AC-signal handling, balancing electrical performance against cost, manufacturability, and supply-chain constraints.
* **PCBA & Bring-Up:** Component selection, prototype assembly, board bring-up, and electrical debugging through design iteration.
* **Firmware & App:** Firmware and Android development for a resource-constrained embedded product.
* **Production Handoff:** Documentation, manufacturability review, and technical transition materials carrying an advanced-development product toward production.

### **Terra Labs** | Robotics Engineer → Project Manager
*Los Angeles, CA · Feb 2026 – Present*
* **Project Cove (Robotics Engineer):** Designed the control architecture for a 7-DOF arm on ROS 2, Raspberry Pi 5, and CAN-based BLDC actuators. Details in [Projects](#-cove-7-dof-robotic-arm).
* **Project Tether (Project Manager, Sep 2026 –):** Leading development of a 7-DOF inch-worm robot.

### **USC Makers** | Director of Technical Resources
*Los Angeles, CA · May 2026 – Present*
* **Knowledge Systems:** Built Confluence-style databases for tutorials, past-project documentation, and onboarding across a 100+ member engineering club.
* **Resource Indexing:** Cataloged hardware, software, and materials so teams stop re-solving the same problems.
* **Sponsorship:** Support company outreach by aligning club needs with industry partners.

### **Manycore Tech** | Machine Learning Engineer Intern, LLM/RAG
*Hangzhou, China · May 2025 – Jul 2025*
* **Knowledge-Graph RAG:** Built a KG-augmented retrieval pipeline on Alibaba Bailian and KuzuDB. Retrieval relevance up **40%**, latency down **20%** through optimized graph queries and vector-database integration.
* **Unified Retrieval:** Combined vector search, KG neighbor expansion, semantic filtering, and deduplication into a single retrieval path.
* **Agents:** LangChain agents for KG-driven multi-hop retrieval and evidence assembly across graph nodes.
* **Data Layer:** High-performance KnowledgeGraph module for CSV ingestion, schema construction, and traversal. Containerized with Docker.

### **Robot Locomotion and Navigation Dynamics Lab, USC** | Undergraduate Researcher
*Los Angeles, CA · Aug 2024 – Present*
* **Locomotion Research:** Multi-legged robot locomotion, focused on body-leg phase coordination and leg-obstacle interaction in cluttered terrain.
* **Phase Control:** Redesigned the coordination scheme from degree-based offsets to **normalized phase offsets**, improving gait consistency and cross-condition comparability.
* **Experimental Validation:** Ran **46 OptiTrack-tracked trials** with IR-marker 3D kinematics and built the data-processing pipeline to compare behavior across parameter configurations.
* **Mechanical Iteration:** Refined servo mounts, gear spacing, cable routing, and enclosure design for reliability in obstacle-heavy environments.

### **MFE Education** | IoT Systems Intern
*Shanghai, China · Jun 2024 – Jul 2024*
* **Device Library:** IoT communication library for Huawei's Astro Dashboard, taking users from sensor setup to live cloud visualization in under 10 lines of code.
* **Adoption:** Onboarding docs cut setup time by **50%**; tested and refined the framework with 70+ users.

---

## Projects

### FlexSense: Tactile Sensing for Scrambler
*2nd Place, Himalaya Robotics Hack 2026 · [ycjohnp/aruco-compliant-hand](https://github.com/ycjohnp/aruco-compliant-hand)*

<img src="https://raw.githubusercontent.com/ycjohnp/aruco-compliant-hand/main/docs/hud_wrapping.png" width="700">

Scrambler is a fully passive climbing hand for the Unitree G1 that lets the humanoid drop to all fours and scramble terrain steeper than it can walk, with no added motors, wiring, or firmware. TPU Fin Ray fingers turn the robot's body weight into grip force. Built in 36 hours; I owned the sensing side. Team overview on [Isaac Chan's site](https://www.isaac.engineering/projects/scrambler.html).

FlexSense is that sensing system: ArUco markers on each finger, tracked by a wrist camera, give a grip readout with zero electronics in the hand.

* **Pose Estimation:** Full 6-DoF marker tracking, with the IPPE pose ambiguity resolved frame-to-frame.
* **Calibration:** Screen-based camera calibration from an animated on-screen target, which outperformed a printed ChArUco board.
* **Simulation:** Co-rotational Euler-Bernoulli FEM solver with a Yeoh hyperelastic TPU model to predict finger deformation under load.
* **Live Tool:** Classifies each finger as wrapping, neutral, or back-bending and renders the bent CAD over the camera view. 123 unit tests.
* **Stack:** Python, OpenCV, NumPy. Developed on a LeRobot SO-101; platform-independent.

### Circuit Sensei: AI Agent for Breadboard Assembly
*LA Hacks 2026*

<img src="https://raw.githubusercontent.com/ycjohnp/pictures_for_lahacks/main/original_test_led.png" width="700">

Describe a circuit in plain language and Circuit Sensei walks you to a physically tested Arduino build.

* **Plan & Guide:** Generates a build plan and renders step-by-step breadboard diagrams.
* **Verify:** Checks each component placement through a webcam with Gemini Vision and blocks progression until the step is correct.
* **Test:** Generates Arduino code, uploads it over serial, and runs electrical tests on the finished circuit. Build and test steps are interleaved so mistakes surface where they happen.
* **Stack:** Gemini 2.5, FastAPI + WebSockets, React, ElevenLabs voice, Arduino Uno running a JSON command interpreter over USB serial.

<img src="https://raw.githubusercontent.com/ycjohnp/pictures_for_lahacks/main/Blank%20diagram%20(6).png" width="900">

### Cove: 7-DOF Robotic Arm
*Terra Labs · Robotics Engineer · Feb 2026 – Present · [ycjohnp/cove_motion_moveit2](https://github.com/ycjohnp/cove_motion_moveit2)*

A 7-DOF arm built in 10 weeks. I designed the control architecture: ROS 2 on a Raspberry Pi 5 commanding CAN-based BLDC actuators.

* **Interfaces:** ROS 2 topics for `/joint_states`, `/target_joints`, and `/estop_event`, linking high-level commands to actuator-level control.
* **Safety:** Hardware and software e-stop with heartbeat timeout, torque cutoff, and ROS 2 fault monitoring.
* **Simulation:** URDF with joint dynamics, transmission tags, and collision geometry for Gazebo and MoveIt 2.

### Tether: 7-DOF Inch-Worm Robot
*Terra Labs · Project Manager · Sep 2026 – Present*

Follow-on to Cove. A 7-DOF robot that locomotes by inching along a surface. In development.

### Vyz: Sensory Adaptation Headset
*Best Hardware Project, LA TechWeek AI/ML Buildathon · Oct 2025*

<p float="left">
<img src="https://github.com/RakshetaK/GVO-Repo/blob/main/Images/vyz-physical-wearable.JPG" width="300">
<img src="https://github.com/RakshetaK/GVO-Repo/blob/main/Images/vyz-compute-box.JPG" width="300">
</p>

A Jetson-powered headset that detects and mitigates visual and auditory overstimulation in real time.

* **Hardware:** NVIDIA Jetson Orin Nano, servo-actuated visor, adaptive RGB LEDs. I did the wire harnesses and power distribution across the servo, LED, and sensor subsystems.
* **Software:** Multithreaded Python with OpenCV brightness tracking, real-time SciPy audio filtering, and a Flask API to external inference.
* **Response:** GPT-3.5-based intervention engine selects parameters with end-to-end latency under **200 ms**.

### SkateMo: Autonomous Skateboard
*USC Makers · Technical Project Lead · Aug 2025 – May 2026*

Led a six-person team building a self-driving skateboard, owning integration across perception, navigation, and embedded control.

* **Perception:** OpenCV + YOLO obstacle detection with camera/IMU fusion.
* **Planning:** FSM-based path planning built around skateboard steering dynamics.
* **Control:** BLDC motor firmware for speed regulation, current limiting, and direction.
* **Integration:** Ran design reviews and full-system testing across electrical, mechanical, and software subsystems.

### Self-Assembling Modular Robot System
*Independent Research · [ycjohnp/self-assembling-modular-robots](https://github.com/ycjohnp/self-assembling-modular-robots)*

<img src="https://github.com/john02px/modular-robot/blob/main/modular-robot/Project%20Photos/Multi%20Module.JPG?raw=true" width="500">

Modules that locate one another, attach, and reconfigure to complete a task.

* **Mechanism:** 4-DoF modules with wheeled locomotion and electromagnetic connectors.
* **Control:** ESP32 microcontrollers with PID for precise positioning.
* **Localization:** AprilTags and OpenCV. Validated through assembly-speed, loaded, and connection-strength tests.

[![Modular Robot Demo](http://img.youtube.com/vi/8HDp2pXij3Y/0.jpg)](http://www.youtube.com/watch?v=8HDp2pXij3Y "Modular Robot Demo")

### Camshaft-Powered Braille Embosser
*Independent Research · [ycjohnp/novel-camshaft-braille-embosser](https://github.com/ycjohnp/novel-camshaft-braille-embosser)*

<img src="https://raw.githubusercontent.com/john02px/braille-embosser/main/Project%20Images%20and%20Diagrams/Machine%20Picture%20(with%20banana%20for%20scale).jpg" width="400">

Commercial embossers cost $2,000+ and rely on loud linear solenoids. This design uses a camshaft instead.

* **Cost:** ~$160 in parts.
* **Performance:** Under 60 dB operating noise, dot height held to ±0.12 mm.

### Karate Kid: Motion-Tracking Training Wearable
*USC Makers · Wireless Systems Lead · Feb 2025 – May 2025*

* **PCB:** Custom two-layer KiCad board with ESP32, 6-DoF IMU, and MOSFET-driven haptic motors.
* **Firmware:** Maps IMU quaternions onto a Unity skeleton over UDP.
* **Manufacturing:** BOM generation, stencil ordering, and reflow assembly for the prototype run.

### IoT Smart Room Control
*EE250 Final Project · [Repository](https://github.com/NamithGang/EE250FinalProject)*

<img src="https://raw.githubusercontent.com/NamithGang/EE250FinalProject/refs/heads/main/overall_diagram.png" width="700">

* **Stack:** Raspberry Pi 4 (vision, YOLOv3-Tiny presence detection) and Arduino Uno (actuation) over UART, with a web dashboard for control.

### Embedded Temperature Monitor
*USC Embedded Systems · Spring 2025*

<img src="https://raw.githubusercontent.com/ycjohnp/pictures_for_lahacks/main/20250429_004539.jpg" width="400">

* **Hardware:** DS18B20 sensor, LCD, rotary encoder, servo, RGB LED.
* **Firmware:** Timer-based control, EEPROM-stored thresholds, PWM, interrupts, and UART alerts.

