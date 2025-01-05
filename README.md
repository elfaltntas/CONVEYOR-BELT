# 🚀 Conveyor Control System Project

Welcome to the *Conveyor Control System* repository! This project demonstrates a conveyor belt system that incorporates advanced safety, control, and monitoring features using PLC and HMI technologies.

---

## 📜 Project Overview

This project includes:

1. *Safety Mechanisms*:
   - The motor stops when the thermal relay trips, the stop button is pressed, or if wiring/contact issues occur.
   - Fault signaling via a red lamp blinking at 1 Hz and a horn sounding, which can be silenced separately.

2. *Directional Control*:
   - Forward operation: Activated via the forward button and indicated by a green light.
   - Reverse operation: Activated via the reverse button and indicated by a yellow light.
   - Direction changes require the system to stop first.

3. *HMI Integration*:
   - Dynamic fault and status displays with a 100ms acquisition cycle for accurate visual feedback.
   - Real-time object tracking on the conveyor based on data block values (0-100).

4. *Data-Driven Animation*:
   - Integer-based data block for conveyor position control.
   - Custom algorithm for value adjustments and resetting.

---

## 🛠 System Details

### Control Features
- *Start/Stop Logic*: Ensures forward/reverse buttons function only after ON/OFF activation.
- *Reset Functionality*: Stops the horn while maintaining fault indicators until the thermal relay is reset.
- *Smooth Operations*: Conveyor objects move seamlessly based on motor activation.

### HMI Configuration
- *Buttons*: Configured to toggle true/false states using press/release actions.
- *Tags*: All objects and indicators are tag-linked for real-time interaction.
- *Cycle Optimization*: Tags utilize memory addresses like M20.0 for efficient performance.

---

## 💡 Key Features

- Fault detection with precise visual and auditory alerts.
- Directional control with interlocking safety logic.
- Animated conveyor object tracking.
- HMI-driven monitoring and control for a user-friendly experience.

---

## 📂 File Structure


/conveyor_project
├── PLC_Code
├── HMI_Configurations
├── Documentation
└── README.md


---

## 📞 Contact

For any inquiries or collaboration:

- 📧 *Email*: burhanustubi@example.com
- 🐙 *GitHub*: [Your GitHub Profile](https://github.com)

> *"Efficiency and safety are the keys to automation success."*
![konveyor](https://github.com/elfaltntas/CONVEYOR-BELT/blob/main/images/Ekran%20g%C3%B6r%C3%BCnt%C3%BCs%C3%BC%202024-12-22%20130516.png)
