# RepSensePublic 🏋

RepSense is a custom-engineered, wearable smart squat tracker designed to provide real-time biomechanical feedback for strength training. By utilizing a 6-axis IMU sensor mounted rigidly to the user, the device continuously monitors femur orientation to accurately track squat depth, count valid repetitions, and filter out unrelated movement.

*Note: The core firmware source code and raw PCB Gerber fabrication files are maintained in a private repository to protect the intellectual property and commercial viability of the tracking algorithms.*

---

##  Engineering Highlights & Technical Overview

This project showcases a complete full-stack hardware product development lifecycle, including custom PCB design, circuit protection, component selection, and mechanical enclosure troubleshooting.

###  System Architecture & State Machine
The device leverages an algorithmic state-machine to track the human body through the distinct phases of a squat:
1. **Upright Standing Baseline:** Establishes the starting reference plane.
2. **Eccentric (Downward) Phase:** Monitors continuous angular rotation.
3. **Depth Threshold Validation:** Pinpoints exactly when the femur passes parallel.
4. **Concentric (Upward) Phase:** Confirms a completed repetition cycle.

###  Custom Hardware Design & BOM
The project integrates a **Seeed Studio XIAO** microcontroller over a shared $I^2C$ bus with:
* **LSM6DS3 6-Axis IMU** for rotational motion tracking.
* **0.96" OLED Display** for user interface and real-time rep counting.
* **Haptic Vibration Motor** driven safely via a **2N7000 MOSFET switch** and protected by a **1N4148 flyback diode** to block inductive voltage spikes.

---

##  Real-World Engineering Challenges Overcome

### 1. Low-Profile Enclosure Clearance Constraint
**The Problem:** Standard plastic female DuPont wire housings proved too tall ($1.5\text{ cm}$ to $2\text{ cm}$) to clear the lid of the ultra-compact clear wearable housing. 
**The Solution:** The plastic connector shells were removed, and short, insulated leads were **direct-soldered flat** to the sensor and display pins, cutting the vertical height clearance profile down to just $3\text{ mm}$ and allowing the case to snap shut securely.

### 2. PCB Footprint Pitch Alignment
**The Problem:** During the prototyping phase of Version 1, the physical sensor breakout board utilized a horizontal pin configuration, while the PCB footprint layout anticipated a vertical array.
**The Solution:** Resolved the physical constraint during final assembly by engineering custom "flying leads" to float the sensor securely inside the housing. 
**Future V2 Optimization:** The next hardware iteration layout has been updated to include non-connected mechanical "dummy" holes to structurally anchor all 10 pins of the module horizontally, eliminating wire jumpers completely.

---

## 📁 Repository Contents
* `README.md` - Technical project overview and engineering case study.
* `media/` - System architecture diagrams, prototype assembly photos, and functional video demonstrations.

---

## 💼 Professional Contact
If you are a recruiter or hardware engineer interested in seeing a live code walkthrough or looking at the schematic architecture via a secure screen-share, please feel free to reach out directly!
