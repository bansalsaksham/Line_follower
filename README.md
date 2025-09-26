# 🤖 Line Follower Robot (Arduino + Adafruit Motor Shield)

This project is an **Arduino-based Line Follower Robot** that uses two IR sensors and the **Adafruit Motor Shield** to detect and follow a line on the ground. The robot adjusts its movement based on the sensor inputs to stay aligned with the line.

---

## 🚀 Features
- Dual **IR sensors** (left and right) for line detection  
- Motor control using **Adafruit Motor Shield**  
- Movement logic:
  - Move forward when no line is detected  
  - Stop when both sensors detect the line  
  - Turn left or right depending on which sensor detects the line  

---

## 🛠️ Components Required
- Arduino UNO (or compatible board)  
- Adafruit Motor Shield (v1 or v2 depending on your setup)  
- 2 × DC Motors with wheels  
- 2 × IR sensors (left & right)  
- Power source (Battery pack)  
- Chassis and wires  

---

## ⚡ Circuit Connections
| Component            | Arduino/Motor Shield Pin |
|----------------------|---------------------------|
| Left IR Sensor OUT   | A4                        |
| Right IR Sensor OUT  | A5                        |
| Motor 1 (Left)       | M4                        |
| Motor 2 (Right)      | M3                        |
| IR Sensor VCC        | 5V                        |
| IR Sensor GND        | GND                       |

*The motors are connected through the Adafruit Motor Shield.*  

---

## 📜 Code Explanation
- `lefts = A4` and `rights = A5` are the IR sensors.  
- Motors are controlled using the **AFMotor library**:  
  - `motor1 = M4` (Left motor)  
  - `motor2 = M3` (Right motor)  
- Threshold for line detection is set at **400** (can be adjusted).  
- Movement logic:
  - **Both sensors detect line** → Stop  
  - **Left detects line only** → Turn left  
  - **Right detects line only** → Turn right  
  - **Neither detects line** → Move forward  

---

## ▶️ Usage
1. Assemble the robot with two DC motors, two IR sensors, and the Motor Shield.  
2. Upload the code to your Arduino board.  
3. Place the robot on a track with a clear **black line on a white surface** (or inverted).  
4. Open the **Serial Monitor** (`9600 baud`) to see sensor values.  
5. Adjust the threshold (`400` in code) if needed depending on your IR sensors and track conditions.  

---

## 📸 Example Output (Serial Monitor)
- 512
- 489
- 350
- 370

Each line corresponds to the **analog values** of the left and right IR sensors.

---

## 📂 Project File
- **line_follower.ino** – The Arduino sketch file  

---

## 📌 Notes
- Adjust `motor.setSpeed(200)` if your motors are too fast/slow.  
- Ensure proper lighting and contrast between the line and background.  
- Sensor threshold (`400`) may vary depending on your IR sensor model.  
- For smoother performance, you can add **PID control** later.  

---

## 🎯 Applications
- Educational robotics projects  
- Autonomous navigation  
- Obstacle and line-following competitions  
- Foundation for advanced robotics (maze solvers, AI navigation)  

---

