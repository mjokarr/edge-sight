# EdgeSight — IoT Gateway & Predictive Monitoring

> EdgeSight is a portfolio project that demonstrates end-to-end skills in embedded devices, backend engineering, deployment (Linux/Docker), realtime dashboards, and a simple ML-based predictive module.

---

## Project Summary

EdgeSight simulates a typical industrial IoT pipeline: devices (or simulated devices) send telemetry (e.g. temperature, voltage, vibration) to a secure API. The backend ingests, stores and processes telemetry; workers run background tasks for alerting and ML preparation; and a web dashboard visualizes real-time status, historical trends and predictive insights.

This repository is intentionally NDA-safe: all sample data is synthetic and no company-sensitive artifacts are included.

---

## Why this project

This project showcases a rare combination of skills in one polished demo:

* Embedded-to-cloud architecture (device → gateway → API → dashboard)
* Production-minded backend design using Laravel
* Dockerized deployment and Linux ops basics (Nginx, systemd, backups)
* Realtime UI (Livewire/Tailwind) suitable for product demos
* A basic ML pipeline for simple anomaly detection / predictive maintenance

These elements are highly attractive in interviews and MSc/PhD applications for programs in IoT, controls, energy systems, and robotics.

---

## High-level Features

* Telemetry ingestion API (POST /api/telemetry) with validation
* Device management (register / disable / metadata)
* Realtime dashboard: current values, recent history, device list
* Threshold-based alerts (email/webhook) and a simple rules engine
* Background processing with queues for heavy tasks
* Basic ML module (e.g. anomaly detection or binary classification) trained on accumulated logs
* Docker compose stack for local testing and deployment

---

## Repo Layout (high-level)

* /backend — Laravel application (API + dashboard skeleton)
* /simulator — telemetry simulator (Python script or lightweight client)
* /ml — notebooks / scripts for training a simple predictive model
* /docs — architecture diagrams, ADRs, and deployment runbook (DEPLOY.md)
* docker-compose.yml — example local stack (app, db, redis, worker)

---

## Quick Demo Goals (Minimal Viable Demo)

1. Run the backend locally with Docker Compose.
2. Start the telemetry simulator to send synthetic data.
3. Visualize incoming telemetry in the dashboard in near-real-time.
4. Trigger a threshold alert and verify notifications.
5. Run the included ML notebook to generate a simple predictive output and surface it on the dashboard.

---

## Tech Stack (suggested)

* Backend: PHP 8.x, Laravel
* Frontend / Dashboard: Livewire + TailwindCSS
* Simulator: Python (requests / asyncio) or Node.js
* ML: Python (pandas, scikit-learn, simple PyTorch example optional)
* Deployment / Ops: Docker, docker-compose, Nginx, basic systemd/runbook

---

## Minimal Setup (local)

> Basic quickstart (assumes Docker installed):

# clone the repo
git clone https://github.com/mjokarr/edge-sight-iot.git
cd edge-sight-iot

# bring up the stack
docker compose up --build

# open http://localhost:8000 (or the port in docker-compose)
# run the simulator (see /simulator README)

Detailed steps and environment variables are documented in docs/DEPLOY.md.

---

## Expected Deliverables for Portfolio

* Clean README with architecture overview (this file) ✅
* Dockerized backend + simulator (working demo) ✅
* Short demo video (2–4 minutes): show simulator → dashboard → alert → ML output ✅
* Architecture diagram (1 page) and a 10-step runbook for deploy/recovery ✅
* A short writeup (1 page) explaining how this project could be extended for real hardware and for industrial use cases ✅

---

## Next Steps (recommended)

1. Initialize the /backend Laravel skeleton and a basic POST /api/telemetry endpoint.
2. Create a small Python simulator that posts JSON telemetry every 5–10 seconds.
3. Add a Livewire page listing devices and showing a small time-series chart (last N points).
4. Dockerize the stack and prepare a short demo video.

---

## Contact & Notes

This repository is a personal portfolio project. For demo requests, collaboration or questions, contact: your-email@example.com (replace with your contact).

---

*License: MIT — feel free to reuse and adapt for portfolio/demo purposes.*
