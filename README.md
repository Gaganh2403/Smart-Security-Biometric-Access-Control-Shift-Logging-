# Smart-Security-Biometric-Access-Control-Shift-Logging-
 -ESP32 Smart Fingerprint Access Control System

A smart door security system built using the **ESP32**, integrating:
- R305 Fingerprint Sensor for identity verification
- SG90 Servo Motor for physical door control
- OLED display for real-time access status
- Buzzer and LEDs for immediate feedback

This compact and effective system ensures secure, biometric-based access control suitable for smart homes, labs, and restricted areas.

---

## ⚙️ Hardware Components

| Component              | Description                      |
|------------------------|----------------------------------|
| ESP32 Dev Board        | Main microcontroller             |
| R305 Fingerprint Sensor| Biometric verification           |
| SG90 Servo Motor       | Controls the door mechanism      |
| OLED Display (I2C)     | 0.96" 128x64, SSD1306 compatible |
| Buzzer                 | Audio alert                      |
| Red LED                | Denied status indicator          |
| Green LED              | Granted status indicator         |
| Jumper Wires           | For connections                  |
| Breadboard / PCB       | For setup layout                 |

---

## 🔌 Pin Configuration

| Component          | ESP32 Pin | Function               |
|-------------------|-----------|------------------------|
| **OLED SDA**       | GPIO 22   | I2C data               |
| **OLED SCL**       | GPIO 21   | I2C clock              |
| **Fingerprint TX** | GPIO 14   | Connects to ESP32 RX2  |
| **Fingerprint RX** | GPIO 12   | Connects to ESP32 TX2  |
| **Red LED**        | GPIO 25   | Output (access denied) |
| **Green LED**      | GPIO 32   | Output (access granted)|
| **Buzzer**         | GPIO 26   | Output (buzzer)        |
| **Servo Motor**    | GPIO 18   | PWM signal to servo    |


---

## 📦 Library Dependencies

Ensure these libraries are installed via Arduino Library Manager:

- **Adafruit Fingerprint Sensor Library**
- **Adafruit SSD1306**
- **Adafruit GFX Library**
- **ESP32Servo**

---

## ▶️ Working of the Project

1. **System Boot**:  
   On power-up, the ESP32 connects all peripherals and checks for the fingerprint sensor. The OLED displays initial system messages.

2. **Fingerprint Detection**:  
   The system continuously waits for a finger to be placed on the sensor.

3. **Matching Process**:  
   - If a stored fingerprint is matched:
     - OLED displays: **"Access Granted: Opening Door"**
     - Green LED turns on
     - Buzzer sounds
     - Servo rotates to unlock (open) the door
     - After a delay, the servo returns to the locked position, and the system resets
   - If no match is found:
     - OLED displays: **"No Match Found"**
     - Red LED turns on briefly

4. **Enrollment Mode (via Serial Monitor)**:
   - Command `enroll <id>` is used to add a new fingerprint.
   - The system guides the user through placing the same finger twice.
   - Upon successful enrollment, the fingerprint is stored under the given ID.

5. **Input Mode for Testing (Optional)**:
   - Send `input` via Serial Monitor to enter manual test mode.
   - You can simulate actions with commands like `p1`, `p2`, etc.
   - Use `exit` to return to normal fingerprint mode.

---

## 💻 Serial Monitor Commands

| Command         | Description                                      |
|-----------------|--------------------------------------------------|
| `input`         | Enters manual input mode                         |
| `p<number>`     | Simulates a fingerprint match (for testing)      |
| `exit`          | Exits manual input mode                          |
| `enroll <id>`   | Enrolls a new fingerprint with specified ID      |

---

## 📷 System Overview

      +------------------------+
      |        ESP32           |
      +------------------------+
        |       |        |
     OLED    Fingerprint   Servo
    (I2C)     Sensor       Motor
       \         |          /
    Buzzer   Red/Green LEDs


---

## 📍 Applications

- Smart Door Lock Systems  
- Lab or Workspace Access  
- Biometric Attendance Systems  
- DIY Security Projects  

---

## 🔒 License

This project is open-source and licensed under the MIT License.

---

## 🙌 Acknowledgements

Built as part of an embedded systems project focusing on secure, user-friendly access control solutions using ESP32.


