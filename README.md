# 🚀 Conveyor Control System Project

*Welcome to the Conveyor Control System repository!* This project demonstrates a conveyor belt system featuring safety, control, and monitoring functionalities using PLC and HMI technologies.

---

## 📜 Project Summary
![conveyor](https://github.com/elfaltntas/CONVEYOR-BELT/blob/main/images/Ekran%20g%C3%B6r%C3%BCnt%C3%BCs%C3%BC%202024-12-22%20130555.png)
This project includes the following:

1. **Safety Mechanisms**:
   - The motor stops when a thermal relay trips, the stop button is pressed, or wiring/contact issues occur.
   - Faults are signaled by a red light flashing at 1 Hz and a buzzer. The buzzer can be silenced independently.

2. **Direction Control**:
   - Forward Operation: Activated with the forward button and indicated by a green light.
   - Reverse Operation: Activated with the reverse button and indicated by a yellow light.
   - Direction changes require the system to be stopped first.

3. **HMI Integration**:
   - Dynamic fault and status indicators with a 100ms data collection cycle.
   - Real-time object tracking based on data blocks.

4. **Data-Based Animation**:
   - Position control for conveyor objects using integer-based data blocks.
   - Custom algorithms for value adjustments and resetting.

---

## 🛠 System Details

### Control Features
- **Start/Stop Logic**: Forward/Reverse buttons operate only after ON/OFF activation.
- **Reset Function**: The buzzer can be stopped, but fault indicators persist until the thermal relay is reset.
- **Smooth Operation**: Conveyor objects move seamlessly based on motor activation.

### HMI Configuration
- **Buttons**: Toggle true/false states through press/release actions.
- **Tags**: All objects and indicators are tag-linked for real-time interaction.
- **Cycle Optimization**: Efficient performance achieved using memory addresses (e.g., M20.0).

---

## 💡 Key Features

- Accurate visual and auditory fault detection.
- Direction control with safety logic.
- Animated conveyor object tracking.
- HMI-based monitoring and control for a user-friendly experience.

---

## 📂 File Structure

```
/conveyor_project
├── PLC_Codes
├── HMI_Configurations
├── Documentation
└── README.md
```

---

## 📞 Contact

For any questions or collaborations:

- 📧 elfaltntas123@gmail.com
