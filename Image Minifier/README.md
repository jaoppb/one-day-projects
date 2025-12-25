# Image Minifier

A service dedicated to optimizing image file sizes without significant loss of visual quality. This project focuses on handling binary data streams and integrating with image processing libraries (like `sharp`, `imagemin`, or system tools).

## Functional Requirements (FR):

-   **FR01 (Upload)**: The API must accept image uploads (single or multiple) via multipart/form-data.

-   **FR02 (Optimization)**: The system must process the uploaded image to reduce its file size. It should support common formats like JPG, PNG, and WebP.

-   **FR03 (Format Conversion)**: (Optional) Allow the user to request a format change (e.g., upload PNG, get optimized WebP) to further reduce size.

-   **FR04 (Download)**: The optimized image must be stored in an S3 bucket. Return a URL to access the file from the bucket.
    *   **Constraint**: Use **LocalStack** to mock S3 services for local development and testing.

-   **FR05 (Stats)**: The response or notification should indicate the savings (e.g., "Original: 2MB, Optimized: 500KB, Savings: 75%").

-   **FR06 (Async Processing & Notification)**: The image optimization must be processed asynchronously. The upload endpoint returns immediately (HTTP 202). When the processing is complete, the client must be notified via a **WebSocket** event containing the result and download URL.

## Non-Functional Requirements (NFR):

-   **NFR01 (Performance)**: Image processing is CPU-bound. Ensure the application remains responsive (using streams or worker threads).

-   **NFR02 (Docker)**: The environment must support the necessary image manipulation libraries (some require native bindings).

-   **NFR03 (Limits)**: specific file size limits (e.g., max 10MB upload) should be enforced to prevent memory exhaustion.
