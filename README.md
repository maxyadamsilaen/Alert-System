# 🛢️ Drilling Operations Alert System  
## Real-Time Monitoring & Alerting for Drilling Engineers

![Django](https://img.shields.io/badge/Backend-Django%20REST-green)
![Python](https://img.shields.io/badge/Python-3.11-blue)
![Real-time](https://img.shields.io/badge/Real--time-WebSocket-orange)
![License](https://img.shields.io/badge/License-MIT-lightgrey)
![Live Demo](https://img.shields.io/badge/demo-available-brightgreen)

A **real‑time drilling operations alert platform** designed to assist drilling engineers and operators in monitoring critical parameters, detecting anomalies, and receiving actionable alerts during drilling. Built with a **Django REST Framework** backend and a dynamic frontend dashboard, it ingests streaming sensor data, applies rule‑based and predictive analytics, and pushes notifications to the user interface.

🔗 **Live Demo**: [https://drilling-analytic.vercel.app/]  
📘 **API Documentation**: [https://automationai.pythonanywhere.com/docs/]

---

## 📚 Table of Contents

- [Key Features](#key-features)
- [System Architecture & Data Flow](#system-architecture--data-flow)
- [Technology Stack](#technology-stack)
- [Screenshots](#screenshots)
- [Why This Approach?](#why-this-approach)
- [Contact](#contact)

---

## ✨ Key Features

- **Real‑Time Drilling Data Monitoring** – Continuously ingest and display key drilling parameters:  
  `ROP` (Rate of Penetration), `WOB` (Weight on Bit), `RPM`, `Torque`, `Flow`, `SPP`, `Hookload`, `T_Downhole`.

- **Intelligent Alerts** – Automatically detect and notify engineers about critical events:
  - ROP optimisation opportunities
  - Stick‑slip tendency
  - Stuck‑pipe risk (simulated)
  - Hole cleaning issues

- **Well Status Overview** – At‑a‑glance view of multiple wells with progress, stuck pipe, stick slip, and hole cleaning indicators.

- **Drilling Operations Analytics** – Switch between **Time Mode** and **Depth Mode** to analyse historical and real‑time data.

- **Well Cinematic Overview** – Visualise drilling phases (surface, intermediate, production) with current depth and progress percentage.

- **Colour‑Coded Parameter Tracking** – Each parameter has its own colour for quick identification on charts and tables.

- **Alert Acknowledgement & Details** – Operators can acknowledge alerts and view detailed recommendations.

---

## 🏗 System Architecture & Data Flow

The platform follows a **modular, event‑driven architecture** to ensure low latency and scalability.

<img width="5084" height="3632" alt="deepseek_mermaid_20260303_45d13e" src="https://github.com/user-attachments/assets/f6ada325-6dfc-4cb8-a480-6cdebfedbe99" />

- **Data Flow**
  
**Data Ingestion** – Drilling sensors (or a playback file) send real‑time telemetry via MQTT or WebSocket to the Django backend.

**Processing** – The backend validates, stores raw data in PostgreSQL, and forwards it to the Alert Engine.

**Alert Generation** – The Alert Engine applies rule‑based logic and/or ML models to detect anomalies (e.g., ROP below target, stick‑slip patterns).

**Storage & Notification** – Generated alerts are stored and immediately pushed to the frontend via WebSocket or long polling.

**User Interface** – The dashboard displays live parameter charts and a notification panel. Engineers can acknowledge alerts, view details, and receive recommendations.
