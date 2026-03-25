# AppCage
locks apps like they’re trapped

# AppCage

**AppCage** is an open-source, system-level application blocker for Windows, designed to help users regain focus and control over their digital workflow. It enforces app time limits, blocks distracting applications, and provides a robust, tamper-resistant system for productivity.

---

## Features

- **Time-based blocking** – Set daily or session limits per application.
- **Process enforcement** – Block or terminate apps in real-time.
- **API hooks** – Intercept app launches before they start.
- **Service mode** – Runs in the background for continuous enforcement.
- **Anti-tamper watchdog** – Protects the blocking engine from termination.
- **Persistent storage** – Rules, timers, and usage logs stored in SQLite.
- **Extensible architecture** – Plugin-friendly, modular design for future contributors.

---

## Architecture Overview

AppCage follows a modular architecture inspired by enterprise-level blockers :

- **UI Layer**: Provides a user interface for rules, timers, and status.  
- **Service Layer**: Runs continuously in the background, enforcing rules.  
- **Hook Layer**: Intercepts app launches and prevents blocked processes.  
- **Core Engine**: Evaluates policies and timers.  
- **Persistence Layer**: SQLite database for rules, timers, and logs.  
- **Watchdog**: Monitors service and hook layer to prevent bypassing.

---

## Getting Started

### Prerequisites

- Windows 10/11  
- Visual Studio 2022 or later  
- Qt 6.x (for UI)  
- CMake (for building C++ modules)  
- SQLite 3.x  

### Installation

1. Clone the repository:

```bash
git clone https://github.com/yourusername/AppCage.git
cd AppCage
