# Automated Smoke Collector and Filtering Machine
An **air quality monitoring and purification system** that detects **smoke/dust** using the **GP2Y1010AU0F optical sensor**.  
When smoke concentration rises above a safe level:  
- LED indicator  
- Exhaust fan turns ON to pull air through an **activated carbon filter**, removing smoke particles  

---

## ✨ Features
- Real-time smoke/dust concentration measurement  
- Automatic exhaust fan control when unsafe levels detected  
- LED indicator warning system  
- Air filtering via activated carbon layer  
- Serial monitor output for live dust density values  

---

## 🔧 Components
- **Arduino Uno**  
- **GP2Y1010AU0F Optical Dust/Smoke Sensor**  
- **LED + 220Ω resistor**  
- **Exhaust Fan (5V/12V)** + **NPN transistor**  
- **Activated Carbon Filter** (mounted physically in front of exhaust)  
- Jumper wires, breadboard  

---

## 🧰 Circuit Connections

### GP2Y1010AU0F Sensor
| Sensor Pin | Connects To |
|------------|-------------|
| V-LED      | +5V (via 150Ω resistor) |
| LED-GND    | Arduino GND |
| LED        | Arduino Pin 2 |
| S-GND      | Arduino GND |
| Vo         | Arduino A0 |
| Vcc        | +5V |
| GND        | Arduino GND |

### Other Components
- **LED indicator** → Pin 8 → 220Ω resistor → GND  
- **Fan** → Pin 9 → transistor → fan → +Vcc  
- **Carbon filter** → physically placed in front of fan  

---

### Key logic:
- Sensor sampled → analog voltage converted → dust density calculated  
- If dust density > threshold (default = `100 µg/m³`), fan + LED turn ON  
- Otherwise, fan + LED stay OFF  
