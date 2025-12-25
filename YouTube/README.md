# YouTube (Video Streaming)

A robust video streaming platform. Unlike Spotify (audio), this project deals with high-bandwidth video delivery, potentially involving adaptive bitrate streaming (HLS/DASH).

## Functional Requirements (FR)

- **FR01 (Upload)**: Users can upload video files. The system should process them for web playback.
- **FR02 (Streaming)**: Users can watch videos. The player must support seeking.
- **FR03 (Thumbnails)**: The system automatically generates a thumbnail for the uploaded video.
- **FR04 (Comments)**: Users can comment on videos.

## Non-Functional Requirements (NFR)

- **NFR01 (HLS/DASH)**: Instead of a simple progressive download (like the Spotify project), implement **Adaptive Bitrate Streaming**. The uploaded video should be transcoded into multiple qualities (e.g., 360p, 720p, 1080p) and served via HLS (`.m3u8` playlists) or DASH.
- **NFR02 (Transcoding)**: Use FFmpeg to handle the video processing pipeline.
- **NFR03 (Storage)**: Video segments (`.ts` files) must be stored efficiently (S3/MinIO compatible).
