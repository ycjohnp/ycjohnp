# Hi there, I'm John Peng! 👋

**Electrical & Computer Engineering Student @ USC** *Building at the intersection of Embedded Systems, Robotics, and AI.*

I am an engineering student and researcher passionate about integrating hardware with intelligent software. From building self-assembling robots to developing RAG pipelines for LLMs, I love solving complex problems that bridge the physical and digital worlds.

---

## 🛠️ Tech Stack

**Languages** ![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?style=flat&logo=c%2B%2B&logoColor=white)
![C](https://img.shields.io/badge/C-00599C?style=flat&logo=c&logoColor=white)
![MATLAB](https://img.shields.io/badge/MATLAB-e16737?style=flat&logo=mathworks&logoColor=white)

**Hardware & Embedded** ![Raspberry Pi](https://img.shields.io/badge/Raspberry%20Pi-A22846?style=flat&logo=raspberrypi&logoColor=white)
![Arduino](https://img.shields.io/badge/Arduino-00979D?style=flat&logo=arduino&logoColor=white)
![ESP32](https://img.shields.io/badge/ESP32-E7352C?style=flat&logo=espressif&logoColor=white)
![NVIDIA Jetson](https://img.shields.io/badge/NVIDIA%20Jetson-76B900?style=flat&logo=nvidia&logoColor=white)
![KiCad](https://img.shields.io/badge/KiCad-3145A0?style=flat&logo=kicad&logoColor=white)

**AI & Software** ![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=flat&logo=opencv&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat&logo=pytorch&logoColor=white)
![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=flat&logo=langchain&logoColor=white)


---

## 🔭 Experience & Research

### **Manycore Tech | Machine Learning Engineer Intern**
*Summer 2025*
* **RAG Pipeline Optimization:** Architected a knowledge-graph-augmented Retrieval-Augmented Generation (RAG) pipeline using **Alibaba Bailian** and **KuzuDB**.
    * Achieved a **40% increase in retrieval relevance** and reduced system latency by **20%** by optimizing graph queries and vector-database integration.
    * Engineered a unified retrieval strategy combining vector search, KG neighbor expansion, semantic filtering, and deduplication.
* **LangChain Agent Development:** Developed advanced agents capable of executing KG-driven contextual reasoning and **multi-hop retrieval**.
    * These agents enabled more accurate evidence assembly across graph nodes, significantly improving semantic search outputs for real-world workloads.
* **High-Performance Data Engineering:** Implemented a robust KnowledgeGraph module supporting fast CSV ingestion, schema construction, and efficient traversal operations to accelerate KuzuDB-based tasks.
    * Documented the full architecture and performance-tuning strategies for scalable deployment.

### **Robot Locomotion & Navigation Dynamics Lab (USC) | Researcher**
*August 2024 - Present*
* **Locomotion Algorithm Design:** Researching multi-legged robot locomotion with a focus on body-leg phase coordination.
    * Redesigned phase-control algorithms by converting degree-based coordination into **normalized phase offsets**.
    * This improved gait consistency, interpretability, and cross-condition comparability for downstream analysis.
* **Experimental Validation:** Executed **46 physical trials** using **OptiTrack** IR-marker 3D kinematics to characterize performance across various coordination regimes.
* **Hardware & Mechanical Iteration:** Improved mechanical system reliability by refining servo-mount clearances, gear spacing, and cable routing.
    * Redesigned electronics enclosures to enhance durability and dust resistance for operation in cluttered/obstacle-heavy environments.

### **USC Makers | Team Leader (Autonomous Skateboard)**
*August 2025 - Present*
* **Leadership:** Leading a 6-member engineering team to build "SkateMo," an autonomous self-driving skateboard, owning the integration of perception, navigation, and embedded control.
* **Perception & Path Planning:** Building real-time obstacle avoidance logic using **OpenCV** and **YOLO** with camera/IMU sensor fusion.
    * Designed Finite State Machine (FSM) based path-planning to handle skateboard-like steering dynamics.
* **Embedded Control:** Developing **BLDC motor-control firmware** to handle speed regulation, current limiting, and direction control.

---

## 🚀 Featured Projects

### 🛹 SkateMo: Autonomous Self-Driving Skateboard (Current)
*Project Manager | USC Makers*
Currently leading a team to build a self-driving skateboard.
* **Tech:** OpenCV, YOLO, IMU Sensor Fusion, BLDC Motor Control.
* **Role:** Designing path-planning logic (FSM-based) and implementing embedded control firmware.

### 👓 Vyz: AI-Enabled Sensory Adaptation Headset
*🏆 Winner - Best Hardware Project (LA TechWeek Good Vibes Only Hackathon)*

<p float="left">
<img src="https://github.com/RakshetaK/GVO-Repo/blob/main/Images/vyz-physical-wearable.JPG" width="250">
<img src="https://github.com/RakshetaK/GVO-Repo/blob/main/Images/vyz-compute-box.JPG" width="250">
</p>

A sensory regulation headset designed to detect and mitigate visual and auditory overstimulation for neurodivergent individuals.

* **Hardware:** NVIDIA Jetson Orin Nano, Servo-controlled Visor, RGB LEDs.
* **Software:** Python (Multithreading), OpenCV (Brightness tracking), SciPy (Audio filtering), Flask API.
* **Function:** Automatically adjusts visor tint and noise cancellation based on real-time environmental analysis.

<br clear="right"/>

### 🤖 Self-Assembling Modular Robot System
*Independent Research*

A fully automatic modular robot system where individual units can locate, attach, and reconfigure themselves to complete tasks.

* **Mechanism:** 4-DoF modules with electromagnetic connection interfaces.
* **Control:** ESP32 Microcontrollers, PID control for precise movement.
* **Swarm Logic:** Uses computer vision (AprilTags) for localization and assembly.

<img src="https://github.com/john02px/modular-robot/blob/main/modular-robot/Project%20Photos/Multi%20Module.JPG?raw=true" width="500">
Project Demo Video:

[![Modular Robot Demo](http://img.youtube.com/vi/8HDp2pXij3Y/0.jpg)](http://www.youtube.com/watch?v=8HDp2pXij3Y "Modular Robot Demo")

### 🏠 IoT Smart Room Control System
*EE250 Final Project*

<img src="https://raw.githubusercontent.com/NamithGang/EE250FinalProject/refs/heads/main/overall_diagram.png" width="800">

An automated environment management solution utilizing a distributed "Master-Slave" architecture.

* **Stack:** Raspberry Pi 4 (Master/Vision), Arduino Uno (Slave/Actuation).
* **Features:** YOLOv3-Tiny for human detection, web dashboard for control, and UART communication protocol.
* **Repo:** [Link to Project](https://github.com/NamithGang/EE250FinalProject)

### 🥋 Karate Kid: Interactive Training Wearable
*Wireless Systems Lead | USC Makers*
A wireless motion-tracking wearable providing real-time haptic feedback for martial arts training.
* **Tech:** ESP32, MPU6050 (6-DoF IMU), Unity Game Engine.
* **Role:** Designed custom PCB and implemented low-latency wireless communication (UDP/TCP).

### 🖨️ Camshaft-Powered Braille Embosser
*Independent Research*

<img src="https://raw.githubusercontent.com/john02px/braille-embosser/main/Project%20Images%20and%20Diagrams/Machine%20Picture%20(with%20banana%20for%20scale).jpg" width="400">

A low-cost, quiet alternative to commercial braille embossers using a novel camshaft design.
* **Cost:** ~$160 USD (vs. $2000+ commercial options).
* **Performance:** <60dB noise level with consistent dot height tolerance (±0.12mm).

---

## 📫 Connect with Me

* [LinkedIn](https://www.linkedin.com/in/yc-john-peng/)
