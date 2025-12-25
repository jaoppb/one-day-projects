# Leetcode (Remote Code Execution)

A system that allows users to submit code in a specific language to solve a problem, which is then executed safely on the server.

## Functional Requirements (FR):

-   **FR01 (Submission)**: Users submit source code and a problem ID.
-   **FR02 (Execution)**: The system compiles (if necessary) and runs the code against a set of hidden test cases.
-   **FR03 (Verdict)**: Return the result: `Accepted`, `Wrong Answer`, `Time Limit Exceeded`, or `Compilation Error`.
-   **FR04 (Languages)**: Support at least one language (e.g., Python or C++).

## Non-Functional Requirements (NFR):

-   **NFR01 (Sandboxing & Orchestration)**: **CRITICAL**. The user code must run in an isolated environment managed by **Kubernetes**. The system should spawn ephemeral Pods (or Jobs) to execute the code and collect the results, ensuring complete isolation and resource control.
-   **NFR02 (Time/Memory Limits)**: Enforce strict limits on execution time (e.g., 2 seconds) and memory usage via Kubernetes Resource Quotas.
-   **NFR03 (Concurrency)**: Handle multiple submissions simultaneously without one blocking the others.

## Improvements

-   **FR05 (Multi-Language)**: Add support for at least **two additional languages** (e.g., if you started with Python, add Java and C++). Each language may require different container images or compilation steps.