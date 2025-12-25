# Battleship

A classic turn-based naval combat game. This project focuses on game logic, grid coordinate management, and state persistence.

## Functional Requirements (FR):

-   **FR01 (Setup)**: Users place their fleet of ships (sizes 5, 4, 3, 3, 2) on a 10x10 grid.
-   **FR02 (Attack)**: Players take turns "firing" at coordinates (e.g., "A5"). The system responds with "Hit" or "Miss".
-   **FR03 (Sinking)**: The system must detect when all coordinates of a ship have been hit and announce "You sunk my Battleship!".
-   **FR04 (Game Over)**: The game ends when one player loses all their ships.
-   **FR05 (Bot)**: Implement a simple AI opponent that fires randomly but targets adjacent cells after a "Hit".

## Non-Functional Requirements (NFR):

-   **NFR01 (Real-time Communication)**: The game must be implemented using **WebSockets**. The server will maintain the state of active games in memory (Stateful) and broadcast updates (Hits, Misses, Turn changes) to connected players in real-time. REST is not allowed for gameplay logic.
-   **NFR02 (Validation)**: Strictly validate ship placement to ensure no overlaps and ships are within bounds.
-   **NFR03 (Matrix)**: Use 2D arrays (matrices) for internal grid representation.
