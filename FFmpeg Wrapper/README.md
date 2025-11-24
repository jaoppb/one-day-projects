# FFmpeg Wrapper

This project involves wrapping functions of the FFmpeg command-line tool into a REST API. It is an excellent exercise for learning about Streams, File Uploads, and Child Processes (executing OS commands via code).

## Functional Requirements (FR):

-   **FR01 (Upload)**: The API must accept video file uploads via multipart/form-data.

-   **FR02 (Conversion)**: There must be an endpoint to convert formats, for example: converting an .mp4 video to an .mp3 audio file.

-   **FR03 (Metadata)**: There must be an endpoint that returns technical video information (duration, codec, resolution) using ffprobe.

-   **FR04 (Download Single File)**: There must be an endpoint to download a specific converted file by its identifier.

-   **FR05 (Download All Files)**: There must be an endpoint to download all converted files in a single ZIP archive.

## Non-Functional Requirements (NFR):

-   **NFR01 (Docker Environment)**: The application's Dockerfile must explicitly install the ffmpeg binary in the image's base operating system (e.g., RUN apk add ffmpeg on Alpine), as it is a prerequisite for the code to run.

-   **NFR02 (Disk Management)**: The system must clean up temporary files (original upload and converted file) after delivering the response to avoid filling up storage.

-   **NFR03 (Async)**: Video processing must not block the main web server thread; the code must await the child process asynchronously.
