# RFC-001: A Proposed Architecture for the Helios Framework

**Date:** 7/6

## 1. Motivation

The growing complexity of FRC robot need a more constructured, reusable, and maintainable approach to code development. This document proposes the "Helios" architecture, a layered and modular framework.

## 2. Proposed Architecture

![Alt text](https://gi.de/fileadmin/GI/Hauptseite/Service/Lexikon/AUTOSAR_Figure2.jpg)

### 2.1. Layered Design


*   **Application Layer:** Contains all team-specific robot logic, promoting a clean separation of concerns. 
*   **Helios Core:** A reusable middleware providing essential services for scheduling, state management, and communication.
*   **Hardware Abstraction Layer (HAL):** Decouples the software from specific hardware, enabling greater portability and easier hardware swaps. 

### 2.2. Core Framework Components

*   **Real-Time Scheduler:** A priority-based, preemptive scheduler to ensure critical control loops meet their deadlines, enhancing robot predictability.
*   **State Machine Engine:** A formal mechanism for managing robot modes and complex subsystem behaviors, making logic easier to design and debug. 
*   **IPC Bus:** A publish/subscribe message bus for decoupled communication between different parts of the robot code, improving modularity. 

## 3. Rationale for FRC

*   **Improved Maintainability:** By isolating hardware dependencies and separating subsystem logic, the architecture makes the codebase easier to manage and modify.
*   **Enhanced Reusability:** The HAL and Helios Core are designed to be season-agnostic, allowing teams to carry forward a stable software foundation.
*   **Reduced Complexity:** The architecture provides clear patterns for common FRC software problems, reducing the cognitive load on student developers.

## 4. Request for Comments

We are actively seeking feedback on this proposal from the FRC community.  We are particularly interested in critiques regarding:

*   Potential performance overhead on the roboRIO.
*   Strategies for integrating with the existing WPILib libraries.
*   Alternative design patterns that may be better suited for the FRC context.
*   Potential security considerations and mitigation strategies. 

Please contribute to the discussion by opening an Issue or submitting a Pull Request with your suggestions in this repository.
