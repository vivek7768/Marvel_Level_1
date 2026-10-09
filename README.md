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
### 1. Gyroscope 

#### Working Principle
The gyroscope measures **angular velocity** (the rate of rotation around an axis, expressed in degrees per second or rad/s) across the three rotational axes: Roll, Pitch, and Yaw. 
* **MEMS Design:** Inside the sensor, microscopic silicon structures (often shaped like tuning forks or ring structures) are driven into continuous, high-frequency electrostatic oscillation.
* **The Coriolis Effect:** When the drone is rotated (e.g., pitched or rolled by wind), a secondary inertial force known as the **Coriolis force** acts perpendicularly to the direction of motion and the vibration. 
* **Detection:** This force causes the vibrating elements to deflect slightly. Capacitive electrodes pick up this physical displacement, converting it into an electrical voltage proportional to the angular speed.

### 2. Accelerometer

#### Working Principle
The accelerometer measures **linear acceleration** along the X, Y, and Z axes, including the constant static acceleration pull of **Earth's gravity** ($1g \approx 9.81 \, \text{m/s}^2$).
* **MEMS Design:** It consists of a microscopic proof mass attached to flexible micro-springs suspended between fixed capacitor plates. 
* **Deflection & Capacitance:** When the drone accelerates linearly (speeds up, slows down, or moves vertically) or tilts, inertia shifts the microscopic proof mass. This movement changes the distance between the capacitor plates, altering electrical capacitance.

## 1.1 Basic Principles of Flight

### Four Aerodynamic Forces
- **Lift (L):** Force acting perpendicular to the airflow, supporting the aircraft.
- **Weight (W):** Gravitational force acting downward.
- **Thrust (T):** Force produced by an engine/propeller to move the aircraft forward.
- **Drag (D):** Aerodynamic resistance opposing motion.

## Bernoulli's Principle on an Airfoil

![image alt](https://github.com/vivek7768/Marvel_Level_1_IMGS/blob/9b73b38523b5a0d7274a36173849037189bb3a61/Bernoulli.png)

* **Streamline Division:** Incoming airflow splits at the leading edge into an upper path (blue) and a lower path (red)
* **Upper Path Dynamics:** The top path features high curvature and a longer distance, forcing air to move at high velocity, which creates a region of low pressure
* **Lower Path Dynamics:** The bottom path features lower curvature and a shorter distance, resulting in lower fluid velocity and higher static pressure
* **Bernoulli's Principle Core Rule:** According to Bernoulli's principle, an increase in fluid velocity occurs simultaneously with a decrease in static pressure
* **Lift Generation:** The resulting pressure differential—low pressure on top versus high pressure on the bottom—generates a net upward lifting force

### Newton's Third Law
An aircraft or propeller generates lift/thrust by accelerating air downward or backward. The air produces an equal and opposite reaction force on the aircraft.

## 1.2 Lift Equation

![image alt](https://github.com/vivek7768/Marvel_Level_1_IMGS/blob/9b73b38523b5a0d7274a36173849037189bb3a61/LIFT_EQ.png)

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

## Working of a Pitot Tube

![image alt](https://github.com/vivek7768/Marvel_Level_1_IMGS/blob/c819c0da2e4cb8562f5f6f6bc2b0d8ae479ee9fd/Pitot_Tube.png)

* **Primary Purpose:** A Pitot tube is an aerodynamic measurement instrument used to determine fluid flow velocity or aircraft airspeed
* **Total Pressure ($P_t$):** 
  * The central forward-facing opening points directly into the oncoming airflow
  * As air enters this tube, it is brought to a complete stop at a stagnation point, converting all kinetic energy into measurable stagnation pressure
* **Static Pressure ($P_s$):** 
  * Small ports located on the sides of the probe, perpendicular to the flow, measure the undisturbed ambient static pressure of the surrounding fluid
* **Pressure Transducer & Airspeed Calculation:** 
  * Both the total pressure ($P_t$) and static pressure ($P_s$) lines feed directly into a differential pressure transducer
  * The transducer measures the difference between these two values ($P_t - P_s$), which gives the dynamic pressure used to calculate the actual speed

## 1.5 Radio Altimeter

A **radio altimeter** measures the aircraft's height above the ground (**AGL**) using radio waves.

Basic operation:
1. Transmit a radio signal toward the ground.
2. Receive the reflected signal.
3. Determine the signal's travel time.
4. Calculate height above the surface.

### Advantages
* **True Terrain Clearance:** Measures exact height above the immediate ground, unlike barometric altimeters which depend on local pressure settings and measure height above sea level (MSL).
* **Low-Visibility Operations:** Crucial for precision approaches (such as ILS Category II and III landings) where knowing the exact distance to the runway threshold is vital.
* **Safety Systems Integration:** Provides essential altitude data to Ground Proximity Warning Systems (GPWS) to help prevent controlled flight into terrain (CFIT).

### Disadvantages
* **Limited Range:** Typically effective only at lower altitudes, usually restricted to the final 2,500 feet AGL.
* **Terrain Sensitivity:** Readings can fluctuate abruptly over uneven terrain, steep cliffs, or dense tree canopies because the radio wave reflects off the highest or closest obstacle below.

# 2. Understanding and Designing an Airfoil

## Objective
To understand airfoil fundamentals and nomenclature, model a NACA 4412 airfoil in Fusion 360, and analyze its lift and drag using Autodesk CFD.

## 2.1 Airfoil Fundamentals

An **airfoil** is a streamlined shape designed to produce lift when air flows around it.

![image alt](https://github.com/vivek7768/Marvel_Level_1_IMGS/blob/3b6f739936f2799225a83b694c86eeb313de1c57/Airfoil.png)

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

---

### 2. NACA 5-Digit Series

Example: **NACA 23012**

The 5-digit series provides more control over the **design lift coefficient and camber-line shape**.

- **1st digit (2):** Multiplied by $0.15$ to determine the design lift coefficient ($C_{li}$) $\rightarrow 2 \times 0.15 = 0.30$.
- **2nd digit (3):** Multiplied by $5\%$ to give the location of maximum camber from the leading edge $\rightarrow 3 \times 5\% = 15\%$ of the chord.
- **3rd digit (0):** Camber type indicator (`0` = standard normal camber, `1` = reflexed camber designed for zero pitching moment).
- **Last 2 digits (12):** Maximum thickness as % of chord $\rightarrow 12\%$.

---

### 3. NACA 6-Series

Example: **NACA 63-412** (frequently styled with a subscript as **NACA 63$_4$-412**)

The 6-series was developed primarily for **high aerodynamic efficiency and low drag**.

- **1st digit (6):** Series identifier designating the advanced laminar-flow airfoil family.
- **2nd digit (3):** Chordwise location of minimum pressure for Coriolis/basic symmetrical section in tenths of the chord $\rightarrow 30\%$ of the chord.
- **Subscript digit (4):** Range of lift coefficient in tenths above and below the design lift coefficient where favorable pressure gradients and low drag are maintained $\rightarrow \pm 0.4$ range.
- **Digit after the hyphen (4):** Design lift coefficient in tenths $\rightarrow 4 \times 0.1 = 0.4$.
- **Last 2 digits (12):** Maximum thickness as % of chord $\rightarrow 12\%$.
These airfoils are commonly associated with **laminar-flow airfoil design**.

## 2.3 Turbulence

**Turbulence** is an irregular flow containing fluctuating velocities and eddies. It can increase drag and cause flow separation.

The **Reynolds number** is used to characterize the flow:

$$Re = \frac{\rho VL}{\mu}$$

where:
- $\rho$ = Air density
- $V$ = Flow velocity
- $L$ = Characteristic length
- $\mu$ = Dynamic viscosity


### Design Parameters
* **Airfoil Profile:** NACA 4412
* **Solid Material:** Aluminum

## 2.4 Autodesk CFD Analysis

The airfoil is placed inside an external airflow domain.

### CFD Setup
* **CFD Software:** Autodesk CFD 2027
* **Fluid Domain Material:** Air
* **Mesh Type:** Automatic Mesh Sizing
* **Solver Iterations:** 100 iterations
* **Primary Result Field:** Velocity Magnitude (cm/s)

![image alt](https://github.com/vivek7768/Marvel_Level_1_IMGS/blob/c819c0da2e4cb8562f5f6f6bc2b0d8ae479ee9fd/CFD_1.png)

### Results
* **Max Velocity Magnitude:** 3197.29 cm/s
* **Total Wetted Area:** 357.483 cm²
* **Total Force (FX):** 1.60029 N
* **Total Force (FY):** -0.00120279 N
* **Total Force (FZ):** -5.32802 N

![image alt](https://github.com/vivek7768/Marvel_Level_1_IMGS/blob/c819c0da2e4cb8562f5f6f6bc2b0d8ae479ee9fd/CFD_2.png)

## 2.5 Conclusion

A **NACA 4412 airfoil** with 100 mm chord and 160 mm span and AOA:15° was modeled in Fusion 360 and analyzed in Autodesk CFD at 25 m/s. The lift and drag obtained for composite and wood-based configurations were compared, with the final design selected based on achieving the required **minimum 5 N lift** and suitable structural properties.

---

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

### Potentiometer as Throttle Control

A potentiometer can be used as a variable throttle input. When the potentiometer is rotated, its output voltage changes. The Arduino reads this voltage using its analog-to-digital converter (ADC), which provides a value from **0 to 1023**.

This value is mapped to the required ESC throttle range. Therefore, rotating the potentiometer changes the control signal sent to the ESC, resulting in a corresponding change in BLDC motor speed.

## Task Simulation

https://github.com/vivek7768/Marvel_Level_1_IMGS/blob/main/ESP.mp4

# 6. Basics of PID

## Objective

- To understand PID tuning for stability in UAVs.
- To understand the working of GPS Hold and Altitude Hold.
- To compare GPS Hold and Altitude Hold.

## 1. Introduction to PID Control

PID stands for **Proportional, Integral and Derivative**. It is a feedback control technique widely used in UAVs to maintain stable flight and control parameters such as roll, pitch, yaw, altitude and position.

A PID controller continuously compares the **desired value (setpoint)** with the **actual measured value** and calculates the error.

$$
Error = Setpoint - Actual\ Value
$$

The PID controller then uses this error to generate a correction signal for the motors.

The basic PID equation is:

$$
Output = K_p e + K_i \int e \, dt + K_d \frac{de}{dt}
$$

where:

- $K_p$ = Proportional gain
- $K_i$ = Integral gain
- $K_d$ = Derivative gain
- $e$ = Error

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

## 5. PID Tuning for UAV Stability

![image alt](https://github.com/vivek7768/Marvel_Level_1_IMGS/blob/eda49c5f32d783ffd5a4dfe8a3dc8816031e1971/PID.jpg)

A basic tuning procedure is:

1. Start with a low **P** value.
2. Gradually increase P until the UAV responds quickly and begins to show slight oscillation.
3. Reduce P slightly to obtain stable operation.
4. Increase **D** to reduce oscillations and improve damping.
5. Gradually increase **I** to eliminate persistent drift or steady-state error.
6. Perform repeated flight tests and fine-tune the values.

The objective is to achieve a balance between **response speed, stability and accuracy**.

## 6. GPS Hold

**GPS Hold**, also known as **Position Hold** or **Loiter** on some flight controllers, is a flight mode used to maintain the UAV at a fixed horizontal location.

The flight controller uses GPS/GNSS information to determine the UAV's position. If the UAV moves away from the desired position due to wind or another disturbance, the controller commands roll and pitch corrections to bring it back.

GPS Hold primarily controls the UAV's horizontal position. Altitude is generally controlled separately using an altitude-control system such as a barometer.

---

## 7. Altitude Hold

**Altitude Hold** is a flight mode that automatically maintains the UAV at a selected height.

The flight controller continuously measures the altitude and adjusts the motor throttle to compensate for changes.

A barometer is commonly used for altitude estimation, while rangefinders such as LiDAR or sonar can provide additional altitude information at low heights.

Altitude Hold primarily controls the **vertical Z-axis**. The UAV can still drift horizontally because its X-Y position is not automatically maintained.

---

## 8. GPS Hold vs Altitude Hold

| Parameter | GPS Hold | Altitude Hold |
|---|---|---|
| Main purpose | Maintains horizontal position | Maintains altitude |
| Controlled axis | X-Y position | Z-axis |
| Primary sensor | GPS/GNSS | Barometer / Rangefinder |
| Horizontal drift | Automatically corrected | Not automatically corrected |
| GPS requirement | Required for GPS-based position hold | Not necessarily required |
| Wind compensation | Corrects horizontal movement caused by wind | Mainly compensates for vertical disturbances |
| Main control action | Roll/Pitch correction | Throttle correction |
| Typical use | Hovering at a fixed location | Maintaining constant height |

---

# 8. Different Flight Modes in Mission Planner

## Objective

To understand the various flight modes available in Mission Planner and their specific applications.

## Introduction

Mission Planner is a Ground Control Station (GCS) used with ArduPilot-based UAVs. It allows the user to configure, monitor and control the vehicle and select different flight modes according to the required operation.

Flight modes determine how much control is given to the pilot and how much control is handled automatically by the flight controller. ArduPilot Copter provides modes ranging from fully manual stabilization to completely autonomous navigation.

---

## 1. Stabilize

Stabilize is a basic manual flight mode in which the pilot controls the throttle, yaw, roll and pitch. The flight controller automatically self-levels the roll and pitch axes when the sticks are released.

---

## 2. ACRO

ACRO mode is an advanced manual flight mode intended for experienced pilots. Unlike Stabilize, it does not automatically return the UAV to a level attitude.

The pilot controls the angular rate of the aircraft, allowing continuous rolls and flips.

---

## 3. Altitude Hold

Altitude Hold automatically maintains the UAV's altitude while allowing the pilot to control roll, pitch and yaw.

The flight controller primarily uses a barometer to estimate altitude and automatically adjusts the throttle to maintain the desired height.

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

---

## 5. Guided

Guided mode allows the pilot or a Ground Control Station to command the UAV to fly to a selected location.

In Mission Planner, the operator can select a location on the map and command the UAV to move there. After reaching the target, the UAV normally holds that location.

---

## 6. Loiter

Loiter automatically maintains the UAV's current position, altitude and heading.

The pilot can still move the UAV using the control sticks. When the sticks are released, the UAV slows down and attempts to return to and hold its previous position.

---

## 7. Return to Launch (RTL)

RTL stands for **Return to Launch**.

When RTL is activated, the UAV automatically returns to its home position, which is normally the location where it was armed.

RTL is mainly used as a safety feature when:
- The pilot loses control
- The battery is low
- The communication link is lost
- The mission needs to be aborted

---

## 8. Circle

Circle mode causes the UAV to fly in a circular path around a specified point.

The UAV maintains a fixed distance from the centre while continuously moving around it.

It can be useful for:
- Surveillance
- Aerial photography
- Inspecting a fixed object
- Demonstrating autonomous navigation

---

## 9. Land

Land mode automatically brings the UAV down and attempts to land it.

The flight controller controls the descent while maintaining horizontal position as appropriate.

It is useful for:
- Automated landing
- Emergency landing
- Completing autonomous missions

---

## 10. Drift

Drift mode provides a more aircraft-like manual flying experience.

It is similar to Stabilize but coordinates yaw and roll so that the UAV can be flown using coordinated turns.

It is useful for:
- Manual flying
- Smooth turns
- Learning coordinated UAV control

---

## 11. PosHold

PosHold stands for **Position Hold**.

It is similar to Loiter because it automatically maintains the UAV's position and altitude. However, the pilot has more direct control over roll and pitch.

When the sticks are moved, the UAV responds manually. When they are released, the flight controller attempts to stop the UAV and hold its position.


---

## 12. Guided_NoGPS

Guided_NoGPS is a variation of Guided mode that does not require GPS.

It is mainly intended for companion computers and specialized applications rather than normal manual flying.
---

## 13. Smart RTL

Smart RTL is an enhanced form of Return to Launch.

Instead of simply flying directly back to the home location, the UAV records its recent flight path and attempts to retrace that path when returning.

This can be useful when:
- The direct path to home may contain obstacles
- The UAV has flown through a narrow route

---

## 14. Follow Mode

Follow mode allows the UAV to automatically follow another vehicle or a ground station.

The UAV receives the target's position and continuously updates its own position to follow it.

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



