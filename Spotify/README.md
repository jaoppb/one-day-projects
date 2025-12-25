# Spotify (Audio Streaming)

A basic audio streaming service. This project deals with serving large media files efficiently.

## Functional Requirements (FR):

-   **FR01 (Stream)**: Users can request a song and the server streams it back.
-   **FR02 (Range Requests)**: The server must support HTTP Range headers to allow seeking (skipping forward/backward) in the audio player.
-   **FR03 (Metadata)**: Return ID3 tags or metadata (Artist, Album, Title, Duration) for the files.
-   **FR04 (Catalog)**: List available songs/albums.

## Non-Functional Requirements (NFR):

-   **NFR01 (Streaming)**: Do not read the entire file into memory. Use file system streams to pipe data to the HTTP response.
-   **NFR02 (Codecs)**: Support standard audio formats like MP3 or OGG.
-   **NFR03 (Storage)**: Audio files can be stored locally or in S3 (mocked with LocalStack), but the streaming implementation must handle the chosen source efficiently.
