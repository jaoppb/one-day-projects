# Real Time Chat

A classic real-time messaging application. The goal is to facilitate instant communication between users, potentially organized into rooms or a global lobby.

## Functional Requirements (FR)

- **FR01 (Identity)**: Users must be able to pick a username upon entering.
- **FR02 (Send/Receive)**: Users can send text messages which are immediately broadcast to other connected users.
- **FR03 (System Events)**: The chat should notify when a user joins or leaves (e.g., "User123 has entered the chat").
- **FR04 (Persistence)**: Save the last N messages so new users see recent context upon joining.

## Non-Functional Requirements (NFR)

- **NFR01 (WebSockets)**: Must use WebSockets for message delivery. Polling is not allowed.
- **NFR02 (Scalability - Logical)**: Code should be structured to allow rooms/channels, even if only one "Global" room is implemented initially.
- **NFR03 (Docker)**: The WebSocket server must be containerized.
