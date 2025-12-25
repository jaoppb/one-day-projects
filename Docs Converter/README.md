# Docs Converter

This project aims to build a service that converts document formats. The primary goal is to convert `.docx` (Word) files to `.pdf` and potentially vice-versa. This challenges the developer to work with file parsing libraries or shell out to tools like LibreOffice/Pandoc within a containerized environment.

## Functional Requirements (FR):

-   **FR01 (Upload)**: The API must accept a document file (specifically `.docx` or `.pdf`) via multipart/form-data.

-   **FR02 (DOCX to PDF)**: There must be an endpoint to convert a valid `.docx` file into a `.pdf` file.

-   **FR03 (PDF to DOCX)**: There must be an endpoint to convert a `.pdf` file back into an editable `.docx` format (best effort).

-   **FR04 (Download)**: The converted file must be uploaded to an S3 bucket. The response should return a pre-signed URL (or a direct public link) to download the file from S3.
    *   **Constraint**: Use **LocalStack** to mock S3 services for local development and testing.

-   **FR05 (Validation)**: The system must validate file extensions and MIME types to ensure only supported formats are processed.

## Non-Functional Requirements (NFR):

-   **NFR01 (Docker Dependencies)**: The Docker image must include any necessary system dependencies for conversion (e.g., LibreOffice, Pandoc, or specific libraries) so it works out-of-the-box.

-   **NFR02 (Cleanup)**: Temporary files created during the conversion process must be deleted immediately after the request is completed.

-   **NFR03 (Concurrency)**: The conversion process (which can be CPU intensive) should not block the main event loop; consider using worker threads or a queue if necessary (though simple async execution is acceptable for this level).
