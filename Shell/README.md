# Shell (Terminal Emulator)

This project challenges you to build a basic command-line interface (CLI) or a shell program that interacts directly with the operating system's kernel.

## Functional Requirements (FR):

-   **FR01 (Prompt)**: Display a prompt (e.g., `user@host:path$ `) awaiting user input.
-   **FR02 (Execution)**: Execute standard commands found in the `$PATH` (e.g., `ls`, `grep`, `echo`).
-   **FR03 (Built-ins)**: Implement at least `cd` (change directory) and `exit` as built-in commands (since they affect the shell process itself).
-   **FR04 (Pipes)**: Support a single pipe `|` connecting the output of one command to the input of another.
-   **FR05 (Redirection)**: Support output redirection `>` to a file.

## Non-Functional Requirements (NFR):

-   **NFR01 (Syscalls)**: Use low-level system calls (fork, exec, wait) to manage processes (if using C/Go/Rust). If using a higher-level language, ensure you are manually managing the child process lifecycle, not just passing the string to `sh -c`.
-   **NFR02 (Signal Handling)**: Handle `Ctrl+C` (SIGINT) gracefully—it should interrupt the running command, not kill the shell itself.
