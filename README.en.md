# Mechatronics Project - MR2022

## Industrial Curtain Automation with Safety System

**Team 5** | Analysis of Mechatronics Elements

---

## Problem

A manufacturing company that produces industrial curtains requires an automated system for handling curtains measuring 3–7 meters in length and 3–4 meters in width, with 35 kg metal tension bars. The system must:

* Allow automatic raising and lowering
* Detect obstacles to prevent accidents
* Control position limits
* Ensure safety for people and vehicles

**Prototype:** 1 m wide × 2 m long with a 1–2 kg metal bar

---

## System Architecture

![image alt](https://github.com/a00574862-cyber/Anlisis_de_elementos_de_la_mecatrnica_Equipo_5/blob/92daf150ad46942228aae8dd43e4ab75c1ef36dc/Evidence/Imagenes/Software_LOGO_2.0.jpeg)

**Operation flow:**

* I2 (Inductive) detects metal → Activates system → RED light (Q3)
* Motor LOWERS (Q1) until I6 (DOWN magnetic sensor) → GREEN light (Q4)
* If I1 or I3 detect an obstruction → EMERGENCY STOP
* Waits 10s → Motor RAISES (Q2) until I4 (UP) → Reset

---

## Components Used

### Sensors (Inputs)

| Sensor | Type             | Input | Function                                        |
| ------ | ---------------- | ----- | ----------------------------------------------- |
| **S1** | Capacitive       | I1    | Detect presence of rubber/non-metallic material |
| **S2** | Inductive        | I2    | Detect metal tension bars                       |
| **S3** | Optical/Infrared | I3    | Safety - Detect obstacles/people                |
| **S4** | Magnetic         | I4    | Upper limit (UP)                                |
| **S5** | Magnetic         | I5    | Middle position (transition)                    |
| **S6** | Magnetic         | I6    | Lower limit (DOWN)                              |

### Actuators (Outputs)

| Actuator         | Output | Function                                  |
| ---------------- | ------ | ----------------------------------------- |
| **24V DC Motor** | Q1     | Lower curtain (clockwise rotation)        |
| **24V DC Motor** | Q2     | Raise curtain (counterclockwise rotation) |
| **RED Lamp**     | Q3     | Alarm/Emergency stop                      |
| **GREEN Lamp**   | Q4     | System OK/Cycle completed                 |

### Controller and Power Supply

* **PLC:** Siemens LOGO! 12/24 RCE V8
* **Programming:** LOGO!Soft Comfort V8.3
* **Power Supply:** 24V DC / 14.5A / 350W

---

## Control Logic

### Operating Sequence

1. **Activation:** Inductive sensor (I2) detects metal → System activates
2. **Lowering:** Motor (Q1) rolls the curtain DOWN
3. **Safety:** If I1 or I3 detect an obstruction → Motor STOPS and RED light activates
4. **Lower Limit:** When I6 is reached → Motor turns off and GREEN light turns on
5. **Timer:** Waits 10 seconds (B006)
6. **Raising:** Motor (Q2) reverses direction and raises the curtain until I4 (UP)
7. **Reset:** System returns to the initial state

### Implemented Logic Gates

| Block    | Type         | Function       | Condition                          |
| -------- | ------------ | -------------- | ---------------------------------- |
| **B002** | AND          | Allow lowering | I2 (Metal) AND I4 (UP)             |
| **B006** | Timer        | 10s delay      | Activated when I6 is reached       |
| **B007** | AND          | Allow raising  | I6 (DOWN) AND Timer completed      |
| **B009** | RS Flip-Flop | Motor memory   | Maintains operating state          |
| **B010** | OR           | GREEN light    | Multiple success conditions        |
| **B012** | AND          | Safety lock    | Stops operation due to obstruction |
| **B013** | AND          | Emergency stop | I1 (Capacitive) OR I3 (Optical)    |

### Interlocks and Safety Features

* ✅ **Q1/Q2 Interlock:** The motor cannot raise and lower simultaneously
* ✅ **Emergency stop:** Activation by I1 or I3 blocks the motors
* ✅ **Limit protection:** Magnetic sensors stop the motor at extreme positions
* ✅ **Safety timer:** 10-second delay before reversing motor direction

---

## Test Results

### Sensor Validation

| Sensor                        | Tested Condition                        | Expected Result   | Obtained Result |
| ----------------------------- | --------------------------------------- | ----------------- | --------------- |
| **S1 - Capacitive (I1)**      | Bring a non-metallic object within 5 cm | HIGH signal on I1 | ✅ HIGH detected |
| **S2 - Inductive (I2)**       | Bring a metallic object within 3 cm     | HIGH signal on I2 | ✅ HIGH detected |
| **S3 - Optical (I3)**         | Interrupt light beam                    | HIGH signal on I3 | ✅ HIGH detected |
| **S4 - Magnetic UP (I4)**     | Curtain in upper position               | HIGH signal on I4 | ✅ HIGH detected |
| **S5 - Magnetic MIDDLE (I5)** | Curtain in central position             | HIGH signal on I5 | ✅ HIGH detected |
| **S6 - Magnetic DOWN (I6)**   | Curtain in lower position               | HIGH signal on I6 | ✅ HIGH detected |

### Actuator Validation

| Actuator            | Action            | Expected Result           | Obtained Result |
| ------------------- | ----------------- | ------------------------- | --------------- |
| **Motor Q1**        | Activate lowering | Clockwise rotation        | ✅ Correct       |
| **Motor Q2**        | Activate raising  | Counterclockwise rotation | ✅ Correct       |
| **RED Lamp (Q3)**   | Activate alarm    | Light turns on            | ✅ Correct       |
| **GREEN Lamp (Q4)** | System OK         | Light turns on            | ✅ Correct       |

### Functional Tests

| Test             | Expected Result                | Obtained Result |
| ---------------- | ------------------------------ | --------------- |
| **Raising**      | Raising motor turns on         | ✅ Correct       |
| **Waiting Time** | Waits 10s before reversing     | ✅ Correct       |
| **Lowering**     | Relay activates lowering motor | ✅ Correct       |
| **Green Light**  | Turns on when motor stops      | ✅ Correct       |
| **Red Light**    | Turns on during alarm/stop     | ✅ Correct       |

---

## Detected Failures and Adjustments

| Failure                              | Cause                                | Adjustment Made                         | Result             |
| ------------------------------------ | ------------------------------------ | --------------------------------------- | ------------------ |
| Magnetic sensors did not detect      | Distance > 1.5 cm from magnet        | Sensors moved closer to 5 mm            | ✅ Detect correctly |
| Motor rotated in the wrong direction | Inverted wiring polarity             | Q1/Q2 wires were swapped                | ✅ Correct rotation |
| Optical sensor had low sensitivity   | Dirty lens and incorrect calibration | Lens cleaned and potentiometer adjusted | ✅ Detects at 5 cm  |
| LOGO programming errors              | AND/OR gates incorrectly configured  | B002, B007, and B013 corrected          | ✅ Stable logic     |

---

## Video

📹 **Automated Industrial Curtain System Demonstration:**

[![Video Demo](https://img.youtube.com/vi/jsxeerO_dHk/maxresdefault.jpg)](https://youtu.be/jsxeerO_dHk?si=4y5mCOTqE1LufV9U)

**▶️ Click the image to watch the video**

**Video content:**

* ✅ Complete operating sequence
* ✅ Testing of all sensors
* ✅ Safety system in operation
* ✅ Safety indicators

## Team

**Project members:**

| Name                            | Student ID | Responsibilities              | @                |
| ------------------------------- | ---------- | ----------------------------- | ---------------- |
| Andrés Alejandro Sánchez Rábago | A00574862  | Sensors and wiring            | @a00574862-cyber |
| Karol Daniel Cabrera Ramírez    | A00574676  | LOGO programming, integration | @KarolDCabrera   |
| Carlos Tadeo Garay Durá         | A00574676  | Actuators and testing         | @TadeoGadu       |
| Alexa Ortiz Saldaña             | A00573382  | Project Controller            | @ibukiaos        |

---

## Project Status

**✅ FUNCTIONAL AND STABLE SYSTEM**

* [x] Control logic programmed and tested
* [x] Sensors calibrated and validated
* [x] Actuators operating correctly
* [x] Safety system implemented
* [x] Interlocks configured
* [x] Evidence documented

---

## Team Reflection

**What was the most critical aspect of this stage?**

The most critical aspect was **adjusting the distance of the magnetic sensors** so they could correctly detect the curtain positions (UP/MIDDLE/DOWN). Initially, they were positioned more than 1.5 cm away, resulting in inconsistent detection.

It was also critical to **correct the interlock logic** in LOGO to prevent the motor from receiving raising and lowering signals simultaneously, which could damage the system.

Once the sensor distances were adjusted to 5 mm and the programming of blocks B002, B007, and B013 was corrected, the system became stable and fully functional.

---

## Repository

📂 **Project structure:**

* `/Docs/H1_requisitos` - Analysis and requirements
* `/Docs/H2_sensores` - Component selection
* `/Docs/H3_actuadores_seguridad` - Control and integration
* `/Docs/H4_Control_Hdm` - Functional validation
* `/Docs/H5_Entregables finales` - Final deliverables

---

*Last updated: March 2026*

