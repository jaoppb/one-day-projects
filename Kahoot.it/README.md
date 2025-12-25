# Kahoot.it (Clone)

A simple real-time quiz game where a "Host" creates a game room and "Players" join to answer questions. This project focuses heavily on WebSocket communication and managing synchronized game state.

## Functional Requirements (FR):

-   **FR01 (Host Game)**: A user can act as a Host to create a new game session. The system must generate a unique "Game PIN".
-   **FR02 (Join Game)**: Players can join a specific game using the Game PIN and a nickname.
-   **FR03 (Real-time State)**: The Host controls the flow (Start Game, Next Question). When the Host moves to the next stage, all connected Players' screens must update simultaneously.
-   **FR04 (Answering)**: Players submit answers within a time limit. The system must accept answers and calculate scores based on correctness and speed.
-   **FR05 (Leaderboard)**: At the end of each question (or the game), display a leaderboard showing the top players.

## Non-Functional Requirements (NFR):

-   **NFR01 (WebSockets)**: Communication between Host, Players, and Server must use WebSockets (e.g., Socket.io, raw WS) for low-latency updates.
-   **NFR02 (Concurrency)**: The server must handle multiple concurrent game rooms without state collision.
-   **NFR03 (Ephemeral State)**: Game state can be stored in-memory (e.g., variables or Redis) as long-term persistence isn't strictly necessary for a quick session, though Redis is recommended for scalability.
