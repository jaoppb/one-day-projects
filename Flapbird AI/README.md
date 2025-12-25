# Flapbird AI

This project involves training a simple AI agent (Reinforcement Learning or Genetic Algorithm) to play a clone of the famous "Flappy Bird" game. The backend should serve the game state and potentially the model decision logic.

## Functional Requirements (FR):

-   **FR01 (Game Engine)**: Implement a basic simulation of the Flappy Bird physics (gravity, jump, pipes). This can be server-side.
-   **FR02 (AI Agent)**: Implement an AI agent that takes the current game state (bird y-position, distance to next pipe, gap height) as input and decides whether to jump or wait.
-   **FR03 (Training)**: The system must have a mode to train the agent (e.g., running many generations) and store the best performing model.
-   **FR04 (Visualization)**: Provide a simple endpoint or websocket stream to visualize the AI playing (or return a replay of a high-score run).

## Non-Functional Requirements (NFR):

-   **NFR01 (Algorithm)**: Explicitly use a known algorithm like NEAT (NeuroEvolution of Augmenting Topologies) or Q-Learning.
-   **NFR02 (Persistence)**: Save the "Brain" (neural network weights/topology) to a file/database so it can be reloaded without retraining.
-   **NFR03 (Performance)**: The simulation loop should be decoupled from the rendering/API response speed to allow fast-forward training.
