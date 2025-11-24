# To-Do List (Simple CRUD)

While this is the most common project, the goal here is to create a canonical RESTful API. The system must manage the task lifecycle (create, read, update, and delete). The original description asks only for "title and description", but for a real-world scenario, we need to manage task state and timestamps.

## Functional Requirements (FR):

-   **FR01 (Create)**: The system must allow creating a task by sending a title (required) and a description (optional).

-   **FR02 (Read)**: The system must list all tasks, allowing filtering by status (completed true/false).

-   **FR03 (Update)**: The system must allow editing the title, description, or marking the task as completed.

-   **FR04 (Delete)**: The system must allow removing a task by its ID.

-   **FR05 (Find)**: The system must return a 404 error (Not Found) if the user tries to fetch or modify a non-existent ID.

## Non-Functional Requirements (NFR):

-   **NFR01 (Docker)**: The database (PostgreSQL, MySQL, or Mongo) must run in a container separate from the application, orchestrated via docker-compose.

-   **NFR02 (Quality)**: 100% unit test coverage, specifically validating the required field rules.

-   **NFR03 (Standard)**: The API must return correct HTTP codes (201 Created, 200 OK, 204 No Content, 400 Bad Request).
