# Enterprise Calendar Management Platform

> **⚠️ Academic Integrity Note:** This project was developed as part of the **CS 5010** curriculum at Northeastern University. To comply with university academic integrity policies, the source code is hosted in a private repository.

A multi-calendar management system built with **Java**, featuring timezone-aware scheduling, recurring events, and dual interface support (Swing GUI + CLI).

## Project Overview

This calendar platform handles complex scheduling scenarios - multiple calendars with independent timezones, recurring event series with flexible modification scopes, and cross-calendar event migration with automatic datetime conversion.

---

## Architecture & Design

The system follows a strict **MVC (Model-View-Controller)** architecture with clear separation of concerns.

### Design Patterns Implemented

| Pattern | Implementation | Purpose |
|---------|----------------|---------|
| **MVC** | Separate model/view/controller packages | Decouple business logic from presentation |
| **Command** | `CalendarCommand` interface + 10 concrete commands | Encapsulate user operations as executable objects |
| **Builder** | `Event.EventBuilder`, `EventSeries.SeriesBuilder` | Construct immutable objects with optional parameters |
| **Factory** | `IeventFactory`, `EventFactory` | Abstract object creation for extensibility |
| **Strategy** | `Features` interface between View and Controller | Enable swappable UI implementations |

### Key Architectural Decisions

- **Features Interface:** Views communicate user actions to Controllers through this contract, enabling the same controller logic to work with different UI implementations (Swing, CLI) without modification.
- **Immutable Events:** Events are final classes with private constructors, built only via Builder pattern - ensures data integrity and thread-safe reads.
- **Command Dispatcher:** CLI input is parsed via regex patterns mapped to `CalendarCommand` implementations through Java functional interfaces.

---

## Key Features

### Multi-Calendar Management
- Create unlimited calendars with independent timezone configurations
- Switch between active calendars seamlessly
- Copy events across calendars with automatic timezone conversion (preserves duration, adjusts wall-clock time)

### Recurring Events Engine
- **Pattern Encoding:** 7-day system (M=Monday, T=Tuesday, W=Wednesday, R=Thursday, F=Friday, S=Saturday, U=Sunday)
- **Termination Options:** Count-based ("repeat 10 times") or date-based ("repeat until Dec 31")
- **Three Modification Scopes:**
  - `ONLY_CURRENT_EVENT` -> Edit single instance only
  - `CURRENT_EVENT_AND_NEXT_IN_SERIES` -> Edit this and all future occurrences
  - `ALL_EVENTS` -> Edit entire series
- **Automatic Series Dissociation:** When temporal properties (start/end time) of a single instance are modified, it detaches from the series to preserve original recurrence pattern

### Timezone Intelligence
- Each calendar maintains independent timezone configuration
- Cross-calendar event migration uses `ZonedDateTime.withZoneSameInstant()` for accurate conversion
- Properly handles timezone offset differences during copy operations

### Dual Interface Support

**Swing GUI:**
- Month grid view with clickable event cards
- Day timeline view with overlap-aware column layout algorithm
- Visual event creation and editing dialogs
- Real-time view refresh on data changes

**Command Line Interface:**
- **Interactive Mode:** Manual command entry with prompt
- **Headless Mode:** Batch processing from command files for automation/scripting

### Export Capabilities
- **iCalendar (.ics):** Timezone-aware export compatible with Google Calendar, Outlook, Apple Calendar
- **CSV:** Spreadsheet-friendly format with formatted date/time columns

---

## Testing

| Metric | Coverage |
|--------|----------|
| Instruction Coverage | 95% |
| Branch Coverage | 90% |

**Testing Approach:**
- **Unit Tests:** Isolated component testing with dependency injection for mocking
- **Integration Tests:** End-to-end command parsing through execution validation
- **Edge Cases:** Series modification conflicts, timezone boundary conditions, duplicate event detection

---


## Screenshots

### Swing UI View
<img width="882" height="626" alt="image" src="https://github.com/user-attachments/assets/df585367-ed60-45bf-9a1d-20ffdc48f3ff" />
<img width="886" height="628" alt="image" src="https://github.com/user-attachments/assets/e0d27b4d-000d-4b0c-a097-65c3c813086f" />


---

## What I Learned

- Applying **SOLID principles** and **design patterns** in a non-trivial codebase
- Trade-offs between **immutability** and ease of modification
- Designing **extensible command processing** systems with regex + functional interfaces
- **Timezone complexity** in scheduling applications (wall-clock vs instant, DST handling)
- Building **testable architecture** through interface segregation and dependency injection
- Creating **UI-agnostic controllers** via abstraction layers


## Access to Source Code

Due to strict university policies regarding the publication of course solutions, the source code cannot be made public.

However, I am happy to grant **Read-Only access** to recruiters, hiring managers, and engineering leads for code review purposes.

### How to Request Access:
1.  Please send an email to elanchezhian.sa@northeastern.edu
2.  **Important:** To ensure verified access, if requesting via email, please use your official company email address. Requests from personal email domains (e.g., Gmail, Yahoo) cannot be processed.
3.  Include a note in your connection request or send a direct message with the subject: "GitHub Access Request: Calendar Project".
4.  Once received, I will add your GitHub username as a collaborator to the private repository.

---
