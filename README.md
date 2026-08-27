# Avionics Induction Task 1 - Data Analysis

## 📌 Project Overview
This project focuses on processing and visualizing sensor/avionics data using Python (`pandas`, `numpy`, and `matplotlib`). 

## 💡 Author's Note & Personal Reflection
> **Honesty & Process Disclosure:**  
> I am a complete beginner when it comes to writing code from scratch. Every script, plot design, and logic structure in this task was generated with the assistance of Artificial Intelligence (AI). 
> 
> However, I took full ownership of the project by:
> - Formulating, testing, and refining detailed prompts to solve technical errors.
> - Independently troubleshooting environment issues (e.g., configuring Python/pip PATH variables and dependencies).
> - Tracing and understanding how each data transformation and visualization worked under the hood.
> 
> My main goal in applying for this team is to transition from AI-assisted prompt engineering to writing raw code independently.

---

## 🛠️ Dependencies & Setup
Run the following command in your terminal to install the necessary libraries:

```cmd
python -m pip install pandas numpy matplotlib
---

### Task 2: Odysseus State Machine (`README.md`)

```markdown
# Avionics Induction Task 2 - Odysseus Navigation State Machine

An Arduino-based Finite State Machine (FSM) designed in Tinkercad to simulate navigation hazards, emergency overrides, and timed state transitions.

## 📌 Hardware Components & Pin Mapping
| Component | Arduino Pin | Description |
| :--- | :--- | :--- |
| **Push Button** | Pin 2 | Anchor Emergency Override (`INPUT_PULLUP`) |
| **LCD Display (16x2)** | Pins 7, 6, 5, 4, 3, 10 | Real-time state display |
| **HC-SR04 Ultrasonic** | Trig: Pin 9, Echo: Pin 8 | Charybdis Hazard Detector |
| **Piezo Buzzer** | Pin 11 | Charybdis (800 Hz) & Wrecked (200 Hz) Alarm |
| **Warning LED** | Pin 12 | Storm Warning (Blinking) & Wrecked Indicator |
| **Photoresistor (LDR)**| Analog Pin A0 | Storm Hazard Detector |

---

## 🚦 State Machine Rules
1. **OPEN SEA (State 0):** Normal navigation mode. LCD displays normal status.
2. **STORM (State 1):** Triggered when light levels drop. Blinks the LED every 200ms and starts a 5-second countdown.
3. **CHARYBDIS (State 2):** Triggered when distance is $< 100\text{ cm}$. Sounds an 800 Hz continuous tone and starts a 5-second countdown.
4. **ANCHOR DROPPED (State 3):** Triggered by pressing the push button. Immediately overrides Storm/Charybdis hazard states and resets timers.
5. **WRECKED (State 4):** Latches permanently if Storm or Charybdis hazard timers run out (5 seconds continuous). Solid LED and continuous alarm.

---

## 💡 Author's Note & Learning Journey
> **Honesty & Process Disclosure:**  
> I entered this task with zero prior knowledge of C++, state machine logic, or physical circuit design. Every line of Arduino code and breadboard layout was created collaboratively with AI guidance. 
> 
> Throughout this project, I:
> - Spent hours debugging hardware misconfigurations (e.g., floating button states, pull-up vs. pull-down LDR wiring, pin conflicts).
> - Learned how state machine priorities, non-blocking timers (`millis()`), and hardware debouncing work.
> - Carefully directed every code iteration to ensure strict adherence to task requirements.
> 
> I am extremely curious about avionics hardware and eager to build on this foundational project as a member of the team.
