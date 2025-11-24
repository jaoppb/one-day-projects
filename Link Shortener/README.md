# Link Shortener

A service that receives a long URL and returns a shortened URL. The original description is simple: "receive a link returns a link". The technical challenge here is the short code generation algorithm and efficient redirection.

## Functional Requirements (FR):

-   **FR01 (Shorten)**: The endpoint must accept a long URL and return a JSON with the short code and the full shortened URL.

-   **FR02 (Redirect)**: When accessing the route GET /:code, the server must redirect the user to the original URL.

-   **FR03 (Validation)**: The system must reject inputs that are not valid URLs (must contain http:// or https:// protocol).

-   **FR04 (Idempotency)**: If the user sends the same URL twice, the system may choose to return the existing short code.

## Non-Functional Requirements (NFR):

-   **NFR01 (Performance)**: Redirection must use status code 301 (Permanent) or 302 (Temporary) correctly so browsers understand it.

-   **NFR02 (Algorithm)**: The generated code should be at most 6 to 8 characters long (e.g., NanoID or Base62) to be user-friendly.

-   **NFR03 (Tests)**: Test for collisions (ensure generated codes are unique) and validate the redirection in integration tests.
