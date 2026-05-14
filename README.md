# CPU Process Scheduling Algorithms Simulator

**Tarlac State University — College of Computer Studies**
**Bachelor of Science in Computer Science | Operating Systems**
**Academic Year 2025–2026**

> A web-based simulator that implements six fundamental CPU scheduling algorithms, generates dynamic Gantt charts, and computes per-process Waiting Time and Turnaround Time.

---

## Table of Contents

- [Overview](#overview)
- [Algorithms Implemented](#algorithms-implemented)
- [Features](#features)
- [How to Run](#how-to-run)
- [How to Use the Simulator](#how-to-use-the-simulator)
- [Input Parameters](#input-parameters)
- [Output](#output)
- [Repository Contents](#repository-contents)
- [Video Demonstration](#video-demonstration)
- [Author](#author)

---

## Overview

This project is a browser-based CPU Scheduling Simulator developed as a case study for the Operating Systems course at Tarlac State University. It simulates how an operating system schedules processes to run on the CPU using six different algorithms, making the scheduling behavior visible through dynamic Gantt charts and metric tables.

No installation or server setup is required — the simulator runs entirely in a single HTML file opened in any modern web browser.

---

## Algorithms Implemented

| # | Algorithm | Type |
|---|-----------|------|
| 1 | First-Come, First-Served (FCFS) | Non-preemptive |
| 2 | Shortest Job First (SJF) | Non-preemptive |
| 3 | Shortest Remaining Time (SRT) | Preemptive |
| 4 | Round Robin (RR) | Preemptive |
| 5 | Priority Scheduling | Non-preemptive & Preemptive (user selects) |
| 6 | Priority Scheduling with Round Robin | Preemptive |

---

## Features

- Accepts user-defined process parameters (minimum 3, maximum 20 processes)
- Supports configurable Priority convention — user chooses whether higher or lower value means higher priority
- Dynamic Gantt Chart showing exact execution timeline per process
- Per-process table of Waiting Time (WT) and Turnaround Time (TAT)
- Computed Average Waiting Time and Average Turnaround Time
- Handles idle CPU gaps when no process is ready
- Fully runs in the browser — no installation needed

---

## How to Run

### Option 1 — Open directly in a browser (Recommended)

1. Download or clone this repository:
   ```bash
   git clone https://github.com/ciaoski/CPU_Scheduling_Algorithm.git
   ```
2. Open the `index.html` file in any modern browser (Chrome, Firefox, Edge):
   - Double-click `index.html`, **or**
   - Right-click → *Open with* → your browser

That's it. No server, no dependencies, no installation.

---

### Option 2 — Run with a local server (Optional)

If your browser blocks local file access, you can serve it locally:

**Using VS Code Live Server:**
1. Install the [Live Server extension](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)
2. Right-click `index.html` → *Open with Live Server*

**Using Python:**
```bash
# Python 3
python -m http.server 8080

# Then open: http://localhost:8080
```

**Using Node.js:**
```bash
npx serve .
# Then open the URL shown in your terminal
```

---

## How to Use the Simulator

1. **Enter the number of processes** (minimum 3)
2. **Fill in the process table** — each row represents one process:
   - Process ID (e.g., P1, P2, P3...)
   - Arrival Time
   - Burst Time
   - Priority *(only required for Priority Scheduling algorithms)*
3. **Select a scheduling algorithm** from the dropdown
4. **Configure additional settings** if prompted:
   - Time Quantum — for Round Robin and Priority + RR
   - Priority mode — for Priority Scheduling (Non-preemptive or Preemptive)
   - Priority convention — higher value = higher priority, or lower value = higher priority
5. Click **Run Simulation**
6. View the **Gantt Chart** and **Results Table** below

---

## Input Parameters

| Parameter | Description | Required For |
|-----------|-------------|--------------|
| Number of Processes | Minimum 3, maximum 20 | All algorithms |
| Process ID | Label for each process (e.g., P1, P2) | All algorithms |
| Arrival Time | Time the process enters the ready queue | All algorithms |
| Burst Time | Total CPU time the process needs | All algorithms |
| Priority | Numeric priority value per process | Priority Scheduling, Priority + RR |
| Time Quantum | Fixed CPU time slice per turn | Round Robin, Priority + RR |
| Priority Convention | Whether higher or lower number = higher priority | Priority Scheduling, Priority + RR |

---

## Output

For every simulation run, the program produces:

**Gantt Chart**
A horizontal timeline showing which process occupied the CPU at each time unit, including any idle periods.

**Results Table**

| Process | Arrival Time | Burst Time | Completion Time | Turnaround Time (TAT) | Waiting Time (WT) |
|---------|-------------|------------|-----------------|----------------------|-------------------|
| P1 | ... | ... | ... | CT − AT | TAT − BT |
| ... | | | | | |

**Summary Metrics**
- Average Waiting Time = Sum of all WT ÷ Number of processes
- Average Turnaround Time = Sum of all TAT ÷ Number of processes

---

## Repository Contents

```
cpu-scheduling-simulator/
│
├── index.html              # Main simulator — open this in your browser
├── README.md               # This file
│
├── docs/
│   └── CPU_Scheduling_Case_Study.docx   # Full documentation (hardcopy)
│
└── demo/
    └── demo_video.mp4      # Video demonstration (or see link below)
```

>
> `https://drive.google.com/file/d/1nUdQmD0l6G-qZizkq-Y7oEF8Ii5_bfwV/view?usp=sharing`

---

## Video Demonstration

📹 Watch the full video demonstration here: **https://drive.google.com/file/d/1nUdQmD0l6G-qZizkq-Y7oEF8Ii5_bfwV/view?usp=sharing**

The video covers:
- Program overview and input demonstration
- Live simulation of all 6 scheduling algorithms
- Gantt chart and results explanation
- Summary and comparison of algorithm performance

---

## Author

**ROSACASE, Bei Fatima I.**
Bachelor of Science in Computer Science — BSCS 3B
Tarlac State University
Operating Systems | Academic Year 2025–2026

---

## References

- Silberschatz, A., Galvin, P. B., & Gagne, G. (2021). *Operating system concepts* (10th ed.). Wiley.
- Tanenbaum, A. S., & Bos, H. (2023). *Modern operating systems* (5th ed.). Pearson.
- Arpaci-Dusseau, R. H., & Arpaci-Dusseau, A. C. (2023). *Operating systems: Three easy pieces*. Arpaci-Dusseau Books.
- GeeksforGeeks. (2026, January 6). *CPU scheduling in operating systems*. https://www.geeksforgeeks.org/cpu-scheduling-in-operating-systems/
- Tutorialspoint. (n.d.). *Round Robin (RR) scheduling algorithm*. Retrieved May 14, 2026, from https://www.tutorialspoint.com/operating_system/os_round_robin_scheduling_algorithm.htm
