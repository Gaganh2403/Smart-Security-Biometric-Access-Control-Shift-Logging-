<h1 align="center">🔐 Smart Fingerprint-Based Security System</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Platform-ESP32-blue?style=for-the-badge">
  <img src="https://img.shields.io/badge/Connectivity-WiFi-green?style=for-the-badge">
  <img src="https://img.shields.io/badge/Firebase-Connected-orange?style=for-the-badge">
  <img src="https://img.shields.io/badge/OLED-Display-black?style=for-the-badge">
</p>

---

## 📸 Project Overview

A **Smart Security System** built using an **ESP32 microcontroller**, a **fingerprint sensor**, and **Wi-Fi-enabled real-time logging**. The system records access logs to **Firebase** and offers an **Admin Dashboard** for live monitoring of access attempts.

> 💡 Designed for secure and contactless door access, with visual feedback via OLED display and centralized logging via Firebase.

---

## 🧰 Features

✅ Fingerprint-based secure access  
✅ OLED display for real-time status updates  
✅ Real-time logging using Firebase  
✅ Admin Dashboard for live access log monitoring  
✅ Green/Red LED indicators for access feedback  
✅ Buzzer for audible access confirmation  
✅ Fingerprint enrollment via Serial Monitor  
✅ Manual input simulation mode for testing

---

## 🧠 System Boot Process

- 🔌 On boot:
  - ESP32 connects to the configured Wi-Fi network
  - Initializes fingerprint sensor, OLED display, buzzer, LEDs, and servo motor
  - OLED shows: `Smart Security System`

---

## 👆 Fingerprint Detection Workflow

1. ✅ **If a fingerprint match is found:**
   - OLED shows:
     ```
     Matched ID
     Access Granted
     ```
   - Green LED turns ON  
   - Buzzer sounds  
   - Servo unlocks the door (rotates)
   - Fingerprint ID + timestamp sent to Firebase
   - After a short delay, servo locks the door again

2. ❌ **If no fingerprint match is found:**
   - OLED shows:
     ```
     No Match Found
     Access Denied
     ```
   - Red LED flashes

---

## 🧑‍💻 Enrollment Mode (via Serial Monitor)

### How to Enroll a Fingerprint:

1. 🔐 **Open Serial Monitor** (baud: `115200`)  
2. 💬 **Type the command:**  
