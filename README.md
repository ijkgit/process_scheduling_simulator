# Basic Process Scheduling Algorithms in Python with Tkinter GUI

## Overview
This project implements the core process scheduling algorithms in operating systems using Python. It encompasses First-Come, First-Served (FCFS), Round Robin (RR), Shortest Process Next (SPN), Shortest Remaining Time Next (SRTN), and Highest Response Ratio Next (HRRN) algorithms, essential for understanding process management and scheduling in computer science.

## Features
- **Algorithm Implementation**: Each scheduling algorithm (FCFS, RR, SPN, SRTN, HRRN) is meticulously coded to simulate process scheduling.
- **Graphical User Interface**: Developed using Tkinter, the GUI provides an interactive visualization and control of the scheduling process.
- **Gantt Chart Visualization**: Offers a clear and detailed view of process execution order and duration through Gantt charts.

## Advanced Core and Power Management
- **P-Core and E-Core Support**: Adapted for modern CPU architectures with Performance cores (P-cores) and Efficiency cores (E-cores), enhancing the scheduling for performance and energy efficiency.
- **Dynamic Scheduling for Core Types**: Assigns resource-intensive tasks to P-cores and less demanding tasks to E-cores, balancing performance and power consumption.
- **Power Consumption Analysis**: Includes a feature to calculate and compare the power consumption differences between tasks scheduled on P-cores and E-cores, providing insights into energy efficiency.

## Comprehensive Metrics Calculation
- **Arrival Time**: Tracks the time at which a process enters the scheduling system.
- **Burst Time**: Measures the time a process takes to execute on a CPU.
- **Waiting Time**: Calculates the time a process spends waiting in the scheduling queue.
- **Turn-Around Time**: Determines the total time taken from the arrival of a process to its completion.
- **Normalized Turn-Around Time**: Evaluates the turn-around time relative to the burst time, offering a normalized metric for performance comparison.

### User Interface
![Process Scheduling Simulator Interface](https://github.com/joowon7172/process_scheduling_simulator/assets/83939775/7a1eec28-1cc8-499b-8b82-4c95bfd25f5b)
The user interface is intuitive and straightforward, allowing for easy input of process data such as arrival time and burst time, as well as the selection of the scheduling algorithm. The interface also displays a table of processes with their respective metrics, such as waiting time and turn-around time, including the normalized turn-around time. Moreover, it provides an estimation of the power consumption for the selected scheduling.

### Gantt Chart Output
![FCFS Scheduling Gantt Chart](https://github.com/joowon7172/process_scheduling_simulator/assets/83939775/99d66996-89f0-4ab8-be9c-2f945b2fe664)
The Gantt chart offers a visual representation of the scheduling order and duration for each process, as illustrated here for the FCFS scheduling algorithm. This visual aid is essential for understanding how different scheduling algorithms will execute the processes.

## SPNRR: A Hybrid of SPN and RR
### Concept
- **Combination of SPN and RR**: The SPNRR algorithm is a novel scheduling method that combines elements of Shortest Process Next (SPN) and Round Robin (RR).
- **Dynamic Time Quantum**: It utilizes a dynamic time quantum based on the burst time, reducing the phenomenon of indefinite waiting.
- **Minimization of Average Waiting Time**: Aims to minimize the average waiting time for processes.
- **Flexibility in Time Quantum**: The time quantum size influences the algorithm's behavior, resembling SPN for longer quanta and providing faster response times to a larger number of processes.
- **Overhead Considerations**: Smaller time quanta can lead to higher overhead.

### Operation
- **Half Preemptive Scheduling**: The SPNRR operates in a semi-preemptive mode, where there is a limit (time quantum) on resource usage time.
- **Priority Sorting Post-Completion**: Once a process completes, it reorganizes the ready queue based on SPN priorities.
- **Waiting and Turn-Around Time Calculations**: It involves calculations for metrics like waiting time and turn-around time, normalized turn-around time, considering GUI requirements.

### Implementation in Code
- **Initialization**: The `SPNRR` class takes process input, CPU input, and the time quantum (`tq`).
- **Scheduling Loop**: It maintains a loop where processes are allocated CPU time based on their arrival time and burst time.
- **Process Handling**: If a process's burst time exceeds the time quantum, it executes for the time quantum duration and then re-enters the ready queue. If the burst time is less than or equal to the time quantum, the process completes in one go.
- **Dynamic Adjustments**: The algorithm dynamically adjusts the ready queue and recalculates waiting times for processes awaiting CPU allocation.
- **Gantt Chart Integration**: Process start and finish times are recorded for Gantt chart visualization.

### SPNRR Simulation Screenshots
To illustrate the SPNRR scheduling algorithm's execution, below are screenshots of both the user interface after running the algorithm and the resulting Gantt chart visualization.

#### SPNRR Interface
![SPNRR Process Scheduling Simulator Interface](https://github.com/joowon7172/process_scheduling_simulator/assets/83939775/baf0a9ea-b4b4-4cde-8727-564366844fc6)
The interface showcases the input and scheduling process for SPNRR. Users can input the arrival and burst times for each process, and select the SPNRR algorithm from the drop-down menu. The table updates to display key process metrics such as waiting time and normalized turn-around time, and the power consumption for the simulation is displayed at the bottom.

#### SPNRR Gantt Chart Output
![SPNRR Scheduling Gantt Chart](https://github.com/joowon7172/process_scheduling_simulator/assets/83939775/0b5c0d54-c448-43c5-8511-ca523ead31fc)
The Gantt chart captures the SPNRR algorithm's scheduling process over time. Each block represents the time frame during which a process occupies the CPU, with different colors indicating different processes. The chart effectively visualizes the dynamic nature of the SPNRR algorithm, highlighting how the time quantum impacts process scheduling and execution.

### How SPNRR Works
The SPNRR algorithm combines the preemptive nature of RR with the efficiency of SPN. It assigns a dynamic time quantum based on the processes' burst times to minimize waiting time and prevent indefinite postponement of execution. This hybrid approach allows the algorithm to adaptively switch between behaviors akin to SPN or RR depending on the system load and process requirements. It ensures a responsive system while managing overhead and maintaining efficiency.

## Custom Development
The entirety of this project, including the logic for scheduling, core management, and performance metrics, has been developed from scratch, with no reliance on external libraries. This ensures a deep and comprehensive understanding of the scheduling concepts and their application in modern computing environments.
