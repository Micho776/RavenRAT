# MickeyMouse – Educational Android Remote Administration Tool

> **⚠️ LEGAL & ETHICAL WARNING**  
> This project is **for educational purposes only**. It is designed to teach Android security, network resilience, and stealth techniques.  
> **You may only use this tool on devices you own or have explicit written permission to test.**  
> Unauthorized access to devices is illegal and unethical. The author assumes no liability for misuse.

---

## 📖 Overview

RavenRAT is a stealthy Android Remote Access Tool that demonstrates:

- **No launcher icon** – invisible installation
- **Persistence** – auto-starts on device boot
- **Network resilience** – works over IPv4, IPv6, and via ngrok tunnels
- **Google Sheets C2** – uses free Google infrastructure as command & control
- **Extensible command set** – easily add camera, file upload, keylogging, etc.

This project is ideal for cybersecurity students to learn how RATs operate and how to defend against them.

---

## ✨ Features

| Feature | Implementation |
|---------|----------------|
| Hidden app (no icon) | Removed `LAUNCHER` intent filter |
| Background service | Foreground service + auto-restart on boot |
| C2 communication | HTTPS POST to Google Apps Script webhook |
| Multi-network | Works on any network (IPv4/IPv6 via HTTPS) |
| Command execution | Polls Google Sheet for commands (extensible) |
| Stealth start | ADB or hidden SMS trigger (SMS code optional) |

---

## 🧠 How It Works

1. **Victim installs the APK** (via phishing, social engineering, or physical access).
2. **App has no icon** – victim doesn't see it.
3. **Service starts automatically** on boot and runs in background.
4. **App reports device info** (IP, device name, local web panel link) to a Google Sheet via HTTP POST.
5. **Attacker monitors the Google Sheet** – sees live devices.
6. **Attacker sends commands** by writing to a specific cell; the app polls and executes them.
7. **Commands can include**: camera capture, file listing, location, etc.

---

## 📋 Prerequisites

- **Android Studio** (latest) – [Download](https://developer.android.com/studio)
- **Java JDK 8+** – included in Android Studio
- **Google account** – for Google Sheets & Apps Script
- **Test Android device** (API 26+ / Android 8+ recommended)
- **ADB** (Android Debug Bridge) – for initial service start (or you can add SMS trigger)

---

## 🚀 Setup & Installation

### Step 1: Clone the Repository

```bash
git clone https://github.com/yourusername/RavenRAT.git
cd RavenRAT
