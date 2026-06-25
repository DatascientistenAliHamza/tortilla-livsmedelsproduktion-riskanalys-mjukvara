# Tortilla Production Simulator

A visual production-line simulator built in Python/Pygame. The project demonstrates how real-time manufacturing data, AI-based risk detection, preventive actions, and financial impact can be combined into one clear dashboard.

The simulator is designed as a portfolio-style data science project. It does not use real factory data. Instead, it creates realistic synthetic production events so the logic, UI, and decision-support concept can be demonstrated safely.

---

## Overview

**Tortilla Production Simulator** simulates a tortilla production line from raw material flow to packed products. The dashboard shows production status, OEE, stop risk, machine health, AI prevention status, live events, and estimated financial effect.

The goal is to show how data science can move beyond static reporting and become an operational decision-support tool for production teams.

The system answers questions such as:

- Is the line running normally?
- Which station is creating risk?
- What happens if speed is increased?
- How much does downtime cost?
- Can preventive action reduce stop risk?
- What is the financial impact of better production stability?

---

## Key Features

- Real-time interactive dashboard built with **Pygame**
- Production-line simulation with multiple stations
- Machine health, downtime risk, restarts, and preventive actions
- AI prevention mode that can be turned on or off
- Online model training using `partial_fit`
- OEE, production pace, shift target, speed factor, and event tracking
- Financial impact view with margin, waste, energy, downtime, and net effect
- Saved telemetry for further analysis in Python, Power BI, Excel, or SQL
- Clear operator-style interface with slower, more readable simulation flow

---

## Dashboard Views

The dashboard contains five main views.

### 1. Overview

Shows the overall state of the simulated factory.

Includes:

- Stop risk
- OEE
- Production rate
- Shift target progress
- Prevented stops
- Net financial impact
- Latest event

### 2. Production

Shows the operational side of the line.

Includes:

- Station health
- Line pressure
- Oven zones
- Belt speed
- Product flow
- Packaging and palletizing status

### 3. AI

Shows the decision-support logic.

Includes:

- AI prevention status
- Model state
- Risk drivers
- Prevention decisions
- Manual and automatic actions

### 4. Economy

Translates production changes into financial impact.

Includes:

- Extra produced packs
- Contribution margin
- Avoided downtime cost
- Waste cost
- Extra energy cost
- Estimated net effect

### 5. Log

Shows the event history.

Includes:

- Stops
- Restarts
- Batch changes
- Manual tests
- Preventive actions
- AI decisions

---

## How the Simulation Works

The line is made up of several virtual production stations. Each station has its own health level, criticality, risk behavior, and recovery logic.

During the simulation, the system continuously updates values such as:

- Production speed
- Product flow
- Dough temperature
- Oven temperature
- Humidity
- Line pressure
- Film level
- Energy consumption
- Waste
- Machine health
- Stop risk

Increasing speed can increase production volume, but it can also increase pressure, waste, energy use, and stop risk. This makes the simulator useful for demonstrating the trade-off between higher output and operational stability.

---

## AI Prevention Logic

The AI prevention mode can be switched between **Active** and **Inactive**.

When AI prevention is **Active**, the simulator can perform preventive actions if the calculated risk becomes high. Examples of preventive actions include:

- Stabilizing oven zones
- Reducing line pressure
- Planning a film-roll change
- Performing micro-service on weak stations
- Temporarily lowering production speed

When AI prevention is **Inactive**, the system still measures and displays risk, but no automatic action is taken. This makes it easy to compare passive monitoring with active decision support.

---

## Data Output

When the simulator runs, it creates an `out/` folder with saved data.

```text
out/tortilla_factory.db
out/telemetry_stream.csv
out/training_samples.csv
out/economy_snapshots.csv
out/events.jsonl
```

These files can be used for further analysis in:

- Python / pandas
- Power BI
- Excel
- SQLite
- BI dashboards
- ML experiments

---

## Tech Stack

- Python
- Pygame
- NumPy
- scikit-learn
- SQLite
- CSV / JSONL logging

---

## Project Structure

```text
main.py           Dashboard, UI, navigation, buttons, and interaction
simulation.py     Production logic, machine behavior, downtime, and economy
model.py          Online AI model and risk-driver logic
storage.py        SQLite, CSV, and JSONL persistence
settings.py       Application, production, AI, and economy settings
utils.py          Helper functions
requirements.txt  Python dependencies
README.md         Project documentation
```

---

## Installation

Clone the repository.

```bash
git clone https://github.com/your-username/tortilla-production-simulator.git
cd tortilla-production-simulator
```

Create and activate a virtual environment.

### Windows

```bash
python -m venv .venv
.venv\Scripts\activate
```

### macOS / Linux

```bash
python3 -m venv .venv
source .venv/bin/activate
```

Install dependencies.

```bash
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

Run the simulator.

```bash
python main.py
```

---

## Controls

| Key | Action |
|---|---|
| `Space` | Pause / resume simulation |
| `F` | Toggle demo speed x3 |
| `A` | Toggle AI prevention active/inactive |
| `W` | Increase production speed by 5% |
| `S` | Decrease production speed by 5% |
| `P` | Run preventive action manually |
| `I` | Inject simulated fault |
| `R` | Reset simulation |
| `1` | Open Overview view |
| `2` | Open Production view |
| `3` | Open AI view |
| `4` | Open Economy view |
| `5` | Open Log view |

The main actions are also available as clickable buttons inside the dashboard.

---

## Demo Idea

A strong demo video can be around 60 seconds.

1. Start on the Overview page and show OEE, risk, speed, and net impact.
2. Go to Production and increase the line speed.
3. Show how speed affects production rate, line pressure, and risk.
4. Go to AI and turn prevention off.
5. Inject a fault and show how the event log updates.
6. Turn AI prevention on again and run a preventive action.
7. End on Economy and show the estimated financial effect.

---

## Portfolio Pitch

This project demonstrates how I approach data science in a production environment.

The focus is not only to build charts, but to connect data, process understanding, machine learning, operational risk, and business value into one clear decision-support system.

It shows how a data scientist can help production teams understand what is happening, why it is happening, and what actions may reduce cost, downtime, and waste.

---

## Disclaimer

This is a simulation project using synthetic data. It is not connected to a real tortilla factory, real industrial equipment, or live production systems.
