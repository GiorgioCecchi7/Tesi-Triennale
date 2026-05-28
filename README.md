# Internet of Things: Detecting Cyber Attacks through Power Consumption Analysis

This repository contains the italian documentation for my Bachelor's Thesis in **Computer Engineering** at the **University of Pisa**.

## 📌 Project Overview
The rapid expansion of the Internet of Things (IoT) has introduced significant security challenges. Traditional security solutions like antivirus software are often inapplicable due to the hardware constraints (limited CPU, RAM, and battery) of IoT devices.

This project investigates an alternative, non-intrusive approach: **Behavioral Power Profiling**. By monitoring the energy consumption patterns of an IoT device from the outside, we can identify specific activities and detect malicious behaviors without impacting the device's performance.

## 🛠 Methodology & Tools
### Hardware Setup
- **Target Device:** Raspberry Pi 3 Model B+ (simulating an IoT node).
- **Measurement Tool:** Otii Arc Pro (high-precision power analyzer).
- **Operating System:** Raspberry Pi OS (64-bit).

### Scenarios Analyzed
The study analyzes 6 distinct operational scenarios:
1. **Normal:** Sensor data acquisition and HTTP transmission.
2. **Normal:** Smart Camera human detection (Haar Cascade).
3. **Normal:** Web Server operations (Lighttpd).
4. **Malicious:** SSH Brute Force attack.
5. **Malicious:** DoS attack via DNS Amplification.
6. **Malicious:** DoS attack via HTTP flooding.

## 📊 Data Processing & Machine Learning
Power traces were sampled at **4000 Hz**. Statistical features (Mean, StdDev, Kurtosis, Skewness, RMS, etc.) were extracted using **MATLAB** via 1-second sliding windows.

### Classification Models
We achieved **>99% accuracy** using supervised learning:
- **Ensemble Bagged Trees** (Multi-class classification).
- **Ensemble Boosted Trees** (Binary classification: Normal vs. Malicious).
- **Isolation Forest** (Anomaly Detection for zero-day attack scenarios).

## 📂 Repository Structure
- `/scripts`: Bash and Python scripts used for sensor simulation and attack execution.
- `/matlab`: MATLAB functions for feature extraction and machine learning training.
- `/docs`: A digital copy of the thesis (in Italian) and presentation slides.
- `/data_samples`: Example CSV files of power traces (if applicable).

## 🚀 Key Findings
- Energy consumption is a highly reliable side-channel for IoT security.
- Supervised models can distinguish between similar network activities with near-perfect accuracy.
- **Anomaly Detection (Unsupervised)** shows great promise for detecting unknown attacks, achieving ~90% recall in our tests.

## 👥 Author
*   **Giorgio Cecchi** - [University of Pisa](https://www.unipi.it/)
*   **Advisors:** Prof. Alessio Vecchio, Prof. Pericle Perazzo

## 📄 License
This project is licensed under the [MIT License](LICENSE) - see the file for details.
