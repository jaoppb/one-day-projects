# Ballot Box

A voting system allowing users to create polls and others to vote on them. This project balances CRUD operations with data integrity and aggregation.

## Functional Requirements (FR):

-   **FR01 (Create Poll)**: A user can create a poll with a question and multiple options.
-   **FR02 (Vote)**: Users can view a poll and cast a vote for one of the options.
-   **FR03 (Results)**: Users can view the results of a poll, showing the count (and percentage) for each option.
-   **FR04 (Real-time Updates)**: (Optional) If a user is viewing the results page, the chart should update automatically when a new vote comes in.

## Non-Functional Requirements (NFR):

-   **NFR01 (Integrity)**: The system should attempt to prevent multiple votes from the same client (e.g., using IP tracking, local storage tokens, or simple auth if implemented).
-   **NFR02 (Database)**: Votes must be persisted in a database (SQL or NoSQL).
-   **NFR03 (Concurrency)**: Ensure vote counts are accurate even if multiple users vote exactly at the same time (Database transactions or atomic increments).
