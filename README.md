# AI Smart Traffic Control

An **IoT-based intelligent traffic control system** that uses computer vision to monitor traffic density and dynamically adjust traffic light timing.

This project is developed as a university IoT course project with the goal of exploring how **AI, IoT, and real-time traffic monitoring** can be combined to improve traffic flow at intersections.

> **Status:** In Development

---

## 📌 Project Overview

Traditional traffic lights usually operate using fixed timing cycles, which may be inefficient when traffic density changes throughout the day.

This project proposes a smart traffic control system capable of:

- Capturing traffic data from cameras or sensors.
- Detecting and counting vehicles in real time.
- Estimating traffic density for each direction.
- Dynamically adjusting traffic light duration.
- Sending traffic information through an IoT system.
- Monitoring the system through a dashboard.

The initial implementation focuses on a **single smart intersection**, with the architecture designed to allow future expansion to multiple intersections.

---

## 🎯 Objectives

The main objectives of the project are:

1. Detect vehicles from camera/video input.
2. Count vehicles in different traffic lanes.
3. Estimate traffic density.
4. Calculate appropriate traffic light timing.
5. Control a physical traffic-light prototype using an IoT device.
6. Monitor traffic conditions and traffic-light states in real time.
7. Design the system so that it can be extended to multiple intersections.

---

## 🏗️ Proposed System Architecture

```text
Camera / Video
      │
      ▼
Computer Vision
Vehicle Detection
      │
      ▼
Vehicle Counting
      │
      ▼
Traffic Density Analysis
      │
      ▼
Traffic Control Algorithm
      │
      ├──────────────► IoT Dashboard
      │
      ▼
Arduino / ESP32 / Raspberry Pi
      │
      ▼
Traffic Light Prototype
Red ─ Yellow ─ Green
```

---

## 🤖 AI & Computer Vision

The computer vision module is planned to detect common road vehicles such as:

- Cars
- Motorcycles
- Buses
- Trucks

A real-time object detection model such as **YOLO** can be used for vehicle detection.

Example:

```text
North Lane : 21 vehicles → High traffic
South Lane :  7 vehicles → Low traffic
East Lane  : 13 vehicles → Medium traffic
West Lane  :  5 vehicles → Low traffic
```

The detected traffic density will then be sent to the traffic control algorithm.

---

## 🚦 Adaptive Traffic Light Control

Instead of using only fixed traffic-light durations, the system will dynamically determine green-light time according to traffic conditions.

Example:

```text
High traffic density
→ Longer green-light duration

Low traffic density
→ Shorter green-light duration
```

The control algorithm must also consider safety constraints such as:

- Minimum green-light duration
- Maximum green-light duration
- Yellow-light transition time
- Avoiding conflicting green signals
- Fairness between traffic directions
- Preventing one lane from waiting indefinitely

---

## 🌐 IoT Integration

The IoT layer connects the traffic analysis system with the traffic-light controller and monitoring interface.

Possible communication architecture:

```text
AI Processing
     │
     ▼
MQTT / HTTP
     │
     ▼
IoT Controller
     │
     ├── Traffic Lights
     │
     └── Dashboard
```

The final communication protocol and hardware platform will be selected during implementation.

---

## 📊 Dashboard

The monitoring dashboard is planned to display:

- Number of detected vehicles
- Traffic density for each direction
- Current traffic-light state
- Remaining traffic-light time
- Current system status
- Historical traffic information

Example:

```text
Intersection Status

North
Vehicles: 24
Density : HIGH
Light   : GREEN
Time    : 35s

East
Vehicles: 8
Density : LOW
Light   : RED
```

---

## 🛠️ Planned Technologies

### AI / Computer Vision

- Python
- OpenCV
- YOLO

### IoT

One of the following platforms may be used:

- Arduino
- ESP32
- Raspberry Pi

### Communication

Possible protocols:

- MQTT
- HTTP / REST API

### Dashboard

The dashboard technology will be selected during development.

---

## 🔄 System Workflow

```text
1. Capture traffic video
        ↓
2. Detect vehicles
        ↓
3. Count vehicles
        ↓
4. Calculate traffic density
        ↓
5. Determine traffic-light timing
        ↓
6. Send command to IoT controller
        ↓
7. Control traffic-light prototype
        ↓
8. Update monitoring dashboard
        ↓
9. Repeat
```

---

## ✅ Expected Results

At the end of the project, the system is expected to demonstrate the following scenario:

```text
Camera captures traffic
        ↓
AI detects vehicles
        ↓
System counts vehicles
        ↓
Traffic density is calculated
        ↓
Green-light duration is adjusted
        ↓
IoT controller changes the traffic light
        ↓
Dashboard displays the updated information
```

A successful prototype should be able to demonstrate how traffic-light timing changes when the number of vehicles in each direction changes.

---

## 🔬 Research Questions

This project also focuses on answering the following questions:

### 1. Which algorithm can be used to detect and count vehicles from cameras in real time?

The project will investigate real-time computer vision approaches for vehicle detection and counting.

### 2. What factors should be considered when automatically adjusting traffic signals?

Factors may include:

- Traffic density
- Number of vehicles
- Waiting time
- Minimum/maximum green-light duration
- Intersection safety
- Traffic fairness

### 3. How can the system be scaled to multiple intersections across a city?

The project will explore a scalable architecture where multiple IoT traffic controllers communicate with a centralized or distributed monitoring system.

---

## 📈 Future Improvements

Possible future extensions include:

- Multiple-intersection coordination
- Emergency vehicle priority
- Pedestrian detection
- Vehicle tracking
- Traffic congestion prediction
- Historical traffic analytics
- Edge AI deployment
- Centralized smart-city traffic management

---

## 📁 Project Structure

The repository structure will evolve during development.

```text
ai-smart-traffic-control/
│
├── ai/
│   ├── detection/
│   ├── tracking/
│   └── traffic_analysis/
│
├── backend/
│
├── dashboard/
│
├── iot/
│   └── traffic_light_controller/
│
├── data/
│
├── docs/
│
├── tests/
│
└── README.md
```

---

## 👥 Team

This project is developed as part of the **IoT and Applications** course.

Team members and responsibilities will be updated as development progresses.

---

## 📝 Development Status

- [ ] System architecture
- [ ] Vehicle detection
- [ ] Vehicle counting
- [ ] Traffic density estimation
- [ ] Adaptive traffic-light algorithm
- [ ] IoT communication
- [ ] Traffic-light hardware prototype
- [ ] Monitoring dashboard
- [ ] System integration
- [ ] Testing and evaluation
- [ ] Final documentation

---

## 📄 License

This project is developed primarily for educational and research purposes.