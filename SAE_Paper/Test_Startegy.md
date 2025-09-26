# Test Strategy for Instrument Cluster & Infotainment

## 1. Objectives

| Objective ID | Description                                           |
|--------------|-------------------------------------------------------|
| OBJ-1        | Ensure feature consistency across powertrain variants |
| OBJ-2        | Early detection of integration bugs (Shift-Left Testing) |
| OBJ-3        | Modular, scalable approach for ICE, Hybrid, EV        |

## 2. Scope of Testing

| Component           | Scope Description                                           |
|---------------------|-------------------------------------------------------------|
| Instrument Cluster  | Gauges, telltales, CAN, HMI Graphics                        |
| Infotainment        | Media, navigation, connectivity across ICE, Hybrid, EV      |

## 3. Test Planning Approach

| Approach Type         | Description                                               |
|-----------------------|-----------------------------------------------------------|
| Requirement Mapping   | SysReq → Feature → Test Case                              |
| Model-Based Design    | Model-based Test Design (MBT)                             |
| Mode Definition       | Define vehicle modes and IC-IVI interactions              |

## 4. Test Levels

| Level             | Description                                      | Tools/Techniques               |
|-------------------|--------------------------------------------------|--------------------------------|
| Unit Test         | Function-level testing                           | CMock, GoogleTest              |
| Integration Test  | CAN to display logic                             | Python, CAPL                   |
| System Test       | ECU/domain validation                            | HIL, Bench                     |
| Acceptance Test   | Scenario-based validation                        | LabCar, Vehicle                |

## 5. Test Types

| Type             | Description                                       |
|------------------|---------------------------------------------------|
| Functional       | Feature validation                                |
| Regression       | Re-testing after changes                          |
| Performance      | Speed, responsiveness                             |
| Usability        | User experience                                   |
| Diagnostic       | UDS, DTCs                                         |
| HMI Validation   | Visual checks using OpenCV                        |

## 6. Domain-Specific Testing

| **Domain** | **Testing Parameters**                                   |
|------------|----------------------------------------------------------|
| ICE        | Gear Info, Fuel Level, Coolant                           |
| Hybrid     | EV/Hybrid Mode, Battery Gauge                            |
| EV         | SOC (State of Charge), Charging Status, Regen Indicator  |

## 7. Automation Strategy

| Area              | Tools/Methods                                     |
|-------------------|---------------------------------------------------|
| Scripting         | Python, Robot Framework                           |
| CAN Tools         | Vector CANoe, SocketCAN                           |
| Display Capture   | HDMI + OpenCV                                     |

## 8. Test Environment Setup
| Environment Type | Description                                       |
|------------------|---------------------------------------------------|
| SIL              | Software-in-the-loop                              |
| MIL              | Model-in-the-loop                                 |
| HIL              | Hardware-in-the-loop                              |
| Bench            | Physical test benches                             |
| Vehicle          | On-road testing                                   |
| Virtual Signals  | Early validation using simulated inputs           |

## 9. Shift-Left Development

| Strategy Element     | Description                                   |
|----------------------|-----------------------------------------------|
| CI/CD Integration    | GitLab, Jenkins                               |
| BDD                  | Gherkin, Robot Framework                      |
| Virtual ECUs         | Use for early-stage testing                   |

## 10. Traceability & Test Management

| Tool/Method         | Purpose                                         |
|---------------------|-------------------------------------------------|
| ALM Tools           | Polarion, DOORS for requirement traceability    |
| Reporting           | Automated reports in Excel, HTML, PDF           |

## 11. Test Data Strategy

| Data Type           | Description                                     |
|---------------------|-------------------------------------------------|
| Synthetic Datasets  | Charging cycles, speed profiles                 |
| Scenario Replay     | CSV/JSON-based test scenarios                   |

## 12. Common Test Case Library

| Category       | Example Test Cases                                  |
|----------------|-----------------------------------------------------|
| Startup        | Boot logo, telltales                                |
| CAN Signal     | RPM accuracy                                        |
| Diagnostics    | DTC triggers                                        |
| Audio          | FM tuning, media resume                             |
| EV             | SOC progression, charging UI                        |
| IC-IVI Sync    | Turn-by-turn navigation                             |
