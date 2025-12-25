# Pinterest (Image Board)

A simplified image sharing platform. This project combines file handling with social features.

## Functional Requirements (FR):

-   **FR01 (Upload)**: Users can upload images with a title and description.
-   **FR02 (Feed)**: The home page lists images uploaded by all users (or followed users), utilizing infinite scroll pagination (cursor-based).
-   **FR03 (Pin/Save)**: Users can "pin" or save images to their personal collections/boards.
-   **FR04 (Search)**: Users can search for images by title or tags.

## Non-Functional Requirements (NFR):

-   **NFR01 (Storage)**: Images must be stored in an object store (MinIO or S3, mocked with LocalStack).
-   **NFR02 (Optimization)**: Serve thumbnails for the feed view.
    *   **Constraint**: Integration with the **Image Minifier** service (or internal equivalent) must be **asynchronous** using a **Message Queue** (e.g., RabbitMQ, Kafka, or Redis Pub/Sub). The main app publishes an "Image Uploaded" event, and a worker consumes it to generate thumbnails.
-   **NFR03 (Database)**: Use a relational database to manage the many-to-many relationship between Users, Images, and Boards.
