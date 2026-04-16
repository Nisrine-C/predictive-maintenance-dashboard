# Predictive Maintenance Dashboard

A cross-platform dashboard built in Flutter for monitoring equipment (gears), predicting faults, and visualizing Remaining Useful Life (RUL).


## Features

- **Equipment Management:** Track industrial gears and their status
- **Fault Prediction:** Visualize predicted faults, maintenance suggestions, and confidence
- **Modern Clean UI:** Interactive interfaces with custom widgets for progress, status, and fault info
- **Consistent Styling:** Centralized color and style management


## Project Structure

- **Constants:** Global color definitions for consistent UI
- **Model:** Dart data models (`Fault`, `Gear`, `Prediction`)
- **Screen:** Main dashboard (Home) and gear detail views
- **Widget:** Reusable UI components (GearItem, ProgressBar, StatusIndicator)

<img src="./images/project_structure.png" alt="Project structure diagram" />


## UI Screenshots

### Main & Detail Interfaces

<p align="center">
  <img src="./images/Interface2.png" alt="Interface screenshot 2" width="45%"/>
  <img src="./images/Interface1.png" alt="Interface screenshot 1" width="45%"/>
</p>
---

## Color System

The app uses a centralized color system for consistency.

<img src='./images/colors.png' alt="App color palette" />


## Core Modules & Code

### Models

<details>
<summary><b>Fault</b></summary>

```dart
class Fault {
  final int faultId;
  final int faultCode;
  final String faultDesc;
  
  Fault({required this.faultId, required this.faultCode, required this.faultDesc});
}
```
</details>

<details>
<summary><b>Gear</b></summary>

```dart
class Gear {
  final int gearId;
  final int faultId;
  final DateTime installationDate;
  final double expectedLifetimeHours;

  Gear({required this.gearId, required this.faultId, required this.installationDate, required this.expectedLifetimeHours});
}
```
</details>

<details>
<summary><b>Prediction</b></summary>

```dart
class Prediction {
  final int gearId;
  final int predictedFaultCode;
  final double predictedRulHours;
  final double confidence;

  Prediction({required this.gearId, required this.predictedFaultCode, required this.predictedRulHours, required this.confidence});
}
```
</details>


## Main Screens

### Home (Dashboard)
```dart
class Home extends StatelessWidget {
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: _buildAppBar(),
      ...
      // See full example in project
    );
  }
}
```

### Detail
```dart
class Detail extends StatelessWidget {
  final int gearId;
  ...
}
```


## Custom Widgets

<details>
<summary><b>GearItem</b> - Equipment List Entry</summary>

Displays important metrics, recommended actions, and a maintenance button.
</details>

<details>
<summary><b>ProgressBar</b> - RUL Bar</summary>

Visualizes how much useful life remains.
</details>

<details>
<summary><b>StatusIndicator</b> - Condition Tag</summary>

Small labeled indicators (e.g., green for ok, red for failure).
</details>


## Getting Started

1. Clone the repo  
   `git clone https://github.com/Nisrine-C/pi_protype.git`
2. Run with Flutter (see your configuration for details).
