# Unit 4 - Advances in Robotics

## 5C level architecture for CPS (Cyber Physical Systems)

### Smart connection

- acquiring accurate and reliable data from machines and their components
- data can be obtained from:
  - ERP(Enterprice Resource Planning)
  - MES(Manufacturing Execution System)
  - SCM(Supply chain management),
  - CMM (Capabilty Management)

### Data to information conversion

- obtaining meaningful information from the obtained data
- brings self awareness to machines

### Cyber Level

- robot compares itself with other machines / data
- central information hub
- better insights

### cognition level

- generates a deep knowledge of monitored systems
- correct decision to be taken

### Configuration

- feedback from the cyber space to physical space
- makes machine self configure and self adaptive

## Layers of Internet of Robotic Things

- advanced tech that combines IoT and robotic systems
- autonomous robots
- enables robots to communicate with each other
- IoRT has three main layers

### Physical layer

- forms the hardware foundation
- robots , sensors, actuators
- senses environment, collects data, performs physical actions

### Network and Control layer

- connects and manages all physical devices
- communicated between robots and devices
- data transmission
- communication protocols used:
  - short range: wifi, bluetooth
  - long range - LoRaWAN, Sigfox
  - IoT-specific - RPL
- TLS encryption, auth, frequency hopping

### Service and Application Layer

- provides services directly to end users
- responsible for monitoring, data processing, control, decision making
- Protocols: XMPP, REST, HTTP
- Cloud Robotics, machine learning, object detection, reinforcement learning

## Robotics Evolution

### Ancient Period

- mythological robots
- imagined mechanical servants and automated machines

### 1920

- birth of the term "ROBOT"
- Karel Capek
- imagined as artificial workers designed to serve humans

### 1950

- rise of industrial robotics
- Unimate → first industral robotic arms
- performed dangerous, repetitive tasks

### 1970

- microprocessor revolusion

### 21st century

- AI and autonomous robotics
- integration of AI and ML

### Modern Robotics Era

- use LiDAR, computer vision, AI , cloud computing, IoT

```
Mythology
   ↓
1920 → Term "Robot" introduced by Karel Čapek
   ↓
1950s → Unimate: First industrial robot
   ↓
1970s → Microprocessor revolution
   ↓
2000s → AI and autonomous robots
   ↓
Present → IoT, Cloud Robotics and IoRT
```

## Robotic Applications

1. Manufacturing, Industrial Automation
2. Logistic and Warehousing
3. Healthcare and medical robots
4. Agriculture
5. Defense and military
6. Space exploration
7. Disaster Management
8. Service Robotics
9. Domestic Applications → floor cleaning, lawn moving, etc
10. Human robot interaction

## Components of Robots

- Hardware components and Software components

### Actuators and Motors

- responsible for movement and manipulation of robot
- electric motors, hydraulic actuators, servo motors, stepper motors

### Sensors and Vision Systems

- allow robots to perceive their environment
- provide information about surroundings
- proximity ultrasonic, infrared, gyroscope, cameras, etc
- **functions** object detection, distance measurement, navigation etc

### Power Supply and batteries

- provide energy needed for robots to operate
- Lithium ion batteries

### Structural Elements and Materials

- form the body and frame of the robot
- aluminum, steel, plastic, etc

### Robot Operating System (ROS)

- acts as the software platform of the robot
- communicates between components

### Programming Languages and Frameworks

- python, c++, matlab

### Algorithms and Data Processing

- enables robots to make decisions and perform tasks
- path planning, localization, object recognition, etc

### Control Algorithms

- ensure precise movement and stabilty
- speed and position control

### ALML

- adds intelligence and autonomy to robots
- deep learning, reinforcement learning, NLP

```
Robot Components
│
├── Hardware Components
│   ├── Actuators and Motors
│   ├── Sensors and Vision Systems
│   ├── Power Supply
│   └── Structural Elements
│
└── Software Components
    ├── Operating System (ROS)
    ├── Programming Languages
    ├── Algorithms
    ├── Control Algorithms
    └── AI and Machine Learning
```
