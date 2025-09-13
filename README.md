# AirCat
Autonomous hull flying 
# AirCat

Based around [Ardupilot Sailboat](https://ardupilot.org/rover/docs/sailboat-home.html), AirCat is an experimental control system for flying the hull of a model catamaran.  
Using real-time sensors and estimation (including roll, roll rate, wind measurements), the system automatically trims the mainsheet to maintain a target heel angle — letting one hull lift while keeping stability and avoiding stall.

---

## 🎥 Demo Video

[![AirCat in action](https://img.youtube.com/vi/XxnVeJbFZ58/0.jpg)](https://youtube.com/shorts/XxnVeJbFZ58?si=_iOAInywII4Alrcp)

*Click the image to watch a video showing the catamaran flying one hull under changing wind conditions, demonstrating the kind of behaviour this project aims to control.*

---

## 🚀 Project Goals

- Learn & estimate the aerodynamic heel (heeling) moment in varying wind and sail conditions  
- Use that estimate to drive a control algorithm that keeps the desired heel angle without stalling the sail  
- Provide a clear, well-documented codebase so others can adapt or extend it (different boat designs, sensor sets, etc.)  
- Improve performance and safety of hull-flying (less oscillation, better speed, more stable behaviour)  

---

## 📋 How It Works (overview)

Briefly:

- Inputs: roll angle & roll rate (from IMU), apparent wind speed & angle, sail angle  
- Estimator: Kalman filter to learn the current heeling moment  
- Controller: PID (and possibly feedforward from wind speed) managing mainsheet angle to hold target heel  
- Safety limits: avoid exceeding maximum lift coefficient (stall), limit sheet/furl movement, trim for gusts  

---

## 🛠 Getting Started

ToDo

---

## 🧾 Variable Naming & Conventions

Ideally we will use strongly typed physical quantities such as are used in [my quan library](https://github.com/kwikius/quan-trunk/blob/master/quan_matters/examples/box_example.cpp)
my (pqs library](https://github.com/kwikius/pqs/wiki) and  [mp_units](https://mpusz.github.io/mp-units/latest/)
To keep code clear, we use descriptive variable names with units appended, e.g.: 

| Variable | Unit | Description |
|---|---|---|
| `rollAngle_deg` | ° | Positive = starboard hull down, negative = port hull down |
| `rollRate_dps` | °/s | Positive → increasing rollAngle (towards starboard down) |
| `apparentWindAngle_deg` | ° | Zero = wind ahead, positive = wind from starboard, negative = from port |
| `sailAngle_deg` | ° | Zero = sail aligned with centerline, positive = sail let out to starboard |
| `mainsheetAngleCommand_deg` | ° | Commanded sail angle in same sign convention as sailAngle_deg |

---

## ⚠️ Licensing

ToDo

---

## 🤝 Contributing

ToDo
