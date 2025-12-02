# Enterprise-Grade Calendar Management Platform

> **⚠️ Academic Integrity Note:** This project was developed as part of the **CS 5010** curriculum. To comply with university academic integrity policies, the source code is hosted in a private repository.

## Project Overview

This application is a robust, multi-tenant calendar management system capable of handling complex scheduling requirements. Unlike simple calendar apps, this system was architected with a focus on **extensibility** and **clean object-oriented design**.

It supports full conflict detection, recurring events, and time-zone management, accessible via both a rich Swing GUI and a dual-mode CLI (Interactive & Headless) for automation.

---

## Architecture & Design

The core strength of this project lies in its strict adherence to **SOLID principles** and **Clean Architecture**.

### Key Design Patterns Implemented:
* **Model-View-Controller (MVC):** Strict separation of concerns ensuring the business logic (scheduling rules) is completely isolated from the UI implementation.
* **Command Pattern:** Used to drive controller execution, allowing for extensible user actions without modifying core logic.
* **Builder Pattern:** Implemented for Event and EventSeries creation, ensuring object immutability and preventing inconsistent states during complex object construction.
* **Strategy & Features Interface:** Decoupled the View and Controller layers, allowing the application to switch seamlessly between a Swing GUI and a Command Line Interface without code duplication.

### System Architecture

*(Note: The system utilizes a modular design where the View communicates user actions to the Controller via a `Features` interface, ensuring high cohesion and low coupling.)*

---

## Key Features

### Advanced Scheduling
* **Multi-Calendar Management:** Support for creating and managing multiple distinct calendars within a single application instance.
* **Recurring Events:** Logic to handle daily, weekly, and monthly repetitions.
* **Conflict Detection:** Algorithms to detect and prevent overlapping events across users.
* **Time-Zone Awareness:** Events are normalized to handle global scheduling.

### Dual Interface (UI & CLI)
* **Swing GUI:** A user-friendly desktop interface for visual calendar management.
* **Interactive CLI:** A text-based menu for quick operations.
* **Headless CLI:** Scriptable support for batch processing commands.

### Data & Interoperability
* **Export/Import:** Full support for **CSV** and **iCal** standards.
* **Platform Independence:** Custom file I/O implementation ensuring functionality across different operating systems.

---

## Quality Assurance

* **Testing Framework:** Comprehensive **JUnit** test suite.
* **Coverage:** Extensive unit testing for edge cases with 95% instruction coverage and 90% branch coverage.
* **Modularity:** The codebase is designed for testability, allowing individual components (like the XML parser or Conflict Detector) to be tested in isolation.

---

## Screenshots

### Swing UI View
<img width="882" height="626" alt="image" src="https://github.com/user-attachments/assets/df585367-ed60-45bf-9a1d-20ffdc48f3ff" />
<img width="886" height="628" alt="image" src="https://github.com/user-attachments/assets/e0d27b4d-000d-4b0c-a097-65c3c813086f" />
---

## Access to Source Code

Due to strict university policies regarding the publication of course solutions, the source code cannot be made public.

However, I am happy to grant **Read-Only access** to recruiters, hiring managers, and engineering leads for code review purposes.

### How to Request Access:
1.  Please contact me via **[LinkedIn](https://www.linkedin.com/in/sarvesh-e/)**.
2.  Include a note in your connection request or send a direct message with the subject: "GitHub Access Request: Calendar Project".
3.  Once received, I will add your GitHub username as a collaborator to the private repository.

---
