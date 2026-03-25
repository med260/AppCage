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

AppCage follows a modular architecture inspired by enterprise-level blockers like Cold Turkey:

```

UI (Qt C++) → IPC (Named Pipes) → Service (C++) → Hook Layer (C++) → Core Engine (C++) → SQLite DB
↘ Watchdog / Anti-Tamper

````

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
````

2. Build Core Engine, Hook Layer, and Service:

```bash
mkdir build && cd build
cmake ..
cmake --build . --config Release
```

3. Build the UI with Qt:

```bash
cd ../ui
qmake AppCage.pro
make
```

4. Run the Service (administrator privileges required):

```bash
AppCageService.exe install
AppCageService.exe start
```

5. Launch the UI and configure your blocking rules.

---

## Contribution

We welcome contributions! To contribute:

1. Fork the repository.
2. Create a feature branch: `git checkout -b feature/my-feature`
3. Commit your changes: `git commit -m 'Add my feature'`
4. Push to the branch: `git push origin feature/my-feature`
5. Open a Pull Request.

Check the `docs/` folder for detailed **architecture guides**, **plugin development**, and **contribution guidelines**.

---

## License

AppCage is released under the **MIT License**. See [LICENSE](LICENSE) for details.

---

## Future Roadmap

* Plugin system for custom blocking rules
* Network blocking via Windows Filtering Platform
* Optional kernel-level enforcement for advanced users
* Statistics and reporting dashboards
* Cross-platform support for macOS (experimental)



## Contact

For questions, feedback, or support, create an issue on GitHub or contact the maintainers.

---

> Take control of your focus — trap distractions before they escape.
> **AppCage**

