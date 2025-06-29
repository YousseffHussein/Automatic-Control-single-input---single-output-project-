

# ⚙️ Automatic-Control-SISO-System (Single Input Single Output)

## 📌 Project Description

This project implements a basic **automatic control system** using an **Arduino**. It simulates a Single Input Single Output (SISO) setup where:

- **Input**: A manually adjusted potentiometer (`pot1`).
- **Output**: A second potentiometer (`pot2`) attached to a DC motor, simulating a system being controlled.

The system aims to **align the position of the motor-driven potentiometer** with the manually set value of the first potentiometer, using a feedback loop. The motor rotates until the difference between both values is within a specified tolerance.

---

## 🎯 Objectives

- Demonstrate the concept of **closed-loop control**.
- Use a **DC motor and dual potentiometers** to simulate input-output behavior.
- Implement control logic in **Arduino C++** to track and match input and output values.
- Apply tolerance and dynamic speed control for smoother convergence.

---

## 🔧 Hardware Components

- ✅ Arduino Uno
- ✅ L298N or similar Motor Driver
- ✅ DC Motor connected to a potentiometer (Output)
- ✅ Manual Potentiometer (Input)
- ✅ Power source (battery or USB)
- ✅ Wires and breadboard

---

## 🧠 How It Works

1. **Two potentiometers** are used:
   - `pot1`: The manual input from the user.
   - `pot2`: Connected to a DC motor, acting as the controlled system output.

2. **The Arduino continuously reads both values** and calculates the difference.

3. If the difference is greater than a defined **tolerance threshold** (±12), the motor rotates to reduce the error.

4. **Motor speed is scaled** based on how far off the output is from the input using `map()`.

5. Once both values are approximately equal, the motor stops.

---

## 🧪 Key Features

- Real-time analog feedback control.
- Dynamically scaled motor speed for smoother operation.
- Serial debugging for value tracking and system behavior.
- Clean modular functions for controlling motor direction and stopping.

---

## 🚀 Code Structure

- `setup()`: Initializes pins and serial monitor.
- `loop()`: 
  - Reads potentiometer values.
  - Computes the error.
  - Adjusts motor speed and direction accordingly.
- Helper functions:
  - `rotateClockwise(int speed)`
  - `rotateCounterClockwise(int speed)`
  - `stopMotor()`

---

The project Demo:




https://github.com/user-attachments/assets/b1934819-a788-4cd3-85ed-d3ffb67cef62









------------------------------------------------------------------------

The system:



![Image](https://github.com/user-attachments/assets/3b480b76-75f1-45d1-8370-819111f51892)






