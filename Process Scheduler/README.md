# Process Scheduler

A simulation of Operating System process scheduling algorithms. The goal is to visualize or report how different algorithms handle a queue of tasks.

## Functional Requirements (FR):

-   **FR01 (Input)**: Accept a list of "Processes". Each process has attributes like ID, Arrival Time, Burst Time (execution duration), and Priority.
-   **FR02 (Algorithms)**: Implement at least 3 standard scheduling algorithms:
    1.  **FIFO** (First-In, First-Out)
    2.  **SJF** (Shortest Job First)
    3.  **Round Robin** (with a configurable time quantum)
-   **FR03 (Output)**: For a given list of processes and selected algorithm, return the schedule: Start Time, Finish Time, Waiting Time, and Turnaround Time for each process.
-   **FR04 (Comparison)**: An endpoint that runs all implemented algorithms on the same dataset and compares the average waiting/turnaround times.

## Non-Functional Requirements (NFR):

-   **NFR01 (Correctness)**: The calculation logic must match standard OS theory.
-   **NFR02 (Visualization Data)**: The output format should be structured (JSON) in a way that a frontend could easily draw a Gantt chart.
-   **NFR03 (Modularity)**: The code should use the Strategy Pattern or similar to make plugging in new algorithms easy.
