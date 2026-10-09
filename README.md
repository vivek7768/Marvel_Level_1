# Marvel Level 1
# 1. Introduction to Aerodynamics and Aircraft Structures

## Objective
To understand the basic principles of flight, aerodynamic forces, aircraft control surfaces, and essential flight instruments.

## Quadcopter Flight Mechanics

A quadcopter uses four fixed-pitch propellers. Instead of changing blade pitch like a helicopter, it changes motor RPM.

Typically, two motors rotate clockwise and two rotate counter-clockwise. Their reaction torques cancel each other during normal operation.

![image alt](https://github.com/vivek7768/Marvel_Level_1_IMGS/blob/c52237b39abd1faeaf7932eadb6b12b9eea27f3b/Drone.png)

Basic Motor Arrangement

CW → Motor 1, Motor 4

CCW → Motor 2, Motor 3

This arrangement provides torque balance and allows controlled yaw.

### Basic Control Movements (Pitch, Roll, Yaw)

All directional movements are controlled by varying the differential speed (RPM) between specific pairs of motors:

#### 1. Pitch (Nose Up / Down)
Pitch tilts the aircraft forward or backward along its lateral axis.

* **Pitch Forward (Nose Down):** Speed up the rear motors and slow down the front motors. The extra lift generated at the rear tilts the nose downward, directing thrust backward to propel the drone forward.
* **Pitch Backward (Nose Up):** Speed up the front motors and slow down the rear motors.

#### 2. Roll (Side-to-Side Tilt)
Roll tilts the aircraft left or right along its longitudinal axis.

* **Roll Left:** Speed up the right-side motors and slow down the left-side motors. The higher thrust on the right pushes the left side down, causing lateral movement to the left.
* **Roll Right:** Speed up the left-side motors and slow down the right-side motors.

#### 3. Yaw (Rotation around Vertical Axis)
Yaw rotates the drone clockwise or counter-clockwise without changing altitude or position. It relies on **torque imbalance** rather than differential lift.

* **Yaw Clockwise:** Speed up the two counter-clockwise (CCW) motors and slow down the two clockwise (CW) motors. The increased reaction torque from the CCW motors pushes the frame in the opposite (clockwise) direction.
* **Yaw Counter-Clockwise:** Speed up the two clockwise (CW) motors and slow down the two counter-clockwise (CCW) motors.

## FPV Drone Core Hardware Components

| Component | Primary Function |
| :--- | :--- |
| **Flight Controller (FC)** | The "brain" running stabilization algorithms and processing sensor inputs. |
| **Radio Transmitter (TX)** | Handheld controller operated by the pilot to send flight commands. |
| **Receiver (RX)** | Onboard module that intercepts wireless commands from the TX. |
| **Electronic Speed Controller (ESC)** | Regulates high current from the battery to dynamically control motor RPM. |
| **GPS Module** | Provides satellite positioning for coordinates and Return-to-Home safety. |
| **FPV Camera** | Captures the real-time first-person optical video feed. |
| **Video Transmitter (VTX)** | Broadcasts the live video signal wirelessly back to the ground station. |
| **VRX (Video Receiver)** | Captures the VTX video transmission inside the pilot's goggles or monitor. |
| **Battery (LiPo)** | High-discharge power source supplying energy to the motors and electronics. |

## Drone Sensors
### 1. Gyroscope (Measuring Angular Velocity)

#### Working Principle
The gyroscope measures **angular velocity** (the rate of rotation around an axis, expressed in degrees per second or rad/s) across the three rotational axes: Roll, Pitch, and Yaw. 
* **MEMS Design:** Inside the sensor, microscopic silicon structures (often shaped like tuning forks or ring structures) are driven into continuous, high-frequency electrostatic oscillation.
* **The Coriolis Effect:** When the drone is rotated (e.g., pitched or rolled by wind), a secondary inertial force known as the **Coriolis force** acts perpendicularly to the direction of motion and the vibration. 
* **Detection:** This force causes the vibrating elements to deflect slightly. Capacitive electrodes pick up this physical displacement, converting it into an electrical voltage proportional to the angular speed.

### 2. Accelerometer (Measuring Linear Acceleration & Tilt)

#### Working Principle
The accelerometer measures **linear acceleration** along the X, Y, and Z axes, including the constant static acceleration pull of **Earth's gravity** ($1g \approx 9.81 \, \text{m/s}^2$).
* **MEMS Design:** It consists of a microscopic proof mass attached to flexible micro-springs suspended between fixed capacitor plates. 
* **Deflection & Capacitance:** When the drone accelerates linearly (speeds up, slows down, or moves vertically) or tilts, inertia shifts the microscopic proof mass. This movement changes the distance between the capacitor plates, altering electrical capacitance.


### 3. Magnetometer (Measuring Magnetic Heading)

#### Working Principle
The magnetometer acts as a solid-state digital compass, measuring the strength and direction of the **Earth's magnetic field** relative to the drone's body frame.
* **Sensing Technology:** Most drone magnetometers utilize **Anisotropic Magnetoresistance (AMR)** or Hall-effect sensors. These materials change their electrical resistance when exposed to external magnetic fields, allowing the sensor to resolve multi-axis vector components of ambient magnetism.

## 1.1 Basic Principles of Flight

### Four Aerodynamic Forces
- **Lift (L):** Force acting perpendicular to the airflow, supporting the aircraft.
- **Weight (W):** Gravitational force acting downward.
- **Thrust (T):** Force produced by an engine/propeller to move the aircraft forward.
- **Drag (D):** Aerodynamic resistance opposing motion.

### Bernoulli's Principle
An increase in airflow velocity is associated with a decrease in static pressure. This pressure difference contributes to lift generation over an airfoil.

### Newton's Third Law
An aircraft or propeller generates lift/thrust by accelerating air downward or backward. The air produces an equal and opposite reaction force on the aircraft.

## 1.2 Lift Equation

![image alt](https://github.com/vivek7768/Marvel_Level_1_IMGS/blob/c52237b39abd1faeaf7932eadb6b12b9eea27f3b/Lift_Force.png)

Where:
- \(L\) = Lift (N)
- \(\rho\) = Air density (kg/m³)
- \(V\) = Air velocity (m/s)
- \(S\) = Wing area (m²)
- \(C_L\) = Coefficient of lift

Lift increases with air density, wing area, velocity², and coefficient of lift.

## 1.3 Stability and Control

Aircraft stability is the ability to return toward its original flight condition after a disturbance.

![image alt](https://github.com/vivek7768/Marvel_Level_1_IMGS/blob/c819c0da2e4cb8562f5f6f6bc2b0d8ae479ee9fd/Control_Surfaces.png)

### Primary Control Surfaces
| Surface | Controls |
|---|---|
| Aileron | Roll |
| Elevator | Pitch |
| Rudder | Yaw |

### Secondary Control Surfaces
- **Flaps:** Increase lift and drag during take-off/landing.
- **Slats:** Improve lift and delay stall at high angles of attack.
- **Spoilers/Airbrakes:** Increase drag and/or reduce lift for deceleration and descent.
- **Trim Tabs:** Reduce the control force required from the pilot.

## 1.4 Pitot Tube

A **Pitot tube** measures the aircraft's total (stagnation) pressure. When combined with static pressure, the pressure difference is used to determine **airspeed**.

![image alt](https://github.com/vivek7768/Marvel_Level_1_IMGS/blob/c819c0da2e4cb8562f5f6f6bc2b0d8ae479ee9fd/Pitot_Tube.png)

\[
q = P_t-P_s=\frac{1}{2}\rho V^2
\]

where \(P_t\) is total pressure and \(P_s\) is static pressure.

## 1.5 Radio Altimeter

A **radio altimeter** measures the aircraft's height above the ground (**AGL**) using radio waves.

Basic operation:
1. Transmit a radio signal toward the ground.
2. Receive the reflected signal.
3. Determine the signal's travel time.
4. Calculate height above the surface.

\[
h=\frac{ct}{2}
\]

where \(c\) is the speed of light and \(t\) is the round-trip travel time.

## 1.6 Basic Flight Concept

Aircraft and drones maintain controlled flight by balancing aerodynamic forces and continuously adjusting their attitude and control surfaces.

**Overall concept:**

`Thrust → Motion → Airflow → Aerodynamic Forces → Stability & Control → Controlled Flight`

---

# 2. Understanding and Designing an Airfoil

## Objective
To understand airfoil fundamentals and nomenclature, model a NACA 4412 airfoil in Fusion 360, and analyze its lift and drag using Autodesk CFD.

## 2.1 Airfoil Fundamentals

An **airfoil** is a streamlined shape designed to produce lift when air flows around it.

### Important Terms
- **Leading Edge:** Front of the airfoil.
- **Trailing Edge:** Rear point of the airfoil.
- **Chord Line:** Straight line joining the leading and trailing edges.
- **Chord Length:** Distance between the leading and trailing edges.
- **Camber Line:** Mean curve between the upper and lower surfaces.
- **Maximum Camber:** Maximum distance of the camber line from the chord.
- **Thickness:** Maximum distance between the upper and lower surfaces.
- **Angle of Attack (AoA):** Angle between the chord line and relative airflow.

## 2.2 NACA Airfoil Nomenclature

NACA airfoils are classified using different numbering systems.

### 1. NACA 4-Digit Series

Example: **NACA 4412**

- **1st digit:** Maximum camber as % of chord → 4%
- **2nd digit:** Location of maximum camber in tenths of chord → 40%
- **Last 2 digits:** Maximum thickness as % of chord → 12%

Therefore, NACA 4412 has:
- 4% maximum camber
- Maximum camber at 40% chord
- 12% maximum thickness

### 2. NACA 5-Digit Series

Example: **NACA 23012**

The 5-digit series provides more control over the **design lift coefficient and camber-line shape**.

- First digit → Related to design lift coefficient
- Second and third digits → Position/shape of maximum camber
- Last two digits → Maximum thickness as % of chord

The 5-digit series is mainly used when a specific **design lift characteristic** is required.

### 3. NACA 6-Series

Example: **NACA 63-412**

The 6-series was developed primarily for **high aerodynamic efficiency and low drag**.

Its nomenclature describes:
- Pressure-distribution characteristics
- Location of minimum pressure
- Design lift condition
- Maximum thickness

These airfoils are commonly associated with **laminar-flow airfoil design**.

## 2.3 Turbulence

**Turbulence** is an irregular flow containing fluctuating velocities and eddies. It can increase drag and cause flow separation.

The **Reynolds number** is used to characterize the flow:

\[
Re=\frac{\rho VL}{\mu}
\]

where:
- \(\rho\) = Air density
- \(V\) = Flow velocity
- \(L\) = Characteristic length
- \(\mu\) = Dynamic viscosity


### Design Parameters
* **Airfoil Profile:** NACA 4412[cite: 1, 2]
* **Solid Material:** Aluminum (`1 Part1.Body1`)[cite: 1, 2]
* **Geometry Units:** Centimeters (cm)[cite: 1, 2]


## 2.4 Autodesk CFD Analysis

The airfoil is placed inside an external airflow domain.

### CFD Setup
* **CFD Software:** Autodesk CFD 2027[cite: 1, 2]
* **Fluid Domain Material:** Air (`2 CFDCreatedVolume`)[cite: 1, 2]
* **Mesh Type:** Automatic Mesh Sizing (`Mesh Size (auto)`)[cite: 1, 2]
* **Solver Iterations:** 100 iterations[cite: 1, 2]
* **Primary Result Field:** Velocity Magnitude (cm/s)[cite: 2]

![image alt](https://github.com/vivek7768/Marvel_Level_1_IMGS/blob/c819c0da2e4cb8562f5f6f6bc2b0d8ae479ee9fd/CFD_1.png)

### Results
* **Max Velocity Magnitude:** 3197.29 cm/s[cite: 2]
* **Total Wetted Area:** 357.483 cm²[cite: 1]
* **Total Force (FX):** 1.60029 N[cite: 1]
* **Total Force (FY):** -0.00120279 N[cite: 1]
* **Total Force (FZ):** -5.32802 N[cite: 1]

![image alt](https://github.com/vivek7768/Marvel_Level_1_IMGS/blob/c819c0da2e4cb8562f5f6f6bc2b0d8ae479ee9fd/CFD_2.png)

## 2.5 Conclusion

A **NACA 4412 airfoil** with 100 mm chord and 160 mm span and AOA:15° was modeled in Fusion 360 and analyzed in Autodesk CFD at 25 m/s. The lift and drag obtained for composite and wood-based configurations were compared, with the final design selected based on achieving the required **minimum 5 N lift** and suitable structural properties.


# 5. Understand About ESC

## Objective

- To understand the working principle of an Electronic Speed Controller (ESC).
- To understand how an ESC is used to control the speed of a BLDC motor.
- To study the role of Arduino UNO and a potentiometer in BLDC motor speed control.


### Electronic Speed Controller (ESC)

An **Electronic Speed Controller (ESC)** is an electronic device used to control the speed and direction of a Brushless DC (BLDC) motor. Since a BLDC motor does not have mechanical brushes and a commutator, electronic switching is required to energize its three-phase windings in the correct sequence. The ESC performs this electronic commutation.

The ESC receives DC power from a battery and converts it into controlled three-phase electrical signals for the BLDC motor. It also receives a low-power control signal from a microcontroller such as an Arduino UNO.

### BLDC Motor

A **Brushless DC motor** consists mainly of a permanent-magnet rotor and multiple stator windings. The rotor rotates because of the interaction between the magnetic field produced by the stator and the permanent magnets of the rotor.

Unlike a brushed DC motor, the BLDC motor requires an electronic controller to switch the stator windings. The ESC performs this function and controls the motor speed by regulating the power supplied to the motor.

### ESC Control Signal

An Arduino typically controls an ESC using a **servo-type PWM control signal**. A common ESC control signal has a frequency of approximately **50 Hz**, corresponding to a period of 20 ms.

The throttle information is represented by the pulse width:

- **1000 µs:** Minimum throttle
- **1500 µs:** Approximately mid throttle
- **2000 µs:** Maximum throttle

The ESC interprets the pulse width and adjusts the power supplied to the BLDC motor accordingly.

### Potentiometer as Throttle Control

A potentiometer can be used as a variable throttle input. When the potentiometer is rotated, its output voltage changes. The Arduino reads this voltage using its analog-to-digital converter (ADC), which provides a value from **0 to 1023**.

This value is mapped to the required ESC throttle range. Therefore, rotating the potentiometer changes the control signal sent to the ESC, resulting in a corresponding change in BLDC motor speed.

### Working Principle

The overall working process can be represented as:

Potentiometer  
↓  
Arduino ADC  
↓  
Throttle Signal  
↓  
ESC  
↓  
Electronic Commutation  
↓  
BLDC Motor  
↓  
Variable Speed

The ESC therefore acts as the interface between the Arduino's low-power control signal and the high-current BLDC motor.

## Task Simulation


## Applications

ESC-controlled BLDC motors are widely used in:

- Drones and multirotors
- RC cars and aircraft
- Robotics
- Electric vehicles
- Cooling fans
- Industrial automation
- Other variable-speed motor applications

## Result

The experiment provides an understanding of how an ESC electronically controls a BLDC motor and how an Arduino with a potentiometer can be used to vary its speed.


# 6. Basics of PID

## Objective

- To understand PID tuning for stability in UAVs.
- To understand the working of GPS Hold and Altitude Hold.
- To compare GPS Hold and Altitude Hold.

## 1. Introduction to PID Control

PID stands for **Proportional, Integral and Derivative**. It is a feedback control technique widely used in UAVs to maintain stable flight and control parameters such as roll, pitch, yaw, altitude and position.

A PID controller continuously compares the **desired value (setpoint)** with the **actual measured value** and calculates the error.

\[
Error = Setpoint - Actual\ Value
\]

The PID controller then uses this error to generate a correction signal for the motors.

The basic PID equation is:

\[
Output = K_p e + K_i\int e\,dt + K_d\frac{de}{dt}
\]

where:

- `Kp` = Proportional gain
- `Ki` = Integral gain
- `Kd` = Derivative gain
- `e` = Error

---

## 2. Proportional (P) Control

The **Proportional term** responds to the present error. A larger error produces a larger correction.

For example, if a UAV tilts away from its desired level position, the P controller increases the motor correction to bring it back.

![image alt](https://github.com/vivek7768/Marvel_Level_1_IMGS/blob/eda49c5f32d783ffd5a4dfe8a3dc8816031e1971/P_Controller.jpg)

### Effect of Increasing P

- Faster response
- Stronger correction
- Reduces error
- Excessive P can cause oscillations

---

## 3. Integral (I) Control

The **Integral term** responds to the accumulated error over time. It helps eliminate small errors that remain after proportional correction.

For example, if wind continuously pushes the UAV slightly to one side, the integral term gradually increases the correction to remove the remaining error.

![image alt](https://github.com/vivek7768/Marvel_Level_1_IMGS/blob/eda49c5f32d783ffd5a4dfe8a3dc8816031e1971/I_Controller.jpg)

### Effect of Increasing I

- Removes steady-state error
- Improves long-term accuracy
- Excessive I can cause overshoot and oscillations


## 4. Derivative (D) Control

The **Derivative term** responds to how quickly the error is changing. It acts as a damping term and helps prevent sudden overshoot and oscillations.

For example, if the UAV is moving rapidly toward its desired angle, the D term reduces the correction before it overshoots.

![image alt](https://github.com/vivek7768/Marvel_Level_1_IMGS/blob/eda49c5f32d783ffd5a4dfe8a3dc8816031e1971/D_Controller.jpg)

### Effect of Increasing D

- Reduces overshoot
- Dampens oscillations
- Improves stability
- Excessive D can make the system sluggish and sensitive to sensor noise

---

## 5. PID Control in UAVs

PID controllers are commonly used in different UAV control loops:

- **Roll control** – maintains lateral attitude
- **Pitch control** – maintains forward/backward attitude
- **Yaw control** – controls heading
- **Altitude control** – maintains desired height
- **Position control** – maintains horizontal position

When wind or another disturbance causes the UAV to tilt, sensors detect the change. The flight controller calculates the error and changes individual motor speeds to restore the desired attitude.


## 6. PID Tuning for UAV Stability

![image alt](https://github.com/vivek7768/Marvel_Level_1_IMGS/blob/eda49c5f32d783ffd5a4dfe8a3dc8816031e1971/PID.jpg)

PID tuning involves selecting suitable `Kp`, `Ki` and `Kd` values to achieve a stable and responsive UAV.

A basic tuning procedure is:

1. Start with a low **P** value.
2. Gradually increase P until the UAV responds quickly and begins to show slight oscillation.
3. Reduce P slightly to obtain stable operation.
4. Increase **D** to reduce oscillations and improve damping.
5. Gradually increase **I** to eliminate persistent drift or steady-state error.
6. Perform repeated flight tests and fine-tune the values.

The objective is to achieve a balance between **response speed, stability and accuracy**.

---

## 7. GPS Hold

**GPS Hold**, also known as **Position Hold** or **Loiter** on some flight controllers, is a flight mode used to maintain the UAV at a fixed horizontal location.

The flight controller uses GPS/GNSS information to determine the UAV's position. If the UAV moves away from the desired position due to wind or another disturbance, the controller commands roll and pitch corrections to bring it back.

GPS Hold primarily controls the UAV's horizontal position. Altitude is generally controlled separately using an altitude-control system such as a barometer.

---

## 8. Altitude Hold

**Altitude Hold** is a flight mode that automatically maintains the UAV at a selected height.

The flight controller continuously measures the altitude and adjusts the motor throttle to compensate for changes.

A barometer is commonly used for altitude estimation, while rangefinders such as LiDAR or sonar can provide additional altitude information at low heights.

Altitude Hold primarily controls the **vertical Z-axis**. The UAV can still drift horizontally because its X-Y position is not automatically maintained.

---

## 9. GPS Hold vs Altitude Hold

| Parameter | GPS Hold | Altitude Hold |
|---|---|---|
| Main purpose | Maintains horizontal position | Maintains altitude |
| Controlled axis | X-Y position | Z-axis |
| Primary sensor | GPS/GNSS | Barometer / Rangefinder |
| Horizontal drift | Automatically corrected | Not automatically corrected |
| Altitude | Usually maintained with altitude control | Directly maintained |
| GPS requirement | Required for GPS-based position hold | Not necessarily required |
| Wind compensation | Corrects horizontal movement caused by wind | Mainly compensates for vertical disturbances |
| Complexity | More complex | Simpler |
| Main control action | Roll/Pitch correction | Throttle correction |
| Typical use | Hovering at a fixed location | Maintaining constant height |

---

# 8. Different Flight Modes in Mission Planner

## Objective

To understand the various flight modes available in Mission Planner and their specific applications.

## Introduction

Mission Planner is a Ground Control Station (GCS) used with ArduPilot-based UAVs. It allows the user to configure, monitor and control the vehicle and select different flight modes according to the required operation.

Flight modes determine how much control is given to the pilot and how much control is handled automatically by the flight controller. ArduPilot Copter provides modes ranging from fully manual stabilization to completely autonomous navigation. :contentReference[oaicite:0]{index=0}

---

## 1. Stabilize

Stabilize is a basic manual flight mode in which the pilot controls the throttle, yaw, roll and pitch. The flight controller automatically self-levels the roll and pitch axes when the sticks are released.

It is useful for:
- Basic manual flying
- Learning UAV control
- Testing the aircraft after setup

It does not automatically maintain the UAV's position, so wind can cause the vehicle to drift. :contentReference[oaicite:1]{index=1}

---

## 2. ACRO

ACRO mode is an advanced manual flight mode intended for experienced pilots. Unlike Stabilize, it does not automatically return the UAV to a level attitude.

The pilot controls the angular rate of the aircraft, allowing continuous rolls and flips.

It is mainly used for:
- Aerobatic flying
- FPV flying
- Advanced pilot training

---

## 3. Altitude Hold

Altitude Hold automatically maintains the UAV's altitude while allowing the pilot to control roll, pitch and yaw.

The flight controller primarily uses a barometer to estimate altitude and automatically adjusts the throttle to maintain the desired height.

It is useful when:
- A constant height is required
- Manual horizontal movement is desired
- GPS is unavailable

The UAV can still drift horizontally because its position is not automatically held. :contentReference[oaicite:2]{index=2}

---

## 4. Auto

Auto mode allows the UAV to execute a pre-programmed mission stored in the flight controller.

A mission can contain:
- Takeoff commands
- Waypoints
- Camera commands
- Loiter commands
- Landing commands
- Other navigation commands

The UAV automatically navigates between waypoints using its position and altitude controllers.

It is mainly used for:
- Autonomous missions
- Mapping
- Surveying
- Repeated flight paths

Auto mode combines altitude control similar to AltHold and position control similar to Loiter. :contentReference[oaicite:3]{index=3}

---

## 5. Guided

Guided mode allows the pilot or a Ground Control Station to command the UAV to fly to a selected location.

In Mission Planner, the operator can select a location on the map and command the UAV to move there. After reaching the target, the UAV normally holds that location.

It is useful for:
- Interactive waypoint navigation
- Testing navigation
- Sending the UAV to a specific location
- Companion-computer control

Guided mode can also be controlled by scripts or companion computers. :contentReference[oaicite:4]{index=4}

---

## 6. Loiter

Loiter automatically maintains the UAV's current position, altitude and heading.

The pilot can still move the UAV using the control sticks. When the sticks are released, the UAV slows down and attempts to return to and hold its previous position.

It is useful for:
- Stable hovering
- Manual flying with position assistance
- Taking photographs
- Training new pilots

A reliable GPS signal, compass and low vibration are important for good Loiter performance. :contentReference[oaicite:5]{index=5}

---

## 7. Return to Launch (RTL)

RTL stands for **Return to Launch**.

When RTL is activated, the UAV automatically returns to its home position, which is normally the location where it was armed.

Depending on the configured parameters, the UAV:
1. Climbs to an appropriate return altitude.
2. Travels toward the home position.
3. Hovers above the home position.
4. Descends and lands if configured to do so.

RTL is mainly used as a safety feature when:
- The pilot loses control
- The battery is low
- The communication link is lost
- The mission needs to be aborted

A reliable position estimate, normally from GPS, is required. :contentReference[oaicite:6]{index=6}

---

## 8. Circle

Circle mode causes the UAV to fly in a circular path around a specified point.

The UAV maintains a fixed distance from the centre while continuously moving around it.

It can be useful for:
- Surveillance
- Aerial photography
- Inspecting a fixed object
- Demonstrating autonomous navigation

Circle mode requires a valid position estimate. :contentReference[oaicite:7]{index=7}

---

## 9. Land

Land mode automatically brings the UAV down and attempts to land it.

The flight controller controls the descent while maintaining horizontal position as appropriate.

It is useful for:
- Automated landing
- Emergency landing
- Completing autonomous missions

The UAV gradually reduces its altitude until it reaches the ground and detects that it has landed. :contentReference[oaicite:8]{index=8}

---

## 10. Drift

Drift mode provides a more aircraft-like manual flying experience.

It is similar to Stabilize but coordinates yaw and roll so that the UAV can be flown using coordinated turns.

It is useful for:
- Manual flying
- Smooth turns
- Learning coordinated UAV control

Drift uses position information but still provides significant manual control to the pilot. :contentReference[oaicite:9]{index=9}

---

## 11. PosHold

PosHold stands for **Position Hold**.

It is similar to Loiter because it automatically maintains the UAV's position and altitude. However, the pilot has more direct control over roll and pitch.

When the sticks are moved, the UAV responds manually. When they are released, the flight controller attempts to stop the UAV and hold its position.

It is useful for:
- Manual flying with GPS assistance
- Smooth position holding
- Situations where more manual control than Loiter is preferred. :contentReference[oaicite:10]{index=10}

---

## 12. Guided_NoGPS

Guided_NoGPS is a variation of Guided mode that does not require GPS.

It accepts attitude targets and altitude-related commands but does not accept normal position or velocity targets.

It is mainly intended for companion computers and specialized applications rather than normal manual flying.

It should not be confused with a complete GPS-free position-hold mode. :contentReference[oaicite:11]{index=11}

---

## 13. Smart RTL

Smart RTL is an enhanced form of Return to Launch.

Instead of simply flying directly back to the home location, the UAV records its recent flight path and attempts to retrace that path when returning.

This can be useful when:
- The direct path to home may contain obstacles
- The UAV has flown through a narrow route
- Retracing the previous path is safer

Smart RTL requires a valid position estimate and sufficient stored path information. :contentReference[oaicite:12]{index=12}

---

## 14. Follow Mode

Follow mode allows the UAV to automatically follow another vehicle or a ground station.

The UAV receives the target's position and continuously updates its own position to follow it.

It can be useful for:
- Following a person
- Vehicle tracking
- Filming moving subjects
- Autonomous convoy applications

Follow mode uses position information and is based on ArduPilot's guided/navigation capabilities. :contentReference[oaicite:13]{index=13}

---

## Flight Mode Comparison

| Flight Mode | Main Function | GPS/Position Required | Level of Automation |
|---|---|---|---|
| Stabilize | Manual flight with self-leveling | No | Low |
| ACRO | Manual rate control/aerobatics | No | Very Low |
| Altitude Hold | Maintains altitude | No | Medium |
| Auto | Executes programmed mission | Yes | High |
| Guided | Flies to commanded locations | Yes | High |
| Loiter | Holds position and altitude | Yes | High |
| RTL | Returns to home | Yes | High |
| Circle | Circles a specified point | Yes | High |
| Land | Automatic landing | Usually no position required | High |
| Drift | Manual coordinated flying | Yes | Low-Medium |
| PosHold | Position hold with manual override | Yes | Medium-High |
| Guided_NoGPS | Guided attitude/altitude control | No | Medium |
| Smart RTL | Returns by retracing path | Yes | High |
| Follow | Follows another vehicle/target | Yes | High |

---

# 9. DGCA Regulations


## Objective:
To understand the legal framework for operating drones in India.


## Task:
Study the Drone Rules 2021 released by the Government of India
Learn about BVLOS (Beyond Visual Line of Sight) regulations and how they impact flight planning, airspace management, and safety

![image alt](https://github.com/vivek7768/Marvel_Level_1_IMGS/blob/541cc14405ee70a9e719c5a3e60cb20b0256a67f/Restricitions.png)

![image alt](https://github.com/vivek7768/Marvel_Level_1_IMGS/blob/ecb12cc6ffd61846ca934b637632b7659112214f/Drone_Rules.jpg)

---



